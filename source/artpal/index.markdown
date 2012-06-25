---
date: '2008-08-02 20:40:30'
layout: page
slug: artpal
status: publish
title: ArtPal
wordpress_id: '242'
---

### Download


Please download ArtPal from the [ArtPal Wordpress Page.](http://wordpress.org/extend/plugins/artpal/)

ArtPal is a free ([GPL](http://www.gnu.org/licenses/gpl.txt)) [Wordpress](http://www.wordpress.org) plugin, originally written for Artists, to seemlessly integrate [PayPal](http://www.paypal.com) with their Wordpress blogs so that they can sell their work online.

Artists' online stores tend to be simple, but also unconventional. The items for sale are one of a kind, and thus the overhead that deals with keeping "stock" is unnecessary. I created ArtPal so that artists would have a simple, easy-to-use solution for their unique needs.

ArtPal's most important features are:



	
  * **Easy PayPal integration**--all you need to supply is your PayPal email address!

	
  * **Real-time sales updates**--as soon as your item sells, ArtPal will disable it from being sold. You'll never worry about your item selling twice!

	
  * **Professionally supported**--businesses mean business. [Digital Sublimity](http://www.digitalsublimity.com/) provides commercial support, so you can be rest assured that your critical application will stay up and running when you need it.


If you have any questions about how to use ArtPal, please post them as comments on this page. I will address them directly or update the FAQ.


### Configuring Artpal


Navigate to the Artpal configuration page by logging into your Dashboard, clicking on "Settings", and then clicking on the "ArtPal" link. I recommend configuring the options on this page as follows:



	
  1. Scroll down to the "E-Commerce" section. The first option to configure is the email address that is linked to your PayPal account. **This is the account to which payments will be deposited, so check twice for typos!**

	
  2. The last E-Commerce option you need to configure is which PayPal button you would like to use. Select the option button next to the button of your choice.

	
  3. Scroll up to the "General Options" section. Select the category that will hold the artwork that you want to sell. **Any posts that you make in this category will be available for sale!**

	
  4. For now, leave the next option blank.

	
  5. In the third option, select the category that will hold the artwork that has already been sold. **Posts in this category will remain on your site for archival purposes, but will not be sold through ArtPal!**

	
  6. The next box holds the HTML that will be displayed when a visitor looks at a piece of art that has sold. You may use the default HTML or customize it to your liking.

	
  7. The next box holds the text that will be displayed to users alongside the PayPal button. The words "PRICE" and "SHIPPING" (case-sensitive) will be replaced with the item price and item shipping charges, respectively. You may use the default text or customize it to your liking.

	
  8. Leave the next option as is, for now.

	
  9. The next text box holds the message to display to a user if you are trying to sell a piece of artwork but have omitted its pricing information. By default it asks the user to contact you; again, you may change this to your liking.

	
  10. The last two text boxes are optional. The "URL of Thank You Page" allows you to enter the URL of a page that you would like to direct your users to after they have purchased your work. This can be a page on your blog or an external link to another web site.

	
  11. The "URL of Cancel Purchase Page" allows you to enter the URL of a page that you would like to direct your users to if they begin purchasing a work but do not complete the purchase or send payment. This can be a page on your blog or an external link to another web site.

	
  12. If you'd like to test your site using the PayPal sandbox, check that final box. Remember to switch it back before you go live!

	
  13. Scroll down to the bottom of the page and click "Update Options"




### Using ArtPal


To use ArtPal in one of your posts, follow these instructions:



	
  1. Create a new post as you normally would.

	
  2. Move the cursor to the position in the post at which you want your ArtPal content to appear. Type the following:

    
    [artpal=insert]


When your page is viewed, that text will be replaced by a PayPal button and the text that you have specified in the plugin settings.

	
  3. Scroll down to the bottom of the post editor page. You will see a blue bar labeled “Custom Fields.” Click the “+” icon on the right side of that bar.

	
  4. Set the price of your artwork by creating a custom field named “artpal_price”. For example, if you are selling a painting for $100, you will enter “artpal_price” in the _key_ field and “100″ in the _value_ field. Click “Add Custom Field” to save the data. This example is illustrated below.
[![](http://www.freerobby.com/wp-content/uploads/artpal-setprice1.png)](http://www.freerobby.com/wp-content/uploads/artpal-setprice1.png)

	
  5. Set the shipping price of your artwork the same way as you set the selling price, using the key “artpal_shipping”. In the example below, the shipping cost is $10.![](http://www.freerobby.com/wp-content/uploads/artpal-setshipping.png)


Your blog post is now ArtPal-ready, and it gets even easier after you’ve made your first post! Wordpress remembers the names of your custom fields, so the next time you add ArtPal content to a post, you can select your tags from a drop-down box instead of having to type them in. This is illustrated in the example below.

![](http://www.freerobby.com/wp-content/uploads/artpal-cfselection.png)





### FAQ


**ArtPal doesn't have as many features as other Wordpress e-commerce solutions. Why should I use it?**

Features come with a price: overhead, complexity and server resources. ArtPal is fast, easy to set up and use, and won't bog down your server. Why set up a whole workshop when all you need is a hammer?

**Can I use ArtPal to sell things besides artwork?**

Of course! The name comes from who it was written for, but anybody can use it!

**I have an idea to make ArtPal better. Will you consider it?**

Absolutely! But keep in mind that one of ArtPal's core aims is to be lightweight and easy to use!

**Do you have an issue tracking system set up where I can report bugs?**

Not at the moment, but I'm working on it. In the meantime, please report all issues as comments to this page so that I have them all in one place when I'm working on the next release.

**ArtPal is so helpful! Do you accept donations for your hard work?**

A typical donation is not going to change my lifestyle, but it might really help somebody else's. Please decide how much you'd like to give me, and then give that amount to the American Red Cross.
