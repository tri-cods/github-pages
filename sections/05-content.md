# Adding Content 

In this section we'll explore a few crucial files that you can use to change settings in your GitHub Pages site, and then go over how to add a theme to make your site more attractive. Then, we'll discuss how to add different types of content using markdown.

## Files

### Index

The default main file of a static website is called "index.html". This document is generated for your github pages site as part of the build process. As we've seen, it currently pulls content from README.md to build that page. But what if you wanted to your README for its original purpose -- to document your project -- rather than as your home page? This is why it's good to create an "index.md" file: if you have one, that will automatically be used to build your main page. 

```md
## Welcome to my home page

Here you can find lots of useful information
```

### Config

Another crucial file to add to your site is the `config.yml` file: it's a metadata file written in the YAML markup language. The config.yml file includes crucial settings and metadata for your website, such as title, author, description, theme, and many more options. The `.yml` file extension indicates that the config.yml file is in the [YAML](https://yaml.org/) markup language. Understanding a few of these settings and how to add them can let you do a lot of customization.

An example of settings in `config.yml`

```yaml
title: Axolotl # The top-level website title
description: The story of an adorable aquatic creature # A tagline that usually appears in your site header

remote_theme: pages-themes/cayman@v0.2.0 # Establishes a theme
plugins:
- jekyll-remote-theme
```


### Themes

GitHub Pages sites are highly extensible, meaning that they are infinately customizable, but many customizations require some coding ability. Fortunately, there's a large community of developers creating and sharing open-source themes for Jekyll and GitHub Pages: website templates with layouts, stylesheets, and features that you can use for your site by adding a few lines of YAML to your  `_config.yml` file. There are hundreds of options for Jekyll themes, including several designed specifically for digital scholarship projects:


- [Collection Builder](https://collectionbuilder.github.io/): a minimal digital exhibit builder featuring data visualizations
- [Ed](https://minicomp.github.io/ed/): for digital editions and textual editing
- [Wax](https://minicomp.github.io/wax/): a digital exhibit template

Every theme has different documentation and some take longer to set up than others: for simplicity's sake, we recommend using one of [these themes supported by GitHub Pages](https://pages.github.com/themes/) while you're getting started. 


### Activity: Add an Index and a Config

#### Add an Index.md

- From the main page of your repository, use the `+` button to "Create a new file".

<img src="../static/add-file.png" alt="Add a new file to your repository" width="40%"/>

- Be sure to name your file `index.md`!

<img src="../static/index.png" alt="Creating index.md file"/>

- Create a header on this page using a hashmark at the beginning of the line: `# Hello, world!` Then, add some additional text to the document. Need some placeholder text? Check out [Lit Ipsum](https://litipsum.com), a site that generates placeholder text text from a selection of public-domain British novels, or use the classic [Lorem Ipsum](https://www.lipsum.com/) passage exemplum from the early days of the printing press.

- Commit your changes and add a brief message about your edit.

#### Add a Config.yml

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

## Content

### Adding images

### Adding pages

### Activity: adding content to your site

1. Find one or two images you'd like to link to or add to your site.

2. Build out the content of your site by editing `index.md`. Use markdown syntax to add headers, images, lists, and links -- refer to our [markdown guide](../more/markdown.md) 

3. Create a new page for your site by adding a new markdown file to your repository. Create links to help you navigate between pages.

[<<<Back](04-how.md) | [Next>>>](06-customize.md)