---
title: "Why I built this site"
description: "Some assorted thoughts on why I built my own website with a blog instead of just posting to social media."
date: 2021-03-30T10:30:00-06:00
tags: ["meta", "dev"]
draft: false
---
I built my first website in 2003, the summer before starting Junior High. I was in a University of Alberta summer camp that taught kids to write very basic code. The final product was a greenish-grey, purely HTML, Web 1.0 site presenting very basic information about the game Star Wars: Galactic Battlegrounds. I learned how to publish the site to GeoCities, took the files home on multiple floppy disks, and then forgot about it as I went back to playing Star Wars.

The internet has come a long way since and so have my reasons for wanting a website.

About 10 years ago I started getting more serious about photography. I needed a website to not only show a portfolio of work, but to link to all of my other online spaces (Flickr, 500px, a Facebook page, etc.). Over the next decade, I built more WordPress portfolios than I actually published, wrestling with themes and plugins. I tried almost every photography-specific web service, like Koken, 22Slides, and 4ormat. These were nicer to use for photography, but lacked customization and weren’t great when I needed to add other projects — like my actual professional work in software development. 

Now after a few years of having no site at all, I created one from scratch using Hugo.

Most of these personal sites/portfolios/blogs don’t talk about why the site was created, or why it’s necessary to have one. I think that thought process might be useful for others who want to do the same, so I’m going into it with the first two posts:

* Why I built the site (this post, a non-technical overview)
* [How I built this site](/posts/how-built-site-theme-hugo/) (a technical overview)

The site is split into two basic parts: the portfolio (Projects) and the blog (Posts). The following are some of the biggest questions I thought about while making the site.

{{< cloudinary src="flight/view-from-plane" alt="A photo taken from inside of an airplane of mountains on a flight from Alberta to British Columbia. The frame of the window is visible in the bottom right corner. The mountains have a golden cast from the sunlight, and the image is grainy due to being taken with a film camera." caption="A photo I took with my Contax G1 at the start of a trip while flying over the mountains between Edmonton and Vancouver." >}}

## Portfolio
### Why not create separate photography and code portfolios?
I’ve always had a hard time combining both my photography and my software and web development work into one portfolio. There aren’t any good search results that I’ve found on this.

One option that sounds easy would be to split the two. Just have a photo.abbieschenk.com and a dev.abbieschenk.com. But what about projects that use both? I worked on a multimedia project before that combined photography, audio recordings, and a coded timeline. A current project was going to include both photography and an interactive website. The photography part was dropped, but which site would it have gone on? Posting to both is redundant, and what about projects that don’t fit neatly into photo or development? I don’t want to spend more time curating when I could be making things, editing, or writing.

### Who is this aimed at?
It all depends on the purpose of the site. Although I’m open to it, I’m not actively looking for photography work. For development jobs, I’m applying to traditional job postings, so anyone looking for me in that context will already have my targeted resumé, cover letter, and a link to my GitHub.

If someone’s hiring me for any other projects, I want it to be for the skills that make me unique because those are the kinds of projects I would more likely find meaningful and fun to work on, especially while holding a full-time job. For me, that’s a combination of both development and multimedia skills. I want the site to show this, not just one or the other.

## Posts
### Why a blog and not just a list of projects?
Sometimes I want to discuss how I made something, and don’t necessarily want to throw it all on the project page — especially if it’s a deep dive into a smaller part. I also might post smaller things here that aren’t necessarily projects. For example, a photo series about mushrooms might be a fun post but wouldn’t go into my projects portfolio.

Another goal with this site is to keep up with writing now that I’ve finished writing my Master of Arts in Recreation and Leisure Studies thesis. I’m not sure where I’m going with writing, but I want to keep up with and continue developing my skills.

### Why not just use social media?
My issues with social media will need their own post. Social media platforms do not allow for meaningful, thoughtful writing. Instead, most of them actively encourage against it. Writing a post here requires me to actually take the time to think about what I’m writing instead of firing off a quick tweet about whatever crossed my brain at that moment. Here I have the space to carefully consider what I type, reference other relevant and interesting work, and provide context and nuance — and consider whether I should even write it at all. I can also post code if that’s necessary, although I don’t plan on this being too coding-focused.

Social media content streams also generate a constant sense of urgency. If you’re not posting, you’re not being seen among everyone else’s posts. If you’re only posting once in a while, yours will get lost in the swarm. But on my own site I can post whenever I have time or feel like it. These first two posts could even be my only two posts. Hopefully not, but we’ll see.

### Analytics
This site doesn’t have likes, it doesn’t have retweets, and it doesn’t show me which of my friends have clicked on the post. While I do have Google Analytics set up, my main goal isn’t driving traffic to the site. I also have comments, but that’s more so that I don’t have to track social media to interact with anyone who feels compelled to write back — and on the user side, they don’t have to reply to a tweet from months ago.

I’ve worked in digital communications, tracking all sorts of content engagement metrics. It’s exhausting and honestly a lot less useful than interesting and unique content. I also don’t want to get drawn into creating content only for its potential to generate engagement. I ultimately don’t really care how many people read these posts. I don’t intend to create a super successful blog, just a place I can write things down that I find interesting and might interest other people who come across it.

### Why not Medium or WordPress?
Although I forgot about my Star Wars: Galactic Battlegrounds site, it lived on, serving grey-green hues and less information than the instruction booklet that came with the game. 

At least it did until GeoCities shut down only six years later in 2009.

GeoCities lasted 15 years from 1994–2009. Just 10 years before shutting down, GeoCities was ranked as the third-most visited website in the world[^1]. I considered using SquareSpace or Medium for this, but it’s impossible to tell how long either of them will exist.

Instead of throwing everything into a closed platform again, I went with building my own site using a Static Site Generator called Hugo. The next post goes more into this topic, but I also had to decide if I wanted to use a Content Management System. I decided against it, and just write my posts in a simple language called [Markdown](https://www.markdownguide.org). All of my site’s content is stored on my computer, its backups, iCloud, and on a GitHub repository that Netlify uses to serve the site. I can change any one of these steps extremely easily, like if Netlify shuts down its free tier.

(If you still really want to use GeoCities, take a look at [neocities](https://neocities.org))

## Conclusion
I wanted a site to:
* Build a portfolio to show my projects in one place.
* Reduce my social media use.
* Keep writing.

If this rings familiar to you, you might be interested in the tandem first post on [how I built this site](/posts/how-built-site-theme-hugo/). Or you might like to follow along, which you can do via the social and RSS links at the top and bottom of this page.

I look forward to wherever this goes.

[^1]: [Yahoo! GeoCities - Wikipedia](https://en.wikipedia.org/wiki/Yahoo!_GeoCities)