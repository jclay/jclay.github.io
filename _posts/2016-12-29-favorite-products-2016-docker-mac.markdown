---
layout: post
title:  "Favorite products from 2016 - Docker for Mac"
date:   2016-12-29
---

## Docker for Mac

Docker for Mac, the new iteration of the Docker Toolbox feels incredibly polished and easy to use. The out of the box experience is more begginer friendly and native feeling than Docker Toolbox. 

There's a lot of great innovation that has enabled Docker for Mac to work so beautifully out of the box. [xhyve](https://github.com/mist64/xhyve/) allows lightweight headless virtualization and [osxfs](https://docs.docker.com/docker-for-mac/osxfs/) provides a native-feeling experience for sharing files between the host and container.

### Lightweight and user friendly

Thanks to the new virtualization layer provided by [OSX 10.10 Yosemite](https://developer.apple.com/library/content/releasenotes/MacOSX/WhatsNewInOSX/Articles/MacOSX10_10.html), Docker for Mac is able to run without the overhead of VirtualBox and docker-machine. 
Simply open Docker.app, and the lightweight [xhyve](https://github.com/mist64/xhyve/) virtualization layer runs in user-space. Quit Docker.app, and the virtualization layer is killed. Anecdotally, the new virtualization layer seems to consume less memory than the previous VirtualBox setup, but I don't have data to back this claim up.

<img src="{{ site.baseurl }}/assets/docker/docker-menu.png" width="400" />

### Easy infrastructure setup
Docker for Mac enables newcomers to quickly spin up and run a complicated infrastructure. Getting a LAMP stack with Wordpress running takes two commands:

{% highlight text %}
$ curl -LO https://raw.githubusercontent.com/bitnami/bitnami-docker-wordpress/master/docker-compose.yml
$ docker-compose up
{% endhighlight %}

### Details matter
Docker for Mac also has a nice auto-update feature, ability to easily opt in to the beta, helpful status indicators and more found in the preferences.

<img src="{{ site.baseurl }}/assets/docker/docker-preferences.png" width="400" />

### Diagnostics built-in
Docker comes with a useful diagnostic feature built-in. It's a great way to diagnose any issues you are experiencing and share in a bug report.

<img src="{{ site.baseurl }}/assets/docker/diagnostics.png" width="400" />

### Wishlist
It would be great to see [Kitematic]() both included and better integrated into the default Docker for Mac download. The GUI would make Docker for Mac instantly accessible to the developers less comfortable with terminal. 
