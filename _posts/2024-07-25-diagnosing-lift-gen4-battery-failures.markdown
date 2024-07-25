---
layout: post

title: "Diagnosing Lift Gen4 Battery Failures"
date: 2024-07-25 10:00
comments: true
categories: [Hardware]
hidden: true
---
    
If you're reading this post, you probably have a [Lift efoil](https://liftfoils.com) with a battery problem.  Lift's battery management system (BMS) is highly protective. This is mostly a good thing, but occasionally it causes the BMS to lock you out of a working battery.

This guide walks you through pulling data off the battery, to assist a battery expert in determining whether your battery can be salvaged or whether it has irreversible cell or hardware damage.

We achieve this by using an undocumented feature of the Gen4 Lift battery, which is its wifi connectivity. When charging your battery (or when applying +12V to pin 4 of the data port), the Gen4 battery creates a wifi network that we can join to pull data from.

This technique only works on Gen4 batteries manufactured by Lithos. If the top of your battery has Torx screws around the outer edge and a "Lithos" logo on the label, then this guide should work. If your battery lacks either of these things, unfortunately, this guide won't help you.

## Using This Guide

### Legal Disclaimer

What you do with this guide is entirely your responsibility. I provide it "as is", and I make no representation or warranty of any kind to you or anyone else.

### Read Ahead

I recommend reading this guide in its entirety before starting. You will lose internet connectivity when joining your battery's wifi network, so be sure you install the required software and understand what you need to do before joining that network.

### Copy and Paste

I provide a number of commands for you to run. Please copy and paste them, rather than retyping them, to avoid typos.

### Experiment at Your Own Risk

When providing commands to the BMS, it is possible to cause damage. I am confident that the commands I am asking you to run do not cause damage or in any meaningful way change the state of the battery.

However, the commands I am using are not an exhaustive list of what the BMS supports. There are other commands you can run that will cause damage. So if you decide to improvise or experiment, be careful.

## Installing Required Software

We will use a tool called "telnet" to talk to the battery.

### Mac Instructions

Launch a Terminal window by pressing Command + [space] and entering `terminal.app`

#### Install Homebrew

