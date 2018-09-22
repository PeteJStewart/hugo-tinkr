+++
date = 2018-09-22T08:06:03+01:00
publishdate = 2018-09-22T08:06:03+01:00

title = "The Importance of Documentation"
tags = []

description = ""

type = "article"

styles = ["https://fonts.googleapis.com/css?family=Noto+Serif+JP:500,700"]

[amp]
elements = []

[article]
lead = "This article discusses the impact not having proper documentation can have on website performance and load time."
category = ""
related = []

[author]
name = "Pete Stewart"
image = "/img/authors/80dHNPJ7P3vme7tC5po0-small.jpg"
bio = ""
homepage = ""

[image]
src = "/img/articles/importance-of-documentation-thumb.png"
title = ""
author = ""
link = ""
license = ""
licenseLink = ""

[sitemap]
changefreq = "monthly"
priority = 0.5
filename = "sitemap.xml"

+++
Properly documenting a project is an often debated subject, as developers, quite rightly want to focus on development, and feel another developer could understand their code if they were to read through it.  In an ideal world where all developers are equally skilled and have plenty of time to read through the whole project codebase, this would be fine.

In the real world, this is usually not the case.  Developers all have different levels of skill and experience, and usually have a time schedule to stick to, so can’t always read through many lines of code.

For these reasons alone, documentation is important.  But there are also a number of other important reasons why we should consider writing documentation.  Following I’ll go through a few of these reasons and discuss the impact some of them can have on the performance of a project.

Content

Ease of collaboration
Speed of development
Reduction of errors
Reduction of repetition and bloat
Increased reusability
Increased performance

Ease of collaboration

It’s always a pleasure when you join or take on a project and it’s well documented!

There is an argument to say well written, functioning code is documentation in itself...but in my experience, this relies on there being at least two highly skilled and experienced developers involved; one to write the code, and a second developer who can fully understand it all.

I’m sure like myself, many developers have written code that they’ve later come back to and struggle to fully understand how it works. 

This is even more common when writing high performance code, as code that is easy for humans to read is often slower for computers to run.

That said, the main purpose of documentation is to ease development/collaboration and increase performance.  So you don’t want to be spending more time documenting code than you are writing it.

It’s for this reason I usually opt for a system that allows you to generate documentation from well commented code, such as sassdoc.
Speed of development

If there is a single developer working on just one project, then this isn’t really applicable, as the developer is likely to be able to remember and understand all the code without much thought. 
This partly depends on the size of the project, though.  As if the project is very large, one developer can even lose their place and therefore lose time trying to figure out what’s going on.

For example, I’ve worked on projects in the past that have had thousands of lines of code in half a dozen languages.  I’ve spent large amounts of time working on a specific areas of the project and then struggled to pick up other sections when needed.

A more common scenario is a project that a few people work on or that moves from developer to developer.  In this case, consistent documentation allows all developers to work on any section without the delay of understanding all the code.
Reduction of errors

As mentioned earlier, developers usually have some time restraints, and therefore can’t always take the time to read through the whole codebase of a project.

This is usually OK, but can occasionally introduce unforeseen errors or bugs.  Sometimes these are bugs that aren’t even picked up by the developer that introduced them.

Proper documentation and where applicable automated tests & continuous integration (CI) can really help prevent this from happening.
Reduction of repetition and bloat

DRY is a principle as developers we should always be thinking about.  Centralised documentation helps to flag up repetition in code. 
When I say centralised, I’m talking about something like what is generated by sassdoc and similar documentation generators.

In-code comment documentation doesn’t cut it here, as you would still need to know about the code to see it.  Where as, when you have all your helper functions in one place, you can easily see if the functionality already exists.
Increased reusability

This is a slightly tenuous point,  as it’s not always the case.  But I personally find that documenting my work encourages me to write better code and therefore modular, reusable code.

I find explaining what a section of code does, forces me to think about it’s place in the codebase and therefore I refine the code itself.
I also find being able to see all of the code documented in one place makes it easier to spot when and where code can be refined and then increase its reusable.
Increased performance

When I say performance, I mean in a broad sense:

The performance of the developers and the speed they can work at.
The performance of the code and the speed the code runs e.g. load times, and server costs.
The performance of the actual project.  How well the project achieves its aim.  This could be conversions, sales, sign-ups, users retention, etc.

Documentation isn’t going to solve all problems you may experience with these areas, but it does play its part in improving the overall performance.  Developers can work without learning overheads, code bloat is reduced and user experience is improved with a faster and leaner project.