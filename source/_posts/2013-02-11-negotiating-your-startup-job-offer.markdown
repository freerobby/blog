---
layout: post

title: "Negotiating Your Startup Job Offer"
date: 2013-02-21 10:00
comments: true
categories: [Business, Startups]
---

Over the last three years I've been on both ends of job offers at startups. One thing that's struck me is how little most applicants know about what to expect in a job offer, and in many cases, what the written offer they've received actually means. I was extremely fortunate that the first startup job offer I received was written by a [pair](https://twitter.com/Pistachio) of [founders](https://twitter.com/graysky) who had the utmost integrity and explained things very clearly. Since then I've learned that not every employee is so lucky.

This post doesn't aim to teach you negotiation itself, but rather to acclimate you to the standards and vernacular of startup negotiations. It assumes you're a startup newcomer.<!--more-->

## Salary

One of the biggest myths that I'd heard while tucked away in my big company cubicle was that in order to get into the startup game, you had to take a substantial paycut. This is false, especially if you're a developer in today's funding climate. VC funded startups pay very close to market rate salaries. Your ask should be the same number it would be at a more established company with hundreds or thousands of people.

### Seed-Stage Companies

An exception to the above statement exists for companies who have raised very little capital and are not generating revenue. These companies do not usually have full salaries budgeted into them. If you join such a seed stage company, you should expect to work for less than a market rate salary until a larger round is raised. However, you should be compensated for this with increased equity.

It's also a good idea to have a discussion about what your market rate salary will be after raising a Series A. This avoids surprises later. Because you haven't yet demonstrated your skills inside the company and because the funding timeline is indefinite, it's difficult for either party to make specific promises. My recommendation is to have something written that states what market rate would be for you right now. This way, if it takes two years to raise a Series A and you've grown into a bigger role during that time, you aren't boxed into a number that you arrived at two years earlier and whose value you've surpassed, but you do have a quantitative starting point for determining what your salary will be.