[Homebrew](https://brew.sh) is a tool for installing other command line tools. Install it by copy/pasting this command into your terminal:

`/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"`

#### Install Telnet

After homebrew is installed, use it to install Telnet by copy/pasting this command into your terminal:

`brew install telnet`

### Windows Instructions

Open the Windows menu, type `cmd` in the Run command box, and press enter.

At the prompt, run `pkgmgr /iu:"TelnetClient"`

Exit the command prompt once installation is complete.

## Connecting to Your Battery

The first thing you must do is activate your battery's wifi network. The easiest way to do this is to plug your battery into your charger.

After about 10 seconds, the battery should advertise its own wifi network. It is typically named `Lift-BMS-XXXXX` where `XXXXX` is a 5-digit number. Connect to this network. It does not require a password. You will lose internet access upon doing this.

## Obtaining Your Battery's IP Address

### The Easy Method

Your battery's IP address is probably `192.168.4.1`. Try skipping this step assuming that is true, and if you have problems, come back and try the discovery method below.

### The Discovery Method (Mac)

1. Launch a Terminal window by pressing Command + [space] and entering `terminal.app`
2. Run the command `route -n get default | grep gateway`
3. You will get a response of: `gateway: <Battery IP Address>` where `<Battery IP Address>` is the IP address of the battery.

### The Discovery Method (Windows)

1. Open the Windows menu, type `cmd` in the Run command box, and press enter.
2. Run the command `ipconfig | find "Gateway"`
3. You will get a response of: `Default Gateway . . . . . . . . . : <Battery IP Address>` where `<Battery IP Address>` is the IP address of the battery.

## Talking to Your Battery

If you're on a Mac, launch a Terminal window by pressing Command + [space] and entering `terminal.app` 

If you're on a PC, open the Windows menu, type `cmd` in the Run command box, and press enter. 

### Initiate a Telnet Connection

Run `telnet <Battery IP Address>` where `<Battery IP Address>` is the IP address of your battery.

You should quickly receive a `Remote Session Connected` notice, followed by a prompt that looks like `R-BMS> `.

If you see:
```
Trying <Battery IP Address>...
telnet: connect to address <Battery IP Address>: Operation timed out
telnet: Unable to connect to remote host
```

Then most likely you are using the wrong IP address. Try the Discovery Method as outlined above.

### Pulling Battery Data

You will now run a sequence of commands to pull data from the battery. I will briefly describe what each command does.

#### Get the Current Time.

At the `R-BMS> ` prompt, enter `time` and then press enter.

This will report what the battery believes the current time to be. It's convenient if this is accurate, but don't worry if it's not; as long as we know what time the battery thinks it is, we can work backwards to establish the correct timeline later.

The output will look something like this:

`2024-07-07 16:28:59.591`

#### Get the Alarm List

Next, enter `alarm-list` and press enter.

This command will generate a table of relevant faults and warnings, as well as some data to indicate whether and how frequently they have occurred.

It will look something like this:

```
Alarm List:
--------------------------------------------------------------------------------------------------------------------------------------------------
Cat# ID# Alarm Name                                Instances Enabled Occurrences LastTriggered LastCleared BCC BCD Active TranLevel SubInstance
--------------------------------------------------------------------------------------------------------------------------------------------------
 0    0 Fault: Severe Over Temperature Limit            1       1           0              0           0    1   1    0      0.0000      0
 0    1 Fault: Severe Over Voltage Limit                1       1           0              0           0    1   1    0      0.0000      0
 0    2 Fault: Severe Under Voltage Limit               1       1           0              0           0    1   1    0      0.0000      0
 0    3 Fault: Power Pin Severe Over Temp Limit         1       1           0              0           0    1   1    0      0.0000      0
 0    4 Fault: Severe Capacity Loss                     1       1           0              0           0    1   1    0      0.0000      0
 0    5 Fault: Open Voltage Sense Wire                  1       1           0              0           0    1   1    0           0      0
 0    6 Fault: Contactor Failed Open                    1       1           0              0           0    1   1    0           0      0
 0    7 Fault: Contactor Failed Closed                  1       1           0              0           0    1   1    0           0      0
 0    8 Fault: All Module Thermistors Failed            1       1           0              0           0    1   1    0           0      0
 0    9 Fault: Power Pin Thermistor Failed              2       1           0              0           0    1   1    0           0      0
 0   10 Fault: Water Ingress                            1       1           0              0           0    1   1    0      0.0000      0
 0   11 Fault: Fuse Blown                               1       1           0              0           0    1   1    0           0      0
 0   12 Fault: Critical Hardware Failure                1       0           0              0           0    1   1    0           0      0
 0   13 Fault: Current Sense Failure                    1       0           0              0           0    1   1    0           0      0
 0   14 Fault: Self Discharge Failure                   1       1           0              0           0    1   1    0      0.0000      0
 0   15 Fault: Over Voltage Limit                       1       1           0              0           0    1   1    0      0.0000      0
 0   16 Fault: Under Voltage Limit                      1       1           0              0           0    0   1    0      0.0000      0
 0   17 Fault: Over Temperature Limit                   1       1           0              0           0    1   1    0      0.0000      0
 0   18 Fault: Power Pin Over Temperature Limit         1       1           0              0           0    1   1    0      0.0000      0
 0   19 Fault: Under Temperature Limit                  1       1           0              0           0    1   1    0      0.0000      0
 0   20 Fault: Over Current Limit Charge                1       1           0              0           0    1   0    0      0.0000      0
 0   21 Fault: Over Current Limit Discharge             1       0           0              0           0    0   1    0      0.0000      0
 0   22 Fault: Ground Fault Detected                    1       0           0              0           0    1   1    0           0      0
 0   23 Fault: Pre-Charge Timed Out                     1       0           0              0           0    1   1    0           0      0
 0   24 Fault: Pre-Charge Circuit Too Hot               1       0           0              0           0    1   1    0           0      0
 0   25 Fault: Pre-Charge No Load Detected              1       0           0              0           0    1   1    0           0      0
 1   26 Warning: Imbalanced SoC between Cell Groups     1       1           0              0           0    0   0    0      0.0000      0
 1   27 Warning: Voltage Reading Mismatch               1       1           0              0           0    0   0    0           0      0
 1   28 Warning: ADBMS Communications Problem           1       1           0              0           0    0   0    0           0      0
 0   29 Warning: CANbus Communications Problem          1       1           0              0           0    1   1    0           0      0
 1   30 Warning: Module Thermistor Failed               6       1           0              0           0    0   0    0           0      0
 1   31 Warning: Hardware Failure                       1       0           0              0           0    0   0    0           0      0
 1   32 Warning: Balancing Circuit Problem              1       1           0              0           0    0   0    0           0      0
 1   33 Warning: Power Pin terminals are hot            1       1           0              0           0    0   0    0      0.0000      0
 1   34 Warning: I2C Communications Problem             2       1           0              0           0    0   0    0           0      0
 1   35 Warning: Self Discharge Problem                 1       1           0              0           0    0   0    0      0.0000      0
 0   36 Fault: Power Cable Disconnected                 1       1           0              0           0    1   1    0           0      0
```

#### Get the Logs

Next, enter `logs all` and press enter.

This will generate three lists:
1. A list of log entries created by various battery operations.
2. An "Event Summary" list of faults and alarms.
3. A "Cycle Summaries" list of all the times you've ridden with or charged your battery.

You may see some scary-sounding errors and alarms dating back to before you received your battery. Don't worry about this, and please do not accuse Lift or Lithos of anything nefarious based on this. Fault and alarm conditions are often generated intentionally during testing to ensure a battery is safe and that the BMS protection mechanisms are working.

#### Get the System Variables

Next, enter `sysvar-list` and press enter.

This will display all data available about the current state of your battery -- cell voltages, temperatures, BMS settings, and more.

#### Get the BMS Version

Finally, enter `version -d` and press enter.

This will display firmware version information about what is currently running on your battery. This can be useful to know if you get data back in a format that is different than what's expected.

## Saving the Data

### Mac Instructions

1. Click inside your Terminal window.
2. Click the "Shell" menu and then select "Export Text As..."
3. When prompted, save the file somewhere for safe keeping.

## Getting Help
                                                      
The actual diagnosis of battery issues is beyond the current scope of this guide. However, now that you have the diagnostic data for your battery, you can post it to the [Lift Foils Owners Group](https://www.facebook.com/groups/589350625100122) or other online forums help.