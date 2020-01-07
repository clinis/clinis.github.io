---
layout: post
title: Offline PWA with fallback images
---

Earlier this year I managed to setup responsive images with `srcset` on a static site I'm working on. Now, I was trying to turn this site into a [PWA](https://developer.mozilla.org/en-US/docs/Web/Progressive_web_apps), mainly for it to work offline.

I decided to use [Workbox from Google](https://developers.google.com/web/tools/workbox) to [precache](https://developers.google.com/web/tools/workbox/guides/precache-files) pages and some images and assets of the site.

> Workbox is a set of libraries and Node modules that make it easy to cache assets and take full advantage of features used to build Progressive Web Apps

Workbox provides caching strategies (how to serve old or new files, from cache or from network first) and can generate a list of files to cache, even handling the versioning/cache busting.


## The Build process

The build process uses Gulp and consists of:
1. Static Site Generator build;
2. process some assets;
3. generate responsive sizes for images.

As I want to cache the pages and some of the assets and images, the generation of the Service Worker from Workbox needed to happen at the end of the build process. All I had to do was follow the Docs [guide to integrate both `workbox-build` and Gulp](https://developers.google.com/web/tools/workbox/guides/generate-service-worker/workbox-build).


## The problem

The problem I faced was that the processing of the images to generate responsive sizes, generates 5 different sizes per image. If I cached all processed images, the site cache would be 100+ MB, which is really big. I could not cache images, but I really wanted to do that. One option would be to only cache the original image, or only the small sizes, but this way the `<img>` would not work offline.


## The Solution: route requests for images to the small cached size

The solution was to only cache the small sizes of images and handle all the requests for images and route them to the small size.

What I had to do was [provide a response to a route](https://developers.google.com/web/tools/workbox/guides/advanced-recipes#provide_a_fallback_response_to_a_route).

So, I pre-cache the small size of all images.

Then, when the service worker detects a request for a image, it intercepts the request and searches for the small version of that image on the cache.