Other methods of compensation and risk adjustment may also arise. For example, when I joined oneforty in 2009, I took a 30% pay cut. We expected to raise money in 6-12 months, and structured my employment offer such that I would receive a 30% bonus upon the raising of a Series A (subject to "outstanding performance" per my manager's discretion). The offer also stated that at that time, my salary would be raised to a market rate. It did not specify what that market rate would be. Before joining, I informed the founders via email of the other offers I was prepared to pass on, and they told me that what I cited was "in a reasonable range." The entire process from initial offer to post-Series A adjustment went very smoothly and without any surprises for anyone.

Whatever agreement you come to, make sure you get it in writing. This protects both parties and ensures that everybody leaves the conversation with the same impression. Every lawyer I know attests that there are more fights over what was said than what was written.

### What About Bonuses?

Startups do not typically offer cash bonuses unless they are generating substantial revenues.[^sales-bonuses] For nonprofitable entities with limited runway, it is much better for everybody that the company provides monthly compensation without accruing variable costs of ~10% of annual payroll every year. It's easier on the books and it prevents the company from setting expectations that it may be unable to meet. Though your cash compensation will likely be comprised only of salary; you can certainly use a bonus you'd earn elsewhere as leverage during negotiations.

## Equity

Equity procedures and vernacular are by far the least understood component of startup job offers. Especially for employees with no background in business law or finance, the specifics pertaining to equity grants are often wildly misunderstood.

### When Equity Goes Wrong: A Narrative

Four years ago, a company granted you 0.5% of it to join as a seed stage engineer. The company has now raised a Series B, and you're ready to take your shares and move on.

Not so fast.

First, the company didn't really grant you 0.5% of it. It granted you the option to _buy_ 0.5% of it at some discount from its seed stage valuation (when you joined). Let's say that discount was 70% and that valuation was \$5M, so you have the option to buy 0.5% (\$25k) of it at a 70% discount of \$7,500. You decide you'll just wait until it sells or goes public, then buy your shares for $7,500 and then sell them at market price.

That won't work either.

Leaving the company invokes your exit clause, which stipulates that you have 90 days to purchase your options, or else you completely forfeit them. The company is not obligated to remind you of this. If you forget to exercise your options during this period, they're gone. If you don't have $7,500 to spare during this period, they're gone. Your only option is to cough up $7,500 or relinquish all of the equity you were told you'd been "given."

If you're leaving Facebook, this is a no brainer. But you're probably not leaving Facebook. You're probably leaving a B stage company that is growing fast but still has problems with churn or customer acquisition or scalability or some other solvable but imminent problem, and while promising, its success is far from certain. You have to decide whether you want to place a $7,500 wager on this company.

You place the wager, and two years later, the company sells for $20M after a year of mediocre numbers and failing to raise a Series C in a downward-sloping economy. It's not the beachhouse you were hoping for, but your $7,500 investment looks to be worth $100k based on a 4x multiple of the original $25,000 value, right?

Nope.

Your stock was restricted, not common. Investors have "preference," which means they get reimbursed for what they put in before anybody else sees a dime. The company raised $18M in combined seed, Series A and Series B investments. First, those investors get their $18M back. Then, there's $2M to be distributed proportionally among stakeholders. You've come out a narrow 25% ahead because of your discount price ($5M * 0.3 vs 2M). You leave with a $2,500 pre-tax profit on your $7,500 investment.

Nope.

When the company issued new shares to Series A and Series B investors, you got diluted. Your 0.5% of the company now constitutes only 0.35% of it. 0.35% of 2M leaves you with... $7,000.

That's right. After four years of work and digging into your savings to preserve your stake in the company, you've _lost_ $500. You let out a long sigh, lamenting that this "granted" equity became a $500 loss.

This story is contrived, but it is not absurd or unrealistic. I recount it like this to emphasize how important it is for you to understand how equity distribution actually works when you're negotiating it.

### Starting Simple: How Does Equity Work?

Equity is given in the form of stock options. Stock options are not gifts; rather they are "options" to buy some amount of stock at a fixed, usually discounted price. The nice thing about this system is that, at least in the ideal case, you don't need to buy the options until you are ready to sell them.

For example, you have options on 1% of a company valued at $1.6M. There are 100k shares outstanding, each worth $16. Your strike price is $0.80, so you make $15,200 before taxes upon selling them:

$$
\begin{eqnarray*}
\mathbf{Your\ Shares} & = & \mathit{\%\ Ownership} & * & \mathit{Shares\ Outstanding} \\
                     & = & 0.01                  & * & 100,000 \\
                     & = & 1000
\end{eqnarray*}
$$

$$
\begin{eqnarray*}
\mathbf{Profit} & = & \mathit{Your\ Shares} & * & \mathit{Sell\ Price} & - & \mathit{Your\ Shares} & * & \mathit{Strike\ Price} \\
                & = & 1000            & * & $16                  & - & 1000            & * & $0.80 \\
                & = & $15200
\end{eqnarray*}
$$

### How Much Equity Should I Get?

There are too many  variables (company stage, company valuation, employee experience, employee domain knowledge, employee salary requirements), let alone disagreement among industry veterans[^fair-equity], to generalize how much equity you should get and when, but Babak Nivi put together a [table of option grants](http://venturehacks.com/articles/option-pool-shuffle#market) that rings true based on my experiences:

> Title Range (%)
>
> CEO 5 – 10
>
> COO 2 – 5
>
> VP  1 – 2
>
> Independent Board Member  1
>
> Director  0.4 – 1.25
>
> Lead Engineer 0.5 – 1
>
> 5+ years experience Engineer  0.33 – 0.66
>
> Manager or Junior Engineer  0.2 – 0.33

You'll notice that Nivi talks about equity in terms of percentages. As Chris Dixon [explains](http://cdixon.org/2009/08/27/the-one-number-you-should-know-about-your-equity-grant), this is the only number you care about in your equity offer:

> The only thing that matters in terms of your equity when you join a startup is what percent of the company they are giving you. If management tells you the number of shares and not the total shares outstanding so you can’t compute the percent you own – don’t join the company! They are dishonest and are tricking you and will trick you again many times.

It's a dangerous game to try to anticipate what your shares will be worth, but if you want to indulge, take your percentage, divide it by two to account for dilution and a low strike price, and multiply it by whatever you think the company might sell for. That's the ballpark of what a home run hit gets you. Let's look at a few examples:

$$
  \mathbf{Equity\ Payout} = \frac{\mathit{Equity\ Percentage} * \mathit{Sale\ Price\ of\ Company}}{2}
$$

You get 0.5% of a company that sells for $25M: $$\frac{\mathit{0.005} * \mathit{25000000}}{2}=$62500$$

You get 1% of a company that sells for $15M: $$\frac{\mathit{0.01} * \mathit{15000000}}{2}=$75000$$

You get 0.25% of a company that sells for $150M: $$\frac{\mathit{0.0025} * \mathit{150000000}}{2}=$375000$$

Though it's tempting, if you're a startup employee, I caution you not to think about equity in such absolute terms, as they are difficult to predict. Look at your equity as a great bonus if things go well. The sad truth is that an overwhelming majority of startups fail, so for the sake of personal financial planning, assume it will amount to nothing. In the best case scenario it will buy you a nice car or provide a down payment on a home. It's not a ticket to establishing independent wealth or never to work again.

### Will I get more equity after I join?

There are a few situations after joining when you may be granted additional equity: first, as new shares are issued, you may be allotted some of them to avoid dilution; second, equity is sometimes used as a performance bonus, especially when companies don't have enough revenue to provide extra cash; third, equity is often granted as compensation for a promotion.

### Vesting Schedules

Your equity should begin accruing as of the start of your employment. Do not listen to any hiring manager who tells you that in order to protect the company, you need to work for a while before you'll receive any equity.[^equity-from-day-one] There is a process called "vesting" that takes care of this and any founder who is both honest and knowledgable uses it.

Vesting lets the company give you some fixed number of stock options, subject to your working at the company for some period of time. Brad Feld [explains](http://www.feld.com/wp/archives/2005/05/term-sheet-vesting.html) the standard 4/1 vesting schedule:

> Industry standard vesting for early stage companies is a one year cliff and monthly thereafter for a total of 4 years. This means that if you leave before the first year is up, you don’t vest any of your stock. After a year, you have vested 25% (that’s the “cliff”). Then – you begin vesting monthly (or quarterly, or annually) over the remaining period. So – if you have a monthly vest with a one year cliff and you leave the company after 18 months, you’ll have vested 37.25% of your stock.

Vesting is great because it protects everybody. Employees know exactly what they will get if they put in their time, and companies avoid the risk of an employee who takes equity and runs away with it.

### Trading Salary for Equity: Do the Math

Some employers talk about equity and salary as dials that you can adjust, increasing one while decreasing the other. Since startups are strapped for cash, this is always presented as the employee giving up some salary in exchange for more equity.

Sometimes these deals are fair, and sometimes they're not. What makes them difficult and often unfair for the employee is that there are a handful of existential disadvantages that come along with taking equity as a substitute for salary. It's important that they be understood so that they can be overcome:

1. Salary accrues over one year, while stock options vest over four years, so in order to break even, the value of your extra stock options needs to be 4x the salary that you're giving up. In reality it should be even more because your stock is going to be a different class than what the investors get, and that means the investors will get preference over you should the company endure a [downround](http://www.investopedia.com/terms/d/downround.asp#axzz2KbknGfYk) or a poor exit. This is immensely unfair to you because if you're giving up cash for equity, you are effectively investing in the company but not receiving the favorable terms that other investors get.
1. Even if the company is doing well, your stock options will likely get diluted at some point over your four year vesting schedule when the company raises more money. This decreases the percentage of the company that you have the right to buy.
1. Stock options are a one-time grant, so you're accepting one-time compensation in exchange for recurring compensation. The portion of your compensation that you receive in equity will not be accounted for in your future salary bumps at the company, and because salary increases are often given in terms of percentages, your losses will likely be compounded during this time.
1. Company valuations are monopoly money until their stock becomes liquid. Having $200,000 in stock options doesn't mean anything if you can't sell your stock, and you can't sell your stock unless your company goes public or you find a private buyer in a secondary market, which won't happen unless your company is far down its path to a successful exit.
1. Exercising your stock options has a monetary cost to you. If you get $25,000 in options with a 60% discount, that means the company is chipping in $15,000 for your stock and you're chipping in $10,000 it.

Now that you understand the inherent disadvantages of this trade, you want to know if the specific deal on the table (to exchange some $x in equity for some $y in salary) is a good one. The best way to determine this is to look at the deal that the investors get, and compare it to the deal that you're getting. You want a risk/reward ratio that is better than theirs.

Let's start with a losing scenario. Tony Wright [illustrates a typical example](http://www.tonywright.com/2008/a-newbies-guide-to-startup-compensation-or-stock-options-will-make-me-rich) where the equity-salary lever is a bad deal for the employee[^my-claim-not-tonys]:

> Let’s say we have an engineer who is getting .5% of the company vested over 4 years. He’s making $80k, but probably could make $90k at a company with limited equity opportunity. Let’s assume a target exit price of $50,000,000 (oh, happy day!).
>
> Our engineer is spending $10k per year to have a shot at a $62,500 per year. If he spends the full four years there, he’s “invested” $40k for a shot at $250k (a 6x+ return– not bad). When you run the same scenario with a billion dollar exit, it’s starting to look a lot prettier. When you run it at a Flickr-sized exit ($20m), it’s not looking like that great of a bet.

A 6x-exit does sound rosy, but when you're shooting for a big reward, you must also consider the big risk. If you were this employee and you dug into the details here, you'd see that:

1. You're taking a bigger risk than the company's investors are; and
1. You receive only half the reward that the company's investors receive in the case of a success.

Let's say you got into the company when it had a $4M valuation (A $90k engineer receiving a 0.5% equity grant implies (s)he is early). Your 0.5% entitles you to buy $20k worth of its shares at that valuation. That means that after four years, you've given up $40k in cash for $20k worth of illiquid stock. If you were an investor in the company, your money would have bought you $40k worth of the stock, it would be preferred stock rather than common stock, and it would not be subject to any vesting period. Dollar for dollar, investors got twice as much stock as you did, and they got it on much better terms.

Now let's change the hypothetical to show when taking equity might make sense. A Director of Engineering comes on for $110k and 1.25% (he would normally make $140k) after the company raises a Series A and is valued at $14M. He is giving up $120k over four years to pick up $175k worth of options, earning 46% more stock per dollar invested than the investors who put in money at a $14M valuation. This increased reward helps to compensate for the increased risk stemming from the aforementioned disadvantages of taking equity over stock.

If you can afford to play the risk/reward game and want to turn up your equity in exchange for some salary, by all means see if you can find a deal that makes sense. There are founders who offer very meaningful equity grants to employees who are willing to sacrifice a portion of their paycheck. But in my experience, this latter example is the exception and Tony's example is the rule. Whatever's on the table, do the math and be cognizant of the tradeoff you're making.

### The Most Important Thing About Equity

Your equity will be worth something or it won't. Which side of that coin you land on matters more than anything -- more than how quickly you vest or how much equity you get or what kind of discount you get or what stage you join at. A bad negotiator at a successful company will wind up with more equity value than a shrewd negotiator at an unsuccessful company.

Betting on equity should imply that you believe in the vision of the company and that you have immense faith in the people you're working with. At the end of the day, those things will impact how much your equity is worth more than any of the aforementioned advice.

## Benefits

With the exception of health insurance, benefits are less numerous and less generous at startups than they are at established companies. Very few startups offer 401k plans; even fewer provide employer matching. The startups I've seen or been at that offered 401k plans instituted them because there was some bloc of employees who wanted to put away more than $5k per year ($5k is the maximum you can do on your own via an IRA).

Startups that have raised funding of any sort should provide your health insurance and they should pick up most if not all of the bill. If the startup doesn't offer a healthcare plan, it should reimburse you for an individual health care plan. The more generous of startups will provide you with dental coverage.

## In Conclusion

The difficult part of negotiating a startup job offer is learning the inside baseball. If you can get past the jargon that you never saw until today, you'll find that, like most negotiations, it boils down to math and common sense.

There are plenty of things to adapt to when you switch to startup life -- culture, work hours, individual autonomy -- but unless you're committed to joining at the seed stage or earlier, a jarring compensation reduction isn't one of them.

If you still have questions about something in your offer letter, or if something seems a little fishy, you can ask questions in the comments and I will answer them, or if it's confidential, you can email me at [robby@freerobby.com](mailto:robby@freerobby.com) and I'll respond privately.

_Thanks to [Chad Mazzola](http://hellohappy.org) for reading an early draft of this post and providing valuable feedback._

[^fair-equity]: I love Joel Spolsky's [approach to divvying equity](http://answers.onstartups.com/questions/6949/forming-a-new-software-startup-how-do-i-allocate-ownership-fairly/23326#23326), but it is a minority opinion.

[^sales-bonuses]: Exceptions exist for roles whose market compensation is typically paid in the form of bonuses, e.g. sales executives who are paid according to how much revenue they bring in.

[^my-claim-not-tonys]: Tony describes only the situation; it is my claim, not his, that the equity tradeoff is a bad one.

[^equity-from-day-one]: Some companies require a board meeting to issue your equity paperwork. This is fine, but the agreement should be retroactive back to your starting date when you receive it.
