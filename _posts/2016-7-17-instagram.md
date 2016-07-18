---
layout: post
title: Instagram API Got You Down?!
---

Sick of tokens? Now your app needs to be approved? Just to get links to a
bunch of images that are publicly available anyway?

Not necessary! A web page IS an API.  All you need is watir and phantomjs.

```ruby
# create a headless browser
b = Watir::Browser.new :phantomjs

uri = 'https://www.instagram.com/explore/tags/cats'
b.goto uri

# all data are stored on this page-level object.
o = b.execute_script( 'return window._sharedData;')

b.close
```
