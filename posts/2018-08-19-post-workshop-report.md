---
title: Software Carpentry- Post workshop report
author: Robin Donatello
date: '2018-08-19'
slug: post-workshop-report
categories:
  - event
  - workshop
tags:
  - coding
  - Rstudio
  - rmarkdown
  - R
  - shell
  - spreadsheets
  - swcarpentry
description: ''
---

Last week Chico State hosted it's first [Software Carpentry](https://software-carpentry.org/) workshop and it was a great success. We were thrilled to have [Reid Otsuji ](https://www2.archivists.org/prof-education/faculty/reid-otsuji) from UC San Diego and a [Library Carpentry](https://librarycarpentry.org/) instructor come up to help teach the material. 

We had three undergraduate students help out as technical assistant roaming helpers throughout the workshop: Grant Esparza (Computer Science), Jerry Tucay (Applied Mathematics & Statistics), and Eisley Adoremos (Statistics). Their assistance with answer questions and helping add to the collaborate class notes was invaluable! We couldn't have done it without them. 

### Learners

Our learners were a mixture of undergraduate and graduate students from non technical majors, many faculty and staff from Chico State, external faculty from Sacramento State and researchers from UC Davis, and community business members. Such a blending of backgrounds and experiences was fantastic. 

What was most impressive was the turnout from the [Center for Healthy Communities](http://www.csuchico.edu/chc/). I will be working with this Center on a new [CalFresh outreach grant](http://www.csuchico.edu/chc/calfresh-outreach/index.shtml) and am looking forward to helping to streamline and automate many of their reporting processes. 


### Lesson Details

The details of the workshop can be seen on the [workshop webpage](https://csucdsi.github.io/2018-08-13-chicostate/), which also includes links to the lesson materials. I will still summarize it here. 

**Day 1** we started off with Reid discussing best practices on organizing and recording data in spreadsheets. He covered common pitfalls, problems with dates, data entry and the like. Learners got a chance to take a "messy" spreadsheet and try to reformat into something that is readable by a computer program. After a gentle introduction to the R language and the [R studio](https://www.rstudio.com/) interface, it was time for a well deserved lunch. 

Then in the afternoon I got to demonstrate how awesome markdown is, and how combined with the powers of R they too could make awesome websites (such as this one and [my personal website](www.norcalbiostat.com)), as well as other HTML pages and PDF reports. We dug more into the guts of the R programming language in how R handles data sets (using `data frames`), how to explore these data frames, how to make new variables, logical statements and such. 

**Day 2** Reid introduced the learners to the Bash Shell. We discussed file hierarchy, benefits to using a command line interface as opposed to a GUI, how to navigate your file system (great setup for learning relative vs. absolute paths), and how to edit files in Nano. 

![](/img/swc_aug13_ro.jpg)

The second afternoon returned us to R, this time specifically I gave a very short introduction to Data visualization using `ggplot`. Only having an hour I really didn't have time to get into many of the statistical graphic examples I would have liked to. The other main topic that afternoon was using `dplyr` for data manipulation and aggregation. 

![](/img/swc_aug13_rad.jpg)

**Day 3**
I have been toying around with writing a lesson for contribution to the Carpentries on how to build a website using RMarkdown. I wrote it originally to test out at a Carpentry workshop at UC Davis in January 17, but got food poisoning the night before so I didn't get to test it out. Reid was interested so we invited everyone to attend an optional 3rd morning on using git and [GitHub](https://github.com/) for version control, and building simple websites. 

I was thrilled when 6 participants (most from CHC) along with the 3 student helpers showed up to have fun with git. I really wish we had a full day to devote to this. We only had time to teach the bare minimum git (what it does,`add`, `commit`, `push` and `pull`) enough to use git along with [R projects](https://support.rstudio.com/hc/en-us/articles/200526207-Using-Projects) to make the website. Everyone walked out of that half day with a functioning webpage, and we had a great discussion about what it could be used for (class notes, project website, informational dashboard, file submission etc)


### Collaboration

Throughout the workshop, participants took notes using the online markdown document sharing platform called HackMD. HackMD is like Google docs but written in Markdown. It was a great hands on way for learners to see how to write Markdown code without "formal" instruction. The notes have been locked at this point and are available for [view and downloading](https://hackmd.io/sfN_8XIlQxWQn2UFRZ0kXA?view) without any login necessary. 

### Feedback
While I know Reid and I had fun, what was more important is that the learners had fun and felt their time was worthwhile. As part of being an officially recognized Carpentry workshop, [The Carpentries](https://carpentries.org/) hosted a pre and post survey. This is critical for the instructors to have to help assess if we were successful in our attempts to share these skills and tools. I want to share some kind words we received via email,

> The workshop was a real help in getting started with R. I’m really glad that I attended.

and survey responses about _things that were considered major strengths of the workshop_

> purposefully having us make mistakes and learning how to correct them -strategies for trouble shooting

> HackMD was critical to staying on track Very open to on-going questions and discusssions on how applied to different disciplines

> Showed us ways to apply these techniques to our own research.

> I got exposure to coding and it was amazing how relevant it was to the type of work I've done before in excel and how easier it is to work on in R vs. excel.

I look forward to reviewing the rest of the survey information, especially the section on what we can do to improve. It's important for all instructors to understand we can always get better, and we are very thankful for the information that the learners provided. 


### Future learning

The DSI will continue hosting weekly community coding sessions, short workshops and seminars throughout the Fall 2018 semester. We are always looking for people interested in speaking and sharing their knowledge. If your group would like to do a personalized set of trainings please contact us for details. 

----
### Links

* https://software-carpentry.org/
* https://www2.archivists.org/prof-education/faculty/reid-otsuji
* https://librarycarpentry.org/
* https://www.rstudio.com/
* https://github.com/
* https://support.rstudio.com/hc/en-us/articles/200526207-Using-Projects
* https://hackmd.io/sfN_8XIlQxWQn2UFRZ0kXA?view
* https://carpentries.org/
