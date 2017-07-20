---
layout: post
title:  "How to set up jekyll in Mac OS"
date:   2015-03-02 11:09 pm
---

Bought a new computer recently. And trying to set it up my old blog repository.

The instruction on Jekyll website is straight forward. Install with an easy command line and you are done.

However, when I tried to run this command in my Mac terminal, it failed serval time. The error message is:

 **Operation not permitted - /usr/bin/jekyll**

This error is caused by Apple's System Integrity Protection. Old ruby gem didn't handle it well.

[Jekyll support document](http://jekyllrb.com/docs/troubleshooting/#jekyll-amp-mac-os-x-1011) gives us two solutions. 

The first one is install jekyll with a more complex command line, which is not working for me. 

The second solution do give me a clue about installing luby using homebrew.
 It turns out, homebrew will install a very latest version of ruby.
  After installing this very latest ruby, I updated my gem with: 

```shell
sudo gem update --system
```

This command runs smoothly. But when I tried to run 

```shell
jekyll serve
```
It gives me another error message about missing paginate and pygments.
Solution to this is pretty straight forward, install them:

```shell
sudo gem install jekyll-paginate
sudo gem install pygments.rb
```

*Note:* all commands start with sudo will require a super user privilege. 
