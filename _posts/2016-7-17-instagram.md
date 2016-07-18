---
layout: post
title: Instagram API Got You Down?!
---

I'm sure there are some good reasons to use the Instagram API, under some circumstances.  But, if your app just needs to get a list of images, there is a much easier way.

You don't need to mess with tokens, or getting your app approved by Instagram, or having a publicly facing page.  All you need is watir and phantomjs.

```ruby
# create a headless browser
b = Watir::Browser.new :phantomjs

uri = 'https://www.instagram.com/explore/tags/cats'
b.goto uri

# all data are stored on this page-level object.
o = b.execute_script( 'return window._sharedData;' )

b.close
```

The data are nicely structured.  You can construct click-through links using the 'code' attribute.  You can retrieve additional pages using the 'end_cursor' attribute.
