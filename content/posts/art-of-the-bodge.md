---
title: "The Art of the Bodge"
date: 2018-03-03T18:00:00+10:00
draft: false
---

Back before I started uni, I was at the wrong end of the country. I had to drive from Mount Isa to Tasmania and I decided I wanted to show where I was each day to whoever was reading my website.

Now I had a problem. I was at the time using a basic Nokia 3315 which had snake, but no internet to speak of. It was at this point that I applied my favourite development tools of the time to the problem. I was doing a bunch of basic php and was playing around with the gd graphics libraries.

I may not have had data, but I did have SMS and a basic Navman GPS. I first grabbed a bunch of kml files from google maps which described my route and the outline of the states which I used to write a basic mapping system in php + gd. I then hooked this up, using the pop email libraries in php to an email inbox, and used a free SMS to Email gateway on my phone.

As we went I would grab the coordinates of my GPS, SMS them to my site and the red dot would follow the path… That was the plan anyway. The system worked fine, however weather intervened and forced me to head west and south rather than to the east as was originally planned, so the dot wandered off the path that was originally drawn.

![A map with a route from Mount Isa to Launceston](/img/posts/art-of-the-bodge/geeks-cant-map.jfif)

For years my Aunty had a copy of this image with the red dot wandering out west on her fridge, with the caption beneath it, “Geeks, they can’t follow a simple map!”

And that is the art of the bodge...

Oh and one last thing...

[Tom Scott video about the Art of the Bodge](https://youtu.be/lIFE7h3m40U)
