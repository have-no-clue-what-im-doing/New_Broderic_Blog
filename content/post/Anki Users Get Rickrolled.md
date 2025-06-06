+++
title = "Anki Users Get Rickrolled"
description = ""
subtitle = "Why Open Source Needs Trademarks"
tags = [
    "blog",
    "anki",
    "open source",
    "trademark",
    "rickroll"

]
date = "2025-06-06"

+++

## Anki

Just recently Anki went through what's probably the most drama it'll ever experience. If you've never heard of [Anki](https://apps.ankiweb.net/), it's a free,  open source flashcard application that uses ["active recall testing" and "spaced repetition"](https://docs.ankiweb.net/background.html), which allows for more efficient study and memorization. Anki was originally developed by Damien Elmes, who created Anki to help him learn Japanese. The word "Anki" comes from the pronunication of the Japanese word for "momorize". Anki is nearly 20 years old and over the decades has become extremely popular. With over 21K stars on Github and [at least 10M+ users on the Android app alone](https://forums.ankiweb.net/t/anki-downloads-statistics/28788/5). This has led to some developers taking absolute advantage of its name and branding. 

## Anki Knockoffs

A problem Anki has faced for quite some time is what has been deemed as ["copycat apps" or "knockoffs"](https://faqs.ankiweb.net/anki-knockoffs.html). 

> AnkiApp and Anki Pro were developed by separate groups of people, and they are not related to the rest of the Anki ecosystem. They were released years after Anki was already established in the marketplace, and we suspect the names were deliberately chosen to take advantage of the brand recognition we have built up. Using Anki in the name implies that they will function with the other Anki clients, which they do not.

When searching Anki in any app store, it gives you results for multiple Anki named flashcard apps. This leads to many users mistakenly downloading one of the knockoff apps. This causes incredible confusion for anyone wanting to try out Anki. I'd say most users don't know any better which one is officially tied to the open source project, and thus end up installing the wrong one. These knock off apps are free to download but usually require a subscription to access features Anki already provides for free. 

The one large exception to this is for iOS. For the official Anki iOS app, the price of purchase is $25. The reason for the iOS being paid is because it acts as the developer's [main source of income](https://web.archive.org/web/20190318140639/https://apps.ankiweb.net/docs/manual.html#why-is-the-android-version-free-when-the-iphone-version-isn%E2%80%99t)[^1].

> Working on Anki desktop, AnkiWeb and AnkiMobile is my full time job, and I need some way of paying the bills. Since I make the desktop & web versions available  for free, I rely on sales of the iPhone app in order to finance development.
> 
> AnkiDroid is written by a separate group of volunteers. Since they based it on the free desktop version I make available (and rely on AnkiWeb in order to synchronize decks), they decided to make it freely available as well.

In the long run, this is actually cheaper than paying a stupid subscription every month, but for most users, the 25 dollar price tag is too much. And so more users end up downloading one of the knockoffs.  

The one knockapp app I want to discuss in particular is (or was)[^2] named AnkiPro. AnkiPro uses similar algorithms as Anki that allow for the same kind of spaced repetition flashcard studying. The app claims to have features such as: 

* User friendly design
* Algorithm presets
* Beginner-friendly
* Advanced sharing options
* Offline mode

![AnkiPro vs Anki](/anki_rickroll/ankipro_vs_anki.png)

I do have to give credit for some of these knockoff apps as the UI is better, more intuitive and they have better, real time syncing. Unlike the official Anki app which you have to [sync manually and there can be merge conflicts](https://docs.ankiweb.net/syncing.html#merging-conflicts). To be fair though it's completely free, unlike these apps. 

It turns out though, for the AnkiPro app, the offline mode feature wasn't entirely true. For most user's, their flashcards were not actually accessible unless online. What could possibly go wrong with that? 

## AnkiPro Outage

Starting on May 17th, AnkiPro users starting reporting syncing issues and even completely lost decks. Both the Anki and AnkiPro subreddits quickly started filling in with complaints. To say people were pissed would be an understatement. This outage happened during the end of May, which for a lot of students is when major exams are taken. It got so bad that the Anki subreddit and forum had to [clarify that they had no control over the AnkiPro app](https://www.reddit.com/r/Anki/comments/1kr9cuj/anki_is_not_down_ankipro_is_not_anki/) and that they had unfortunately been tricked into downloading the wrong application. 

With an application based on the whole premise of daily studies, you'd think AnkiPro would get its shit together and fix the outage within a reasonable time. But no, this outage was **BAD**. The outage wasn't resolved until May 27th. An entire 10 days! 

There were a myriad of complaints stating how users were completely screwed for their upcoming exams and that they were completely doomed. One user posted that he was now going to [fail his Med School Exams](https://www.reddit.com/r/Anki/comments/1kvd3ub/ankipro_scammed_me_and_now_ill_fail_my_med_school). 

> Hi, I don’t know if anyone’s going to see this, but it’s worth a shot. I have my Medical school finals in 2 weeks, and have used AnkiPro for all of my notes throughout the year. I have been in a horrid panic for the last 10 days trying to restore my cards hoping and praying the situation will get fixed soon, but clearly there is no light at the end of this tunnel. When I try to use the copycat converter, it just comes up with a youtube video of a song??? Could anyone possibly have ay advice? I’m willing to pay just to get these cards back, the rest of my life and career depends on these exams.

In the ensuing panic, a developer that goes by the name `abdnh`, was letting users know that he had already [created an add-on tool](https://github.com/abdnh/anki-copycat-importer/tree/master) that would allow an AnkiPro victims to transfer their cards to the real Anki application. However, you'd need your cards to be available online first. So if your cards were already offline, this didn't really help. Named the ["Copycat Importer](https://ankiweb.net/shared/info/2072125761)", the add-on worked by directly scraping the user's AnkiPro account and all its flashcards. 

## Rickroll

The AnkiPro developers were not the biggest fans of this. Realizing this tool's sole purpose was to take customer's away the AnkiPro app, the devs went out of their way to detect the scraping of their site and send victims a nice little rickroll. Just a complete f-you from the devs to anyone who dared tried switching over to a competing app. This was implemented well before the server went down, but it still remained active quite some time while the outage was still ongoing. 

![AnkiPro victims getting rick rolled](/anki_rickroll/rickroll1.png)

Examples:
[[1]](https://forums.ankiweb.net/t/copycat-importer/43883?u=abdo)
[[2]](https://forums.ankiweb.net/t/copycat-importer-ankiapp-ankipro/16734/345?u=abdo)
[[3]](https://forums.ankiweb.net/t/copycat-importer-ankiapp-ankipro/16734/501?u=abdo)

AnkiPro eventually posted a statement on their subreddit stating what exactly happened:

> At one point, our cloud provider's storage system severely degraded, with reads/write to the database becoming 20-30 times slower. This caused syncing issues across our database servers and led to inconsistent data. Some users saw missing decks or cards, while others weren't affected at all.
> 
> We contacted our provider about the ongoing issues with the disk.
> 
> We began preparing to restore from our most recent backup. However, before we could complete that process, our provider without warning, replaced a storage system. This caused severe filesystem corruption on one of our core servers and disrupted the backup environment we were preparing to use for recovery.
>
> Because our system is sharded across multiple nodes, recovery became significantly more complicated - ensuring consistency across the cluster required careful reconciliation.
>
> Following the incident, we immediately restricted access to the app to prevent further data inconsistencies and began the recovery process.
>
> Our team worked around the clock - often 20+ hour days for nearly a week - to restore database functionality and verify data integrity. This was a complex process involving deep inspection and reconstruction, but the vast majority of data was recovered.
>
> We want to be clear: we're not blaming our cloud provider. They acted according to standard procedures. It’s on us, we just weren’t prepared for this kind of situation.

Can see entire statement [here](https://www.reddit.com/r/AnkiPro/comments/1ky7ifp/recent_outage_public_statement/)

No mention of the rickroll. One commenter did bring it up though, with their response being:

> This one is actually pretty simple.
>
> Over the past year, we saw a sharp increase in unauthorized requests to our internal APIs - including DDoS-like traffic. About six months ago, we added a small easter egg that played a certain video when our security system blocked requests coming through unauthorized services.
>
> During the recent outage, we saw posts that some users trying to switch apps or export their data were hit with the video due to using third-party extensions or apps. We turned it off immediately to ensure everyone could access and export their data without interference.

Not really buying that they "immediately" turned it off. The rickroll was active for quite some time afterwards. 

## Trademarks and Open Source

One clear lesson comes out of this: Trademarks! This is a prime example of why trademarks are so important and why companies actively enforce them. Yes, some companies take advantage of trademarks and enforce a little too much. And also some common / vague words simply should not have been trademarked in the first place. But this right here is why trademarks are so important. Just because something is open source does not mean you can't enforce a trademark. If you have a very popular open source project, and have the time and money, consider getting it trademarked. Otherwise, down the road, you could have to deal with a mess like this. All of this could have been prevented if Anki had its name trademarked and enforced it with some attorney harassment. 

Obviously for the majority of open source projects, a trademark would be a huge waste of time and money. But for the few that are popular, hopefully there is enough income to get it trademarked and enforced.

If you want to read more regarding trademarks and open source, Google has a great [article](https://google.github.io/opencasebook/trademarks/#introduction) going over it.

## Finally

Funny thing is that during this whole ordeal, Anki had already [filed a trademark](https://tsdr.uspto.gov/documentviewer?caseId=sn79340880&docId=PB120250430014031&linkId=2#docIndex=2&page=1). Issue date of April 30, 2025. This is something that should have been done years ago.

![Anki trademark filed](/anki_rickroll/trademark.png)

The trademark was published May 6, 2025, with a 30 day window for any appeals. Which means today, June 6, 2025, the trademark can finally be enforced!

## AnkiPro No More

In response to the trademark, AnkiPro has now been renamed to Noji and should still be avoided like the plague. They advertised offline access, yet essentially held everyone's flashcards ransom with this stupid "always online" bullshit. Hopefully Noji fades into obscurity just like the rest of the knockoffs once they are forced to change their names. Doing a search for Anki on either app store (and even a web search) still shows plenty of knockoffs using the Anki name. I'm excited to see all of those disappear in the next couple of months! 

Huge thank you to Damien Elmes and all the other devs keeping Anki alive and well! Long live Anki! 




[^1]: This has since been taken off their website, but I still believe remains true
[^2]: They've recently changed the name of the app, which I will get to later