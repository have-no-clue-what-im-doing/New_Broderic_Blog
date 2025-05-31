+++
title = "Thoughts on Hugo"
description = ""
tags = [
    "blog", "hugo",
]
date = "2022-05-29"

+++




I originally found out about Hugo after browsing Hacker News (YCombinator) and coming across a blog with a footer containing a link to Hugo's site. You can scroll to the bottom to get an exact example of what I'm talking about. If you click on the link you can see Hugo advertised as: "One of the most popular open-source static site generators." Beforehand, I had been thinking about creating my own site and was researching what exactly I wanted to build my site with. Reading this I immediately bookmarked it. Hugo also claims to be the world's fastest framework for building websites. Have no clue how true that is. Although Hugo is freakin fast once everything is set up. I specifically wanted to create my site as a blog and hugo seemed perfect for that. If you look at the [themes](https://themes.gohugo.io) for hugo it's mostly just blogs. 

Once I came across the hugo-dusk theme I decided that I was going to create my blog with Hugo. Before, I was considering Jekyll or Wordpress, but once I saw the hugo-dusk theme I made up my mind and immediately installed Hugo. I started reading the documentation and it looked a little confusing, but I wasn't discouraged. Once I actually started creating my site I quickly realized Hugo was kind of a pain in the ass. Over time I came to the conclusion that the Hugo [documentation sucks](https://news.ycombinator.com/item?id=30527884).  To say it's confusing would be an understatement. I think part of the problem was that I'd never used a static site generator before so everything I was doing was brand new to me. 

Creating the site and implementing a theme locally were pretty easy. The two main issues I had was modifying the theme, and hosting the site. Hugo allows you to either create your own theme or choose a theme created by someone else. Themes are usually hosted on Github. You can just clone the repo into your themes folder. Easy enough. Everything works out great locally until you actually try to host the website. Right when you attempt to put it on Github, Github is like, "Hey this is something you got from Github, you need to create a submodule." I could just delete the git file, but then I have the problem of not getting continuous updates from the theme's author. So I go ahead and create a submodule instead. The problem is now I don't actually have control of the theme. I can't directly modify it myself. Thankfully, with Hugo you can tell your site to overwrite the theme to your liking. The main problem with this is that it isn't that reliable and it's just a huge pain to get it to work.

The way Hugo works is that you choose a theme, add content, then have the Hugo generator convert all your content into static HTML files so it can be properly hosted on the web. Here's what the file structure of my site [looks like](https://github.com/have-no-clue-what-im-doing/Broderic_Blog)

    User\Hugo\MyBlog  
	
    |- .git
	|- archetypes
	|- content
	|- data
	|- layouts
	|- public
	|- resouces
	|- static
	|- themes
	|- .gitmodules.txt
	|- config.toml
	|- netlify.toml
	|- README.md
	
One particular thing I didn't really like about the theme was that the body width was too narrow. I wanted it to be a bit wider. The easy and straightforward way of going about fixing this would be to just change the body width property. But I can't just go to the theme's css file and change it manually since the theme is a submodule. I have to overwrite it. So in order to do that I have to go to: static\css\custom.css and put in my css. In order for Hugo to accept my custom CSS I have to let my config file know. So under params I put:

    custom_css = ["css/custom.css"]
	
But it's not working. Why? Because the theme wasn't ever set up to accept css overwrites. So now I have to overwrite the html in order to get the theme to accept my css. I navigate to: 
    
	User\Hugo\MyBlog  
	
	|-layouts
	     |-partials
	          |-head.html
			  
Then I put this into the head.html:
 
    {{ range .Site.Params.custom_css -}}
    <link rel="stylesheet" href="{{ . | absURL }}">
    {{- end }}
	
So now my custom css should work right? Wrong. Hugo is stupid. When troubleshooting this I had no clue what was going wrong. All I put in my css file was this:

    .main {
    max-width: 55em; 
    }

But the body of the site refused to change. I knew this was the right property as when using inspect element on Chrome and manually changing the property, it actually changed. But for whatever reason Hugo was refusing to do that. I decided to try changing the font size of all text to see if my custom css configuration was wrong or if Hugo was just being a pain. When saving a new font-size to the css file it worked. So my configuration wasn't wrong, Hugo was just ignoring me. I spent about an hour and half on this and finally decided to try putting the !important argument for the property.

    .main {
    max-width: 55em !important; 
    }
	
And suddenly, it worked! Yay! Thank you Hugo, that was so fun figuring all that shit out on my own just to change the body width by like 10%. Usually takes someone about 10 seconds to change a single property in css. Took me 90 minutes. Thank you Hugo!

The other issue I had was with trying to get this thing hosted via Netlify. In order to get this working with Netlify you have to add a netlify.toml configuration file. Hugo gives you like no help with this. They just [mention](https://gohugo.io/hosting-and-deployment/hosting-on-netlify/) it and are like just copy and paste this and it should work. Yeah, well it doesn't. Hugo doesn't even bother explaining what exactly any of of the configs do:

> The Netlify configuration file can be a little hard to understand and get right for the different environment, and you may get some inspiration and tips from this site’s netlify.toml:

I just love who ever wrote this documentation saying: Yeah, this is a little hard to understand, so to help I've given you an example with no explanation whatsoever. It MAY? give me some inspiration and tips? How about you just explain this shit so I don't have to google around like a maniac and waste precious minutes of my life?

    [build]
    publish = "public"
    command = "hugo --gc --minify"

    [context.production.environment]
    HUGO_VERSION = "0.100.0"
    HUGO_ENV = "production"
    HUGO_ENABLEGITINFO = "true"

	[context.split1]
	command = "hugo --gc --minify --enableGitInfo"

	[context.split1.environment]
	HUGO_VERSION = "0.100.0"
	HUGO_ENV = "production"

	[context.deploy-preview]
	command = "hugo --gc --minify --buildFuture -b $DEPLOY_PRIME_URL"

	[context.deploy-preview.environment]
	HUGO_VERSION = "0.100.0"

	[context.branch-deploy]
	command = "hugo --gc --minify -b $DEPLOY_PRIME_URL"

	[context.branch-deploy.environment]
	HUGO_VERSION = "0.100.0"

	[context.next.environment]
	HUGO_ENABLEGITINFO = "true"

	[[redirects]]
	from = "/npmjs/*"
	to = "/npmjs/"
	status = 200
	
I copy and paste this whole config and to my absolute surprise it doesn't work. So now I have to use some Googlefu to see what the hell any of this is doing and what Netlify actually needs.

After like 45 minutes of looking at documentation from unofficial sources, I figure out I just need the [build] and [context.production.evenronment] configs. 

Overall, once I got everything set up correctly, Hugo has been easy to use. No hiccups what so ever. I just do a git push and within seconds my site is updated. Hopefully this configuration of Hugo, Github, and Netlify doesn't break down. Those are three things that all rely on each other for this to actually work. If Github or Netlify have some dumb update it could cost me hours to figure out how to fix. Hopefully that never happens. 

