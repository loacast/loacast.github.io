---
title: "Workshop Considerations"
date: 2022-05-24T17:45:00+10:00
draft: false
---

I was chatting with one of my fellow AusCert presenters, and started to reflect on how vastly different presenting a hands on workshop was from past presentations I have given. I have run workshops before, but they happened to be very content dense, and while the participants had an opportunity to do some worked examples, the material had to barrel forward to fit into the time.

I undertook this .NET pentesting workshop in a very different way, starting from materials preparation. Very quickly, I settled into the idea of breaking the day into two parts, focusing on black-box, any architecture ways of evaluating Windows client applications in the first half of the day, then getting into .NET specific tools and techniques in the second.

Out of the ~3 months of prep time between acceptance and the presentation, 8 to 10 weeks was spend just building the apps that the participants would be pentesting, with 2 to 4 weeks spend building a cloud environment for the participants. My presentation came together very much in the last week leading up to the session. The natural result of this is that my prepared material was relatively sparse across the whole day, largely leaving the participants to explore the two applications. I have some indication that people enjoyed having a more hands on session where they got to get their hands dirty rather than sit through a day of being talked at. It is a different thing to get used to, compared to the time-filling or content-culling that usually needs to happen with a presentative session.

As the day progressed, between the major waypoints I had set up, I did get a bit more chill with letting the guys do what they do well. I also punctuated the end of the session with some... "something like this may or may not have been seen in the field" stories.

There were a few final takeaways for the future:

- I hadn't tested my cloud environment out to a sufficient size of class, and ran into some allocation limits. Fortunately I was able to spin up a final instance in another region manually. I will need to revisit my cloud environment for future sessions.
- I had missed the notification that I would be able to get a list of my participants ahead of time, and I didn't obtain the schedule for the various breaks through the day, which left us a bit reactive.
- Planning a backup network solution for the participants isn't a bad idea, incase a network switch blows up in the future.

As a very final note, my [prior post on submitting to the Call for Papers](https://layersofabstraction.net/posts/road-to-auscert/) has been updated with the original submissions.
