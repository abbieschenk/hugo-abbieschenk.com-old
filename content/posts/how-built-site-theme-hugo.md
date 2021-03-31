---
title: "How I built this site and theme with Hugo"
description: "A technical overview of how I built this site using Hugo and a custom theme."
date: 2021-03-30T10:40:00-06:00
tags: [meta, dev, hugo]
draft: false
---
After determining [why I wanted to build a site](/posts/why-built-site/), I had to actually build it. Static site generators (SSGs) are constantly recommended, and are also free to host using a combination of GitHub, products like Netlify, and Cloudinary for images. I wanted to try one out myself.

# Choices
## Starter Packs
I began by looking into various starter packs.  But every starter theme I tried to clone would break on my local computer, mostly because I’m using a new M1 MacBook. One package in particular, libvips, kept giving me issues and refusing to build even when I tried following the M1-specific instructions (installing it globally with brew).

## Theme
I also had issues finding themes I liked from the ones available as starters. Just like with WordPress, a lot of themes add features I don’t really need or want, and updates to keep track of. And the ones that look the best are often already used on hundreds or thousands of websites. I don’t want my site to look like everyone else’s. I decided to build my own, which would also let me customize every part of my site and get familiar with its inner workings.

It was also difficult to find themes for both portfolios and blogs. Now that I know how Hugo works, it would probably be easy to add this to an existing theme.

## Static Site Generator
I wanted to use Gatsby to start learning React, and it seemed to have the nicest themes available. But since I wasn’t worrying about themes anymore, I looked into other options. Hugo kept jumping out at me as being extremely fast and easy to work with. I have no experience with Go, but I decided to give it a shot. So far, the claims of speed and easiness have been very true.

## Content Management System
I was going to use a CMS to manage my posts and projects. I always wanted one that integrates with GitHub, so that my content isn’t hosted by the CMS but locally on my computer and online on GitHub. I did start trying to integrate Netlify CMS, but questioned why I even needed it about halfway through. I’m the only author, and I’m very comfortable writing these posts in Bear, then pasting them to a new Hugo post in VS Code before pushing them to my GitHub repository. I decided it’s actually less complicated to forgo a CMS for this site.

# The abbieschenk Theme
You can find the theme I made on [GitHub](https://github.com/abbieschenk/hugo-theme-abbieschenk), along with [this site](https://github.com/abbieschenk/abbieschenk.com). It’s made specifically for this site, so some things might not work right for you. I recommend forking the repository and reading the README.

## Tutorial
I followed an excellent tutorial to start building my theme. While looking through the rest of the site to see if I wanted to subscribe to its RSS, I found a list of the author’s favourite things. This included a YouTube debate about “trans activism” by some of the most prominent anti-trans activists on the internet. Whether we can separate the work from the author might be an interesting discussion, but not worth having over a website tutorial.

There are many other tutorials to help you get started with building your own theme, like [this one](https://retrolog.io/blog/creating-a-hugo-theme-from-scratch/) or [this one](https://pakstech.com/blog/create-hugo-theme/). Start with one of these and use the [official Hugo documentation](https://gohugo.io/documentation/) from there.

## NPM
I didn’t want to use NPM. NPM is great and I’ve used it for larger projects, but I wanted to keep this thing as simple and lightweight as possible. I was also annoyed at the amount of NPM modules I’d have to pull in for even the simplest themes when I was still trying to work with existing ones.

## Logo
I made my site logo drop down with the rest of the content by giving it a fixed position, and added a `mix-blend-mode: difference` CSS property. This gives a photo-negative effect when it hovers over images (and anything else).

## Images / Photographs
Since I’m a photographer, the site leans heavy on the photographs. I wanted to display them slightly larger than the text, as many news sites do, and also have a horizontal black border to both edges of the screen.

Hugo unfortunately wraps all content in  `<p>` , including images. This made it impossible to do what I wanted in a simple way, as I needed to apply a specific width to the `<p>` (or its container) and then make the `<img>` in the paragraph tag larger than the existing paragraph tag.

I first built an extremely hacky solution out of oversize borders and negative margins. I’m still pretty proud of the hackiness I made before, so here’s the code in two @mixins:

```scss
@mixin block-border($content-width) {
    $border-width-h: 20px;
    $border-width-w: 50vw;

    border-top: $border-width-h solid black;
    border-bottom: $border-width-h solid black;
    border-left: $border-width-w solid black;
    border-right: $border-width-w solid black;

    margin-left: -webkit-calc(-#{$border-width-w} + (100% - #{$content-width})/2);
    margin-left:    -moz-calc(-#{$border-width-w} + (100% - #{$content-width})/2);
    margin-left:         calc(-#{$border-width-w} + (100% - #{$content-width})/2); 
}

@mixin oversize-img($max-width) {
    @include block-border("(100% + #{$max-width})");
    
    max-width: -webkit-calc(100% + #{$max-width});
    max-width:    -moz-calc(100% + #{$max-width});
    max-width:         calc(100% + #{$max-width}); 
    
    width: -webkit-calc(100% + #{$max-width});
    width:    -moz-calc(100% + #{$max-width});
    width:         calc(100% + #{$max-width}); 
}

```

And then on the `<img>`: 
```scss
img {
    @include oversize-img(20vw);
	max-width: 100%;
    
    @media (max-width: 940px) {
        @include oversize-img(10vw);
    }
	@media (max-width: 840px) {
		@include oversize-img(5vw);
	}
```

## Responsive Cloudinary Images
After hacking this together, I started implementing Cloudinary. I adapted [this shortcode tutorial](https://harrycresswell.com/articles/cloudinary/) for my theme. I then realized that the `<figure>`s created by the shortcode were not wrapped in `<p>` tags, and so I could have much simpler code for the background I wanted — just have the `<figure>` stretch across the screen, and make the contained `<img>` smaller. This doesn’t work for non-Cloudinary  `<img>`s, but I don’t foresee myself using those. If I do, I’ll likely create a shortcode that creates `<figure>`s from static images.

The final result looks lke this:

{{< cloudinary src="flight/view-from-plane" alt="A photo taken from inside of an airplane of mountains on a flight from Alberta to British Columbia. The frame of the window is visible in the bottom right corner. The mountains have a golden cast from the sunlight, and the image is grainy due to being taken with a film camera." caption="A photo I took with my Contax G1 from a plane at the start of a trip." >}}

# Extensibility
I wanted to make the theme easily extendable by anyone who wants to use it for their site. It comes with a README that should go into enough detail to get started. While I do think people should fork it if they want to use the theme, I did include some user-specific files:

* **user.scss** (place in: /assets/scss/): This gets merged into the main.scss and allows users to define their own scss without overriding mine, and with the ability to use the variables and mixins I define in main.
* **user-head.html** (place in: /layouts/partials/): Gets added after the other head tags. I use this on my site to add my Google Analytics code chunk.
* **user-script.html** (place in: /layouts/partials/): Gets added after the other script tags at the end of the page. Useful for adding your own scripts.

There are also some config options detailed in the README, including an easy way to set the accent colour (mine is <span style="color:#53705C;font-weight:bold">green</span>).

# Conclusion
Hugo was extremely easy to develop with. What took the longest time was actually figuring out the design of the theme, but I’m pretty happy with it. If you notice something that is a design faux pas or doesn't seem to be working as intended, I’d love to hear about it in the comments below!