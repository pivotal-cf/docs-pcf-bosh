## <a id='overview'></a>Overview

This repo contains the documentation for PCF BOSH. The repo contains the following folders:

* `docs-book`: The configuration and subnav for the book.
* `docs-content`: The content for the book, in Markdown files.
* `docs-layout`: The layout for the book, including stylesheets, fonts, and images.

## <a id='locate'></a>Locate the Topics and Subnav

Edit the individual topics in the [`docs-content`](https://github.com/pivotal-cf/docs-pcf-bosh/blob/master/docs-content) folder.

Edit the subnav at [`docs-book/master_middleman/source/subnavs/pcfbosh_subnav.erb`](https://github.com/pivotal-cf/docs-pcf-bosh/blob/master/docs-book/master_middleman/source/subnavs/pcfbosh_subnav.erb)

## <a id='bookbinder'></a>Use Bookbinder To View and Publish Docs

[Bookbinder](https://github.com/pivotal-cf/bookbinder/blob/master/README.md) is a command-line utility for stitching Markdown docs into a hostable web app.

Install Bookbinder by running `gem install bookbindery`.

You can use Bookbinder to 
* [View](#view) a live version of these docs on your local machine while editing.
* [Publish](#publish) your documentation changes.

### <a id='view'></a> View Docs

To use Bookbinder to view your documentation, perform the following steps:

1. Clone this repo to your local machine.
1. On your local machine, `cd` into `docs-book` in the cloned repo.
1. Run `bundle install` to make sure you have all the necessary gems installed.
1. Run `bookbinder watch` to build an interactive version of the docs and navigate to `localhost:4567/myservice/` in a browser. (It may take a moment for the site to load at first.) This builds a site from your content repo at `docs-content`, and then watches that repo to update the site if you make any changes to the repo.

### <a id='publish'></a> Publish Docs

1. On your local machine, `cd` into `docs-book` in the cloned repo.
1. Run `bookbinder bind local` to build a Rack web-app of the book. 
1. `cd` into the `final_app` directory.
1. Run `cf push pcfbosh`. You must be logged in to PWS and be targeting the correct org and space.

After the push command has completed, view the docs at https://pcfbosh.cfapps.io. 
