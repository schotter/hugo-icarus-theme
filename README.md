The original Hugo Icarus theme has been unmaintained for years, and as Hugo upgraded, some features broke (such as front-page post listing, recent posts, and post counts). This version fixes such issues.


# Icarus

Icarus is a responsive and customizable theme for bloggers. It's a port of the same-named theme for [Hexo](file://hexo.io) made by [Ruipeng Zhang](https://github.com/ppoffice). Noteworthy features of this Hugo theme are the integration of a comment-system powered by Disqus, localization (l10n) support, syntax highlighting for source code and optional widgets for the sidebar.


## Get the theme

I assume you've Git installed. Inside the folder of your Hugo site run

```shell
$ cd themes
$ git clone https://github.com/schotter/hugo-icarus-theme.git
```

You should see a folder called `hugo-icarus-theme` inside the `themes` directory that we created a few moments ago. For more information read the official [setup guide](https://gohugo.io/overview/installing/) of Hugo.


## Setup

Next, navigate to the `exampleSite` folder at `themes/hugo-type-theme/exampleSite/`. In order to get your site running, you need to copy `config.toml` and all the content of all relevant subfolders such as `data/l10n.toml` into the root folders.

To turn the `exampleSite` folder in a standalone demo site the `themesDir` property has been set to `../..`. This way you can preview this theme by running `hugo server` inside `exampleSite` folder.

****Due to the customized `themesDir` path Hugo will fail to find themes if you copied the `config.toml` into the root directory of a regular Hugo website.**** Make sure you comment out the `themesDir` property if you use the theme in production.


## The config file

Now, let us take a look into the `config.toml`. Feel free to play around with the settings.


### Comments

The optional comment system is powered by Disqus. Enter your shortname to enable the comment section under your posts.

`disqusShortname = ""`

Tip: you can disable the comment section for a single page in its frontmatter:

```toml
disable_comments = true
```


### Menu

You can also define the items menu entries as you like. First, let us link a post that you've written. We can do this in the frontmatter of the post's content file by setting `menu` to `main`.

```toml
+++
menu = "main"
+++
```

Furthermore, we can add entries that don't link to posts. Back in the `config.toml` you'll find a section for the menus:

```toml
[[params.menu]]
    before = true
    label  = "Home"
    link   = "/"
```

Define a label and enter the URL to resource you want to link. With `before` you can decide whether the link should appear before ****or**** after all linked posts in the menu. Therefore, `Home` appears before the linked post.


### Sidebars

In order to use the full width of the website you can disable the profile on the left and / or the widgets on the right for a single page in the frontmatter:

```toml
+++
disable_profile = true
disable_widgets = true
+++
```


### Tell me who you are

This theme also provides a profile section on the left. Add your social network accounts to the profile section on the left by entering your username under `social`. The links to your account will be create automatically.


### Widgets

Beside the profile section you can add widgets on the right sidebar. The following widgets are available:

-   recent articles
-   category list
-   tag list
-   tag cloud

You can deactivate them under `params.widgets`:

```toml
[params.widgets]
    recent_articles = false
    categories = true
    tags = true
    tag_cloud = true
```


### Date line

The date line includes: post date, \* of words, approximate reading, time tags and categories. However, if you want certain pages to omit the date line, simply put `nodateline = true` in the front matter for that page.


### Disable Previous / next article links

To disable the inclusion of a previous/next article link at the bottom of the page, add `noprevnext = true` to the front matter. This feature, along with `nodateline` can be used to create standalone pages that are less "blog-like"


## Localization (l10n)

You don't blog in English and you want to translate the theme into your native locale? No problem. Take a look in the `data` folder and you'll find a file `l10n.toml` that we've copied at the beginning. It contains all strings related to the theme. Just replace the original strings with your own.


## Linking thumbnails

After creating a new post you can define a banner by entering the relative path to the image.

banner = "banners/placeholder.png"

This way you can store them either next to the content file or in the `static` folder.


## Mathematical equations

Mathematical equations in form of LaTeX or MathML code can be rendered with the support of [MathJax](https://www.mathjax.org). MathML works out of the box. If you're using LaTeX you need to wrap your equation with `$$`.

You can also print formulas inline. In this case wrap the formula only once with `$`.

If you don't need equations, you can disable MathJax but putting `disable_mathjax = true` in your config.toml. This will prevent clients from unnecessarily downloading the MathJax library.


### Gallery shortcode

This shortcode you to easily include a gallery into your pages. Copy the code below into your content file and enter the relative paths to your images.

{{< gallery "/banners/placeholder.png" "/banners/placeholder.png" "/banners/placeholder.png" >}}


## Nearly finished

In order to see your site in action, run Hugo's built-in local server.

$ hugo server

Now enter [`localhost:1313`](http://localhost:1313) in the address bar of your browser.


## License

This theme is released under the MIT license. For more information read the [license](https://github.com/digitalcraftsman/hugo-icarus-theme/blob/master/LICENSE.md).


## Acknowledgements

Thanks to

-   [digitalcraftsman](https://github.com/digitalcraftsman/hugo-icarus-theme) for the initial Hugo port of the Icarus theme
-   [Ruipeng Zhang](https://github.com/ppoffice) for creating this theme
-   [Steve Francia](file://github.com/spf13) for creating Hugo and the awesome community around the project
