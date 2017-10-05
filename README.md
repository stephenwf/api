[![Stories in Ready](https://badge.waffle.io/IIIF/api.png?label=ready&title=Ready)](https://waffle.io/IIIF/api)
[![Build Status](https://travis-ci.org/IIIF/api.svg?branch=master)](https://travis-ci.org/IIIF/api)

# Specifications

Markdown Source of specifications documents

## To Debug the Site

 1. `bundle install`

 2. Run `rake dev` to compile the site and run a dev server on [http://localhost:4000](http://localhost:4000).

## To Run the Tests

 1. `bundle install`
 2. Install grunt `npm install -g grunt-cli`
 3. Install grunt dependencies `npm install`
 4. Run ```rake ci```

## To Publish the Site to iiif.io

Branches are available at http://preview.iiif.io/api/[branch_name]/api/index.html. The master branch is automatically loaded to the iiif.io website.

## Some Things to Note

 * Much of the site data is in the YAML files in `_data/` (e.g. member institutions, server impls, demos, etc.) make edits there.
 * The latest versions of the APIs are set in `_config.yml`. Change there will get pushed to `.htaccess`, `technical-details/`, and any other links.
 * The website is now split with the specification website living here and the main website living in [IIIF/website](https://github.com/IIIF/website). Links internal and external should be in the following forms:
    * Internal relative link inside the API website `[hyperlink text]({{ site.url }}{{ site.baseurl }}/end/point)`
    * link from the API website to the main website (not relative to this repo) `[hyperlink text]({{ page.webprefix }}/end/point)`
    * External link `[anchor-text](http://example.com/end/point)`
    * Reference link `[text][link_name]` where link_name is expanded at the bottom of the page.
