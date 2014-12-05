---
title: Theme Setup
description: "Instructions on how to install and customize the modern Grav theme HPSTR."
image:
  feature: abstract-11.jpg
  credit: dargadgetz
  creditlink: http://www.dargadgetz.com/ios-7-abstract-wallpaper-pack-for-iphone-5-and-ipod-touch-retina/
share: true
comments: false
---

This theme is a port of the [Jekyll HPSTR Theme](https://github.com/mmistakes/hpstr-jekyll-theme) developed my [mmistakes](https://mademistakes.com/)

## Basic Setup for a new Grav site

The simplest way to install HPSTR theme for Grav is to download and install the HPSTR Skeleton package:

1. [Download HPSTR Skeleton](http://getgrav.org/downloads/skeletons#extras)
2. Simply unzip the package into your web root folder.
3. Point your browser at the folder, job done!

<div markdown="0"><a href="http://getgrav.org/downloads/skeletons#extras" class="btn">Download the Skeleton</a></div>

**TIP:** Check out the [general Grav installation instructions](http://learn.getgrav.org/basics/installation) for more details on this process.

---

## Existing Grav site

It is possible to install just the theme, but page content will need to reference the HPSTR theme's supported templates.  It is strongly advised to at least install the HPSTR Skeleton package to see the theme's capabilities in action.

To install  **just** the theme:

```
$ bin/gpm install hpstr
```

---

## Configuration

Most of the configuration of the theme is done in the `user/config/site.yaml` file:

```
title: Site Title
description: Describe your website here.
taxonomies: [tags]
disqus_shortname: hpstrtheme
owner:
  name: Joe Bloggs
  email: 'joe@test.com'
  avatar: avatar.jpg
  bio: "Your bio goes here. It shouldn't be super long but a good two sentences or two should suffice."
  # Social networking links used in footer. Update and remove as you like.
  twitter: yourid
  facebook:
  github:
  stackexchange:
  linkedin:
  instagram:
  flickr:
  tumblr:
  # For Google Authorship https://plus.google.com/authorship
  # google plus id, include the '+', eg +mmistakes
  google_plus: +yourid

metadata:
    description: 'Grav is an easy to use, yet powerful, open source flat-file CMS'

navigation:
    - title: Theme Setup
      url: /theme-setup
    - title: External Link
      url: http://getgrav.org
```

Most of these options are self explanatory, but there are some important things to know.

### Disqus Comments

Create a [Disqus](http://disqus.com) account and change `disqus_shortname` in `site.yaml` to the Disqus *shortname* you just setup. By default comments appear on all post and pages if you assigned a shortname. By adding the shortname, you are effectively enabling comments on all blog posts.

To disable commenting on a post or page, add the following to its YAML Front Matter:

```
comments: false
```

### Social Share Links

If you provide social sharing account ids, you effectively enable sharing for that service.

To disable Facebook, Twitter, and Google+ share links on a post or page, add the following to its front matter:

```
share: false
```

### Owner/Author Information

Change your name, and avatar photo (200x200 pixels or larger), email, and social networking URLs. If you want to link to an external image on Gravatar or something similar you'll need to edit the path in `user/themes/hpstr/templates/partials/navigation.html.twig` since it assumes it is located in `/images`.

Including a link to your Google+ profile has the added benefit of displaying [Google Authorship](https://plus.google.com/authorship) in Google search results if you've went ahead and applied for it.

### Google Analytics and Webmaster Tools

Your Google Analytics ID goes here along with meta tags for [Google Webmaster Tools](http://support.google.com/webmasters/bin/answer.py?hl=en&answer=35179) and [Bing Webmaster Tools](https://ssl.bing.com/webmaster/configure/verify/ownershi) site verification.

### Navigation Links

To add additional links in the drop down menu edit the navigation section in the `site.yaml`. Use the following format to set the URL and title for as many links as you'd like. *External links will open in a new window.*

```
navigation:
    - title: Theme Setup
      url: /theme-setup
    - title: External Link
      url: http://getgrav.org
```

---

### Reading Time

This functionality is provided by the [ReadingTime plugin](https://github.com/nunopress/grav-plugin-readingtime).  Reading time is enabled by default. You can configure the plugin via it's own options or just disable it if you don't wish to use it.

### Related Pages

The related pages that show at the bottom of each blog post is powered by the [RelatedPages plugin](https://github.com/getgrav/grav-plugin-relatedpages).  This is a powerful Grav plugin that provides flexible and customizable related page calculations.

### Syntax Highlighting of Code

Code blocks are automatically syntax-highlighted via the Grav [Highlight plugin](https://github.com/getgrav/grav-plugin-highlight).  It has it's own configuration that enable you to choose a theme, or even disable it on a page where you don't need it.

### Feature Images

A good rule of thumb is to keep feature images nice and wide so you don't push the body text too far down. An image cropped around around 1024 x 256 pixels will keep file size down with an acceptable resolution for most devices.

The two layouts make the assumption that the feature images live in the *images* folder. To add a feature image to a post or page just include the filename in the front matter like so.

```
image:
  feature: feature-image-filename.jpg
  thumb: thumbnail-image.jpg #keep it square 200x200 px is good
```

If you want to apply attribution to a feature image use the following YAML front matter on posts or pages. Image credits appear directly below the feature image with a link back to the original source.

```
image:
  feature: feature-image-filename.jpg
  credit: Michael Rose #name of the person or site you want to credit
  creditlink: http://mademistakes.com #url to their site or licensing
```

#### Post/Page Thumbnails for OG and Twitter Cards

Post and page thumbnails work the same way. These are used by [Open Graph](https://developers.facebook.com/docs/opengraph/) and [Twitter Cards](https://dev.twitter.com/docs/cards) meta tags found in `head.html`. If you don't assign a thumbnail the image you assigned to `site.owner.avatar` in `_config.yml` will be used.

Here's an example of what a tweet to your site could look like if you activate Twitter Cards and include all the metas in your post's YAML.

**TIP:** For more information please check out the [Meta Page Headers](http://learn.getgrav.org/content/headers#meta-page-headers) section of the documentation.

![Twitter Card summary large image screenshot](twitter-card-summary-large-image.jpg)

### Videos

Video embeds are responsive and scale with the width of the main content block with the help of [FitVids](http://fitvidsjs.com/).

```
<iframe width="560" height="315" src="http://www.youtube.com/embed/PWf4WUoMXwg" frameborder="0"> </iframe>
```

### Twitter Cards

Twitter cards make it possible to attach images and post summaries to Tweets that link to your content. Summary Card meta tags have been added to `head.html` to support this, you just need to [validate and apply your domain](https://dev.twitter.com/docs/cards) to turn it on.

### Link Post Type

Link blog like a champ by adding `link: http://url-you-want-linked` to a post's YAML front matter. Arrow glyph links to the post's permalink and the the `post-title` links to the source URL. Here's an [example of a link post](/blog/sample-link-post) if you need a visual.

---

## Further Customization

To customize the CSS, you will need to use a SASS compiler as the CSS source is provided in `.scss` files.

By editing values found in the theme's `_sass/variables.scss` you can fine tune the site's colors and typography.

For example if you wanted a red background instead of white you'd change `$bodycolor: #fff;` to `$bodycolor: #cc0033;`.

To modify the site's JavaScript files I setup a Grunt build script to lint/concatenate/minify all scripts into `scripts.min.js`. [Install Node.js](http://nodejs.org/), then [install Grunt](http://gruntjs.com/getting-started), and then finally install the dependencies for the theme contained in `package.json`.

---

## Questions?

Having a problem getting something to work or want to know why I setup something in a certain way? Ping us on Twitter [@getgrav](http://twitter.com/getgrav) or [file a GitHub Issue](https://github.com/getgrav/grav-theme-hpstr/issues/new).

---

## License

This theme is free and open source software, distributed under the [MIT License](/LICENSE) version 2 or later. So feel free to to modify this theme to suit your needs.

