---
layout: post
title:  "Notes For Jekyll Starters"
categories: fold jekyl
---



# Setting up

Jekyll is written in Ruby so install it with gem. See what you already have installed / check your versions.
```terminal
ruby -v
gem -v
```
Install Jekyll:
```terminal
gem install jekyll bundler
jekyll -v
 ```

Create your first Jekyll projectad go into the created folder
```console
jekyll new my_blog
cd my_blog
```

Jekyll will create a server so you can see the web pages:
```terminal
bundle exec jekyll serve
````

Note that subsequently to run Jekyll, you only need to type:
```
jekyll serve
````


# Project Structure

* _posts - your posts - change stuff here
   * Put files in the _post folder
   * These can be .md or .html
* _site - this is generated, don't touch it
* _config.yml - setup stuff - if you change this, restart jekyll


# Front matter (aka meta-info at the top of pages)

* At the top of all pages
* defaut values can be set in the _config.yaml file
* starts and ends with 3 dashes
```yaml
---
title: fred
layout: [post | page]
permalink: /about/
permalink: /:categories/:year/:month/:day/title
---
```
* permalink
   * allows you to define the url path
   * by default it's
   ```yaml
   permalink: /:categories/:year/:month/:day/title
   ```
   ... so no need to write that
   * can add bits like :
   ```yaml
   permalink: /:categories/:year.html
   ```
   * good to define a permalink for the blogs - in case change category accidentally for example

Default values for the Front Matter is set in the _config.yaml file.
then you don't have to put the same stuff at the top of all pages (for exape laout: post)
```yaml
# custom front matter
defaults:
  -
    scope:
      path: "" # an empty string here means all files in the project
      type: "posts" # to only apply these defauts to the "_post" folder pages
    values:
      layout: "post"
      title: "My Title"   # not useful for the tile in fact...

```

# Draft files

* make a folder called _drafts
* put a file in it (no need to give it a date-prefix)
* it won't be visible on the generate _site folder
* to see it: run the server: jekyll serve --draft
* it will take the latest update date
* when it's ok, move it to the _posts folder

# Page types

* Normal pages
   * For example About page
   * these **do not** show up in your posts
* Blog posts


# Non-blog pages

* in the _Front matter_ no date is necessary
* Put the files in a sub-folder if you want - Jekyll will find them


# Themes
Check what theme you have - it's in the _config.yaml file. I's probably:
```
   theme: minima
```
