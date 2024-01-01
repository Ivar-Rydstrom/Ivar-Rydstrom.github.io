---
layout: post
title: Personal YouTube Modifications
image: /assets/images/youtube_mod/code.png
description: Tampermonkey injection script for visual front-end modification and quality of life changes to YouTube.com.
category: projects
permalink: /projects/youtube-modifications
related_posts: ""
tags: [computer science]
---
[View this project on GitHub](https://github.com/Ivar-Rydstrom/Personal-Youtube-Modifications).

## Youtube Polymer 2019

In 2017, YouTube.com pushed a new front-end interface to their site--referred to as "Polymer"--which facilitated the introduction of the wildly popular "shorts" video format. YouTube also implemented a way to temporarily request the original interface using the query parameter: `disable_polymer=1`. This sparked many users (including myself) to implement scripts which automatically included the special query parameter upon visiting the site.

![Pre-Polymer YouTube Interface](/assets/images/youtube_mod/pre_polymer.png){:.center-img style="width:100%;height:auto"}
*The "original" YouTube layout, accessible after 2017 using the argument `disable_polymer=1`.*{:.caption}

At some point in 2019, they disabled the `disable_polymer` parameter. Upset with the new YouTube.com layout I was now forced to use, I began developing an injection script which implemented several personal-preference changes which I thought made the Polymer layout more palatable.

![Polymer YouTube Interface](/assets/images/youtube_mod/polymer.png){:.center-img style="width:100%;height:auto"}
*New YouTube Polymer layout (2023), featuring YouTube Shorts.*{:.caption}

Most of my changes involved increasing the number of videos displayed at a time on the YouTube home page, re-implementing collapsible descriptions underneath videos, and entirely getting rid of YouTube Shorts.

## Implementation

I wrote this script in JavaScript, intended to be run with an injection client such as [Tampermonkey](https://www.tampermonkey.net/).

The biggest challenge was accommodating for asynchronous "[lazy loading](https://en.wikipedia.org/wiki/Lazy_loading)," which the new Polymer layout utilized heavily. Lazy loading makes it extremely difficult to predict when DOM elements will be accessible. In certain cases, it is enough to attach an Event Listener, listening for the `load` event of an existing element. However, in the case of lazy loading, many elements don't exist at all until the very moment they are needed.

To combat this, I heavy relied on Mutation Observers, which is a class native to JavaScript whose purpose is to run a callback function whenever a selected DOM element property is changed (called a *mutation*). A Mutation Observer can be attached to a root element such as `document` or `body`, and the callbacks can be manually parsed until we confirm a certain child element has been created. This allows for the detection of newly created or removed elements which may not have existed before.

### Example usage of Mutation Observers
~~~javascript
function initWatch() {
    if (window.location.href.includes('/watch')) {
        // on video lazy-load
        var lazyWatchObserver = new MutationObserver(function(mutations, observer) {
            // check if selected child element exists yet
            if (document.getElementsByClassName('html5-main-video')[0] !== undefined 
                && document.querySelector('.ytp-endscreen-content') != undefined 
                && document.querySelector('#items.ytd-watch-next-secondary-results-renderer') != undefined) {
                /*
                ... inject changes ...
                */
            };
        });
        // attach observer to body
        lazyWatchObserver.observe(document.querySelector("body"), {childList: true, subtree: true});
    };
};

// whenever a new window loads
window.addEventListener('load', function() {
    // declare Mutation Observer
    var observer = new MutationObserver(function(mutations) {
        if (window.location.href.includes('/watch') && !startedWatch) {
            startedWatch = true;
            initWatch();
            lastVidSrc = document.getElementsByClassName('html5-main-video')[0].src;
        };
    });
    // attach observer to body
    observer.observe(document.querySelector("body"), {childList: true, subtree: true});
});
~~~

[See full script on GitHub](https://github.com/Ivar-Rydstrom/Personal-Youtube-Modifications)
