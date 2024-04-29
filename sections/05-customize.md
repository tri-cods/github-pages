[<<<Back](04-how.md) | [Next>>>](06-resources.md)

# Customizing your GitHub Pages Site

In this section we'll explore a few crucial files that you can use to change settings in your GitHub Pages site, and then go over how to add a theme to make your site more attractive. 

## Index

The default main file of a static website is called "index.html". This document is generated for your github pages site as part of the build process. As we've seen, it currently pulls content from README.md to build that page. But what if you wanted to your README for its original purpose -- to document your project -- rather than as your home page? This is why it's good to create an "index.md" file: if you have one, that will automatically be used to build your main page.

### Activity: add an index.md

From the main page of your repository, use the `+` button to "Create a new file".

<img src="../static/add-file.png" alt="Add a new file to your repository" width="40%"/>

Be sure to name your file `index.md`!

<img src="../static/index.png" alt="Creating index.md file"/>

Create a header on this page using a hashmark at the beginning of the line: `# Hello, world!` Then, add some additional text to the document. Need some placeholder text? Check out [Lit Ipsum](https://litipsum.com), a site that generates placeholder text text from a selection of public-domain British novels, or use the classic [Lorem Ipsum](https://www.lipsum.com/) passage exemplum from the early days of the printing press.

Commit your changes and add a brief message about your edit.

## Config

Another crucial file to add to your site is the `config.yml` file: it's a metadata file written in the YAML markup language. The config.yml file includes crucial settings and metadata for your website, such as title, author, description, theme, and many more options. The `.yml` file extension indicates that the config.yml file is in the YAML markup language.

### What is YAML? 

Like Markdown, YAML (which allegedly stands for [YAML Ain't Markup Language](https://yaml.org/)) is designed to be both human-readable and machine readable. in YAML, attributes and values are expressed using a simple colon and a space, for example: 

```YAML
title: Axolotl
description: The story of an adorable aquatic creature
```

The attribute `title` has the value `Axolotl`. 

If you compare this to HTML, you can start to see why languages like YAML and Markdown were developed.

```html
<head>
    <title>Axolotl</title>
    <meta name="description" content="The story of an adorable aquatic creature">
</head>
```

## Themes

GitHub Pages sites are highly extensible, meaning that they are infinately customizable, but many customizations require some coding ability. Fortunately, there's a large community of developers creating and sharing open-source themes for Jekyll and GitHub Pages: website templates with layouts, stylesheets, and features that you can use for your site by adding a few lines of YAML to your  `_config.yml` file. There are hundreds of options for Jekyll themes, including several designed specifically for digital scholarship projects:

- [Collection Builder](https://collectionbuilder.github.io/): a minimal digital exhibit builder featuring data visualizations
- [Ed](https://minicomp.github.io/ed/): for digital editions and textual editing
- [Wax](https://minicomp.github.io/wax/): a digital exhibit template

Every theme has different documentation and some take longer to set up than others: for simplicity's sake, we recommend using one of [these themes supported by GitHub Pages](https://pages.github.com/themes/) while you're getting started. 

### Activity: add a theme

- From the main page of your repository, use the `+` button to "Create a new file". 

<img src="../static/add-file.png" alt="Add a new file to your repository" width="40%"/>

- Name this new file `_config.yml` -- and don't forget to include the underscore!

- Start by adding a site title and description:

```yaml
title: Your site title
description: A short tagline for your site
```

- Next, add your theme. we'll start with the [Cayman Theme](https://pages-themes.github.io/cayman/), one of the GitHub Pages supported themes. Here's the GitHub repository with documentation for Cayman: https://github.com/pages-themes/cayman
- Copy and paste the following into your config file:

```yaml
remote_theme: pages-themes/cayman@v0.2.0
plugins:
- jekyll-remote-theme
```

- Finally, **commit your changes**: don't forget to add a commit message!

- Be patient as you wait for your site to re-build. 

### What's in a theme?

What exactly does adding a theme do? The `remote_theme` variable in your config file tells GitHub pages where to look for the files that govern the structure and style of your site. Then, it plugs your content (from Markdown and YAML) into the theme's variables, and builds the website. Because these themes are all open source on GitHub, you can see exactly how your theme works by going to the GitHub repository for Cayman: https://github.com/pages-themes/cayman. It may be a little overwhelming at first, but once you get oriented, you can use these files to customize your site even further.

### Style

While HTML provides the core structure of most web pages, the style (including color, size, font, shape, and how the look changes on different screen sizes) is governed by another language called **CSS** or Cascading Style Sheets. Jekyll uses a slightly different version of CSS called SCSS. You'll find these files in the `_sass` folder, which has a lot going on. 

Fortunately, Cayman offers simplified instructions for adding your own [Stylesheet](https://github.com/pages-themes/cayman/tree/master?tab=readme-ov-file#stylesheet), so you can customize your color scheme, fonts, layout, and a variety of other features.

### Activity: Adding a custom stylesheet

- From the main page of your repository, use the `+` button to "Create a new file". 
  
- In the title field, type the name `/assets/css/style.scss`

- Add this content to your file -- feel free to copy and paste so the content is identical:

```scss
---
---

@import "{{ site.theme }}";

```

- Below the `@import` line, add some custom CSS. Need inspiration? Start by changing the color of your heading text:

```css

h1 {
    color: pink;
}

h2 {
    color: yellow;
}

```

- Make sure the filename and first 4 lines look like this:

<img src="../static/stylesheet.png" alt="adding stylesheet demo" width="100%"/>

- Commit your changes with a message explaining what you've done.

### Structure

As we discussed in the last section, the version of your website that you see is an HTML file that is built using your content and the Cayman theme's structure and style. We've seen how to add content to your site via the markdown file, as well as how to add an additional stylesheet that will override the stylesheet built into the theme. But what if you want to change something in the HTML itself -- such as the links in the heading? Well, this is when understanding the structure of your theme comes in handy. Let's take a look.

In the Cayman theme, like many other Jekyll themes, most of the HTML is found in the`_layouts` folder. In this case, there's only one layout: `default.html`. This file sets the basic structure of each page in your site. If you've seen HTML before, you might notice that this file looks a little different: that's because it also uses a language called [Liquid](https://shopify.github.io/liquid/). That is how the YAML variables you add to your pages and your config file get plugged in to the layout. 

You'll notice at line 30, that there's a variable called `content`

```html
    <main id="content" class="main-content" role="main">
      {{ content }}
```

This variable represents the body of your markdown file, so everything you add as markdown will go here. 

When GitHub Pages builds your site, it starts by looking at your repository for specific settings, metadata, and content. Then it looks to your theme for anything it doesn't find. So in order to edit the default layout, all you need to do is copy this `default.html` file into your repository in the place where it's expected, and make any changes you want.

### Activity: editing the layout template

- In your Pages repository, use the `+` button to create a new file
- Give the file the name `_layouts/default.html` (this will create a folder in your repository called `_layouts`)
- In a new tab or browser window, navigate to the [default layout file in Cayman](https://github.com/pages-themes/cayman/blob/master/_layouts/default.html)
- Click 'Copy raw file' to copy the full contents of `default.html`

<img src="../static/copyraw.png" alt="copy raw contents" width="30%"/>

- Return to your Pages repository and paste the contents into the editor window.

- Any changes you make to this file will be reflected on your home page when your site is built. Say I wanted to add my full name and the date to the footer. I can do this by editing line 37 -- instead of:

```html
<span class="site-footer-credits">This page was generated by <a href="https://pages.github.com">GitHub Pages</a>.</span>
```

I could change it to:

```html
<span class="site-footer-credits">This page was created by Alice using <a href="https://pages.github.com">GitHub Pages (2024)</a>.</span>
```

- Once you've made a change, remember to add a message before committing your changes.

## The GitHub code editor



## Activity: customizing your site

- Add an index.md file and add text and images using Markdown
- Create a _config.yml file and add a theme
- Edit your site title and tagline
- Customize the theme using HTML and CSS

[<<<Back](04-how.md) | [Next>>>](06-resources.md)