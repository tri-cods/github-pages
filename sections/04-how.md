# How it Works

GitHub Pages is a service that takes HTML, CSS and JavaScript files from a repository and builds a site out of them. The image below, created by Kyle Meagher and posted at their vlog titled ["Static Site Generators Explained in 5 minutes"](https://www.cosmicjs.com/blog/static-site-generators-explained-in-5-minutes) is a good representation of the process GitHub Pages uses to build the site

<img src="../static/static-process.png" alt="static site process">

Remember the previous section where you where waiting for the dot to turn green?

<img src="../static/progress-check.png" alt="view status of jekyll build" width="40%">
 
this is where the cogs (SSG) where turning, taking content, data and code to create a static site hosted by GitHub. 

To understand the significance of this process, let's take a brief look at the history of web design

## A brief history

Part of understanding why we use the tools and standards for web design today involves understanding how web design started, its evolution and why developers have returned to using static sites.

### First website
![Screenshot of the first ever website](https://raw.githubusercontent.com/tri-cods/html-css/main/sections/images/first.png)

This site, created on August 23, 1991, was and is a static site. This site is made up of a single HTML file. Any page on a static site is made up of an HTML file. What you see on a static site is the same as what I see on the same static site.

### Dynamic 
![Image of first version of wordpress](https://cdn4.wpbeginner.com/wp-content/uploads/2018/07/wordpress-firstrelease-1.png)

The era of dynamic sites brought about sites that generate content "on-the-fly", usually based on user behaivor. Content lives on a database and is updated and displayed as you navigate the site. In other words, in contrast to a static site, what you see is dynamically updated based on the time of day (think of news sites) or user-generated conente (think of social media). 

## Static vs Dynamic

If static sites are made up of single HTML files, what happens when you have to update a feature that appears in each of the files, for example the color of your background? In a dynamic site, this information lives in a database. So, to change the color of your background, just click and pick a color and the change will apply to the whole site

![Image of wordpress styling section](/static/wordpress.png)

For static site, it used to be the case that you would have to make this change on each single HTML file. For a site that contains two or three files, this would be no issue but what if a site has 100s of pages like ESPN.com or CNN.com? Static site generators to the rescue! 

Let's see how we can use GitHub Pages to customize our site without having to edit each single page...

[<<<Back](03-deploy.md) | [Next>>>](05-customize.md)