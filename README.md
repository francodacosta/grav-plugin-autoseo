# [Grav](http://getgrav.org) AutoSEO

This is the new home of Auto SEO. I tried to contact the original author (Laurent), but the email bounced back.

Grav Auto SEO is a plugin for Grav with which you can fill automatically the description and keywords metadata of a page using its content.

It also adds Facebook Open Graph metadata and Twitter Cards Meta Tags (**New** feature since the 1.2 version).

If the plugin is enabled and **the description and keyword metadata of the page are not manually filled** (i.e. the page headers contains some metadata fields), the plugin will use the first words of the page summary to fill the description and its categories and tags to fill the keyword metadata. Facebook and twitter metadata will also be filled if they are enabled in settings and not manually filled in the page header.

## Installation

### Manual Installation

To install this plugin, just download the zip version of this repository and unzip it under `/your/site/grav/user/plugins`. Then rename the folder to `autoseo`.

You should now have all the plugin files under `/your/site/grav/user/plugins/autoseo`

## Configuration

Here is the default configuration and an explanation of available options:

`autoseo.yaml:`

```yaml
enabled: true # lets you turn the plugin off and on.
title:
  append_site_title: false # lets you turn the plugin off and on for the "title" metadata.
  separator: '|' # text that separates the page title from the site title in the "title" metadata.
description:
  enabled: true # lets you turn the plugin off and on for the "description" metadata.
  length: 30 # maximal number of words that will be used to fill the "description" metadata.
keywords:
  enabled: true # lets you turn the plugin off and on for the "keywords" metadata.
  length: 20 # maximal number of words that will be used to fill the "keywords" metadata.
facebook:
  enabled: true # Lets you turn the plugin ON and OFF for the "Facebook Open Graph" metadata.
twitter:
  enabled: true # Lets you turn the plugin ON and OFF for the "Twitter Cards" metadata.
```

If you need to change any value, then the best process is to copy the `autoseo.yaml` file into your `users/config/plugins/` folder (create it if it doesn't exist), and then modify there. This will override the default settings.

## Per-Page Configuration

If you want to alter the settings for one or a few pages only, you can do so by adding page specific configurations into your page headers:

```yaml
autoseo:
  enabled: true
  description:
    enabled: true
    length: 10
  keywords:
    enabled: true
    length: 10
  facebook:
    enabled: true
  twitter:
    enabled: false
```

## Usage

There's not much to do with this plugin, simply install, enabled it and check its configuration to meet your needs.

No need to do anything else.

### Performance

As each page must be analyzed and its content filtered by the plugins, the impact on performance can be important when first access to a page.
But as the result will be cached, once the first analysis is done, you will find no further negative performance impact.

To limit the impact on performance, **the content analyzed will always be truncated to the 1000 first characters for description metadata**, then the limit given by the `length` setting will be applied.

### Notes

`Auto SEO` will make a few cleaning but won't check the content used to auto fill the metadata.
So be sure that the first words of your content (the summary) will be correct to be used as a description.
In a same way, check that the tags and categories of the page are OK to be used as keyword.

### Bugs And TODO

Please send any comments or bug reports to the plugin's [issue tracker](https://github.com/francodacosta/grav-plugin-autoseo/issues).

#### TODO

* No new feature is planned for the moment.

### Authors

`Auto SEO` was developed and maintained by Laurent Ongaro and is now looked after by Nuno Costa.
