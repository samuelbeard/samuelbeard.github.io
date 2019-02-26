---
layout: post
title: "Eight things to add to your website before it goes live."
published: true
tags: [resource, list]
bigimg: /img/eight-things-to-add-to-your-website/feature.png
---

## 1. Android Address Bar Colour
Android users may notice that when visiting some websites on your phone of tablet, the address bar reflects the branding colour of the site you are on. This is a neat little feature that gives your site a more integrated, ‘web app’ feel.

![coloured address bar](/img/eight-things-to-add-to-your-website/one.png?raw=true)

To add this, just use a meta tag like this:

```html
<meta name="theme-color" content="#ff3300" />
```

Thought it has no actual use. It greatly increases the experience a user has on your site. And it is easy to implement.

## 2. Alt Tags
Alt tags on images have two main uses. They help people who can’t see well to understand what is in the image. And they help search engines index the images.

In an alt tag, use text that fulfils the same function as the image. Describe the image’s function to the page as opposed to just describing the image itself. For example, say you had a window with a stylised image of an ‘X’ in the top right to close it. Instead of the alt tag reading ‘An x’, say ‘close window’.

## 3. Meta Tags
Meta tags can organise the content on the page so that companies like Google and Facebook can display it well on their own sites. Google can display more information about your site from a search query. You can choose what information is displayed when someone links to your site on Facebook.

Some useful meta tags:

```html
<!-- Description -->
<meta name=”description” content=”A description of the page. 155 characters long or less.”>

<!-- Author -->
<meta name="author" content="Samuel Beard">

<!-- Display well on Facebook -->
<meta property=”og:title” content=”Title on Facebook”/>
<meta property=”og:type” content=”article”/>
<meta property=”og:image” content=”image.jpg”/>
```
[Twitter uses a similar way to tweet cards.](https://dev.twitter.com/cards/overview)

Don’t use the keywords or copyright meta tags as they are now obsolete.

## 4. robots.txt and humans.txt
Robots.txt is a file that you would put in the root directory of your site to tell automatic web crawlers (Like Google indexing your website) how to index your site. You can stop the crawlers from indexing certain directories.

[Google has a lot of information of robots.txt.](https://support.google.com/webmasters/answer/6062608?hl=en&ref_topic=6061961)

Humans.txt is not as well known as robots.txt but is always nice to have. Humans.txt is basically the credits of your website. In this document, you credit the people who helped build it. Putting ‘Site build by’ in the footer is a bit tacky nowadays so this is great way to get credit for your work.

[Here is a site with information about humans.txt.](http://humanstxt.org/)

## 5. Replace CDN Links
When building the site, you may have linked to a CDN or two to import libraries like jQuery or some CSS. Though this is ok (Depending on the CDN source.) it does add another point of failure to your site. Especially if that link gets updated and breaks your site in some way.

Download the libraries and put them on your server with the site. That way, your site will always work just like your built it.

## 6. Speed Test the Site
Once everything is up and running on the server, use Google’s [PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/) to improve its load speed. This will give you loads of suggestions on how to speed up your site including minifying JavaScript and compressing images.

Aim to at least complete the ‘Should Fix:’ suggestions for mobile *and* desktop. There are usually the things that slow your site the most.

## 7. Favicons and App Icons
Different devices and software display an icon for your site in slightly different ways. It is a good idea to have optimised icons for each of the most common ways. Some of the common ways people will see the icon is on the tab in the browser or as an app icon on their phone.

![favicon and app icon](/img/eight-things-to-add-to-your-website/two.png?raw=true)

[This site generates all the sizes you will need from one image file that you upload.](http://www.favicon-generator.org/)

## 8. Submit for Indexing
Although Google and other search engines will eventually index your site. You can submit it yourself once it is online to get the ball rolling.

Use [Google’s Webmaster Tools](https://www.google.com/webmasters/tools/home?hl=en) to see how your site will do on Google Search.

[Here is where you can submit your site to Bing because some people actually use it.](http://www.bing.com/toolbox/submit-site-url)

---

I hope this list has been helpful to you. If there is anything I have missed or made a mistake, feel free to let me know on Twitter [@_SamueBeard](https://twitter.com/_SamuelBeard).
