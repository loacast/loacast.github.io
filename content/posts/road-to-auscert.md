---
title: "Road to AusCert"
date: 2022-05-18T18:00:00+10:00
draft: false
---

Presenting at conventions is something I have been incredibly fortunate to do from very early in my Cyber Security career. I need to go back and find the specific snippets, but Bruce Potter, Dan Kaminsky, and others I have watched over the years have stated the importance of new people presenting and that the best experience of these cons is from presenting. I also had the benefit of a very supportive team at Alcorn Group supporting my first submission to CrikeyCon 2018.

## Call for Papers

I have submitted CFP's to a few conventions at this point, and I have succeeded at a couple (though one fell through nearer to event date). Without having joined a review board for CFP submissions, I still think I have seen a pattern in the talks which were accepted. Each successful CFP has been on an area where I had substantial passion and drive. CrikeyCon 2018 my session was about a Raspberry Pi based network KVM that I had been working on for nearly two years (HD am I in the middle, CrikeyCon 2018)[https://www.youtube.com/watch?v=5meK6Ty0oSc]. In this latest case, with AusCert 2022, I am running a .NET Thick App Pentesting workshop which mixes a substantial area of growth in my personal experience with a obsession with learning new things and teaching others. 

The CFP submissions opened in December 2021 and had two deadlines, the 10th of January to get feedback from the committee, and a final dealine of the 30th of January. I sumbitted around the 4th of January.

I actually submitted two CFP's for AusCert 2022, one a presentation breaking down the failure modes I have seen in .NET applications in the wild, and the second successful CFP to run a .NET Pentesting workshop. The CFP process was fairly straightforward, several paragraphs to describe what I intended to walkthrough in a form on the AusCert site, and the CFP's were away. 

I am trying to re-acquire my initial CFP submissions to include here, and will update if I get them.

On the 19th, I got asked for some additional data for my workshop session:

```
Thank you for submitting "Penetration testing of .NET client applications" presentation for consideration into the AusCERT2022 Conference program. The program committee have provided the following feedback:
Please provide clarity/understanding of the following
1.	More detail/specificity on presentation content required 
2.	What angle will this be presented from?
3.	What will attendees learn/gain from the presentation?
```

My response was:

```
Thank you for reaching out about my proposed workshop session. 
 
This workshop would be targeted at persons with some existing web application testing experience, and provide an overview of the additional attack surfaces, failure modes, and testing complexity inherit in thick client assessments. This will be done through a hands-on workshop and demonstration of evaluating security risks existing within a DotNET client application. DotNET applications can be readily decoded back into readable application code, unlike C++ or similar compiled languages. This lends to DotNET being an excellent waypoint between web app testing and thick client assessments.
 
The content will follow the following topics:
•	Assessing applications from a zero-knowledge perspective
  o	Black-box thinking – Looking at the application inputs and outputs
•	Thick client attack surface
  o	Network Communications
  o	Filesystem Interaction
  o	OS Interaction (Registry entries, system calls)
•	Fundamentals of the DotNET platform
  o	The CIL interpreter
•	Setting up an environment to intercept and interact with a DotNET client
  o	Network interception
  o	System, network, and registry calls
  o	Attaching a DotNET debugger
•	Runtime manipulation through a debugger
  o	Setting breakpoints
  o	Manipulating memory to affect application execution
•	Using instrumentation to call application functionality
  o	Injecting attack code into an application
  o	Invoking sensitive functionality directly
•	Tales from the field – Describing real world thick client vulnerabilities
 
The overall intent of the training will be to give web application penetration testers an initial exposure to thick client penetration testing, and practical experience with tools for performing DotNET assessments. 
 
I hope this further assists in understanding the intention and format of the proposed workshop.
```

## The nervous wait

So the final deadline came and went, and so started the nervous wait to hear back from AusCert. On the 25th of February, I got two emails. Unfortunately, I read this one first:

```
Dear Clinton,

Thank you for submitting your presentation for consideration into the AusCERT2022 Conference program.

We received a large volume of presentation submissions for consideration and the AusCERT2022 Program Committee spent a great deal of time carefully reviewing each one. The calibre of submissions received was incredibly high and it was a difficult task to select presentations for the main program and even fewer for the workshop days.

Unfortunately, on this occasion, we regret to advise you that your below submission has not been accepted to the 2022 conference program.

Presentation Details
Title	Bringing the streetlamp to native client applications
Presentation Type	Conference Presentation
Theme	Other
Presenting Author	Mr Clinton Kerrison
```

I was somewhat deflated, then saw the second email...

```
Dear Clinton,

Congratulations, we're pleased to advise that your below submission has been accepted into the AusCERT2022 program, the 21st Annual Information Security Conference is being held from Tuesday, 10th to Friday, 13th May at the Star Gold Coast.

Accepted Presentation
Title	Penetration testing of .NET client applications
Presentation Type	Tutorial
Theme	Other
Presenting Author	Mr Clinton Kerrison
Affiliations: Cybercx 
```

I exploded... and rushed out to tell Chrissie (my lovely wife) the good news...

## So whats the big deal about AusCert

For a bit of context, I had not attended AusCert at this point, but had floated around the periphery for several years. I first went down in 2016 to attend a Hak5 Meetup when Darren was down to present at AusCert. From that meetup I met Dook, one part of the driving force for SecTalks Brisbane and started the chain of networking that led to meeting Wade and starting my InfoSec career.

![Playing "The Contender" card game with the Hak5 meetup, GC 2016](/img/posts/auscert2022/Contender.jfif)
Source: [@hak5darren](https://twitter.com/hak5darren/status/736585218023264256/photo/1)

The story of developing the workshop and preparing for the event will need to wait till another day. The main takeaways I want to put out there is that doing a CFP isn't hard, and that it is 100% worth having a go. I did my first CFP to CrikeyCon within months of starting at Alcorn Group. I want to see more of our fresh faces up on stage learning their craft from both the learning and the teaching angle.


