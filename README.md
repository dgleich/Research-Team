# David's Research Team Notes and Frequently Addressed Questions

### What is this?
It's an overview of things that you should understand as a student if you are going to work with me.
It's also a place where you should look for answers before asking questions. 
It's also a place where you should look before writing papers.
It is not exhaustive. Some people would call it a lab manual, but I don't run a lab.

## Is there any prerequisite requirement for being your student?

There are zero _requirements_ to working with me. But my standards are very high. I expect people to be able to learn anything they need to pursue interesting research. That might be programming. That might be some esoteric concept in theory. That might be how to make a video. I can't give a list of all of these things and you need to be able to learn to do them yourself. 

As a general suggestion (and this goes for just about any professor), if you've taken a class with me, and enjoyed how I teach, and did well in the class, it probably means we'd be able to have a productive relationship.

### If I'm a high school student, undergraduate, or master student, can I work with you?

Most things like this don't work out. Some do. See above. 

## David's Philosophy
It's your PhD. You are responsible. I am here as a guide, advisor, or mentor. I am not a _boss_ or a _manager_ or a _leader_. Better to think of me as a _coach_. I'm here to help you become better. I want you to develop into an independent researcher that is able to pose interesting questions and understand when and how you should try and answer them. 

## What do I need to know? 

- You need to be on the research team slack! 

- If you need help with grad school / program requirements, don't come to me. 

- You get a pay raise after completing your Plan of Study (Purdue). You get another pay raise after your Prelim (Purdue).

- Nominally, an RA should work 20 hours per week.

### Weekly status reports 

You should have a channel on slack for weekly reports. If you don't have this, let me know. Generally these should be done sometime before Monday at noon. I'll bug you if you haven't done one in a few weeks. Sometimes these aren't required if there is another reporting requirement associated with your work. But the idea is that I want to track to make sure you aren't stuck on the same thing week after week. 

### Why don't we have regular meetings?

Progress doesn't come in weekly intervals. Some weeks you are working on understanding something in classes. Some weeks you are working on a technical proof but don't have progress. Some weeks you are working on code and just need to keep at it. This is all okay, in which case a meeting wouldn't be helpful. I'd rather have longer, more in-depth meetings when there are interesting things to discuss rather than short, useless meetings. 

### What books / articles / etc. should I read?
- Anything by Edward Tufte. 
- Anything by Nick Trefethen.

## Contacting me

Please contact me on slack. If you don't hear back from me soon, please send me another note. It's okay. I'm busy. I forget things. I have kids demanding my attention. I have research reports and grants and deadlines demanding attention. I _like_ responding to people on the research team, but that doesn't mean I can always do it. So please do feel free to bug me.

### If you need a letter
Let me know as soon as possible.

Please do bug me about it.


### If you need an answer in a hurry
Then bug me repeatedly. 

## Writing 

### Authorship
Authorship on papers and ownership of ideas should be discussed as early as possible. As a rough guide, an author should be anyone that contributed meaningfully to the intellectual effort of the paper. 

Datasets are a grey area. 

Authorship does not include:
- Help with reading the paper for improvement
- Pointing out flaws
- Being a helpful member of the team

If you believe you should have authorship on something that you are not the lead / obvious person responsible for, make sure I know about it as soon as possible. 

See the section of collaboration also. 

### Deadlines
Papers should have reasonably complete drafts at least one week before any deadline. (Sadly, sometimes we need to make exceptions to work with collaborators.)

### Feedback

Plan to ask your fellow team-mates for feedback as early as possible. At least one or two days before any deadlines. (See above, but this type of feedback does not constitute authorship, and you are all expected to help each other out!)

### Latex Quirks
Always use `\varepsilon` and never `\epsilon`; consider the macro `\newcommand{\eps}{\varepsilon}`.

Consider using [my macros and pacakges](https://github.com/dgleich/dgleich-latex)

For citations use `Gleich's article on PageRank~\cite{Gleich2015}`. i.e. include the LaTeX `~` character to prevent a line break between the citation and the text.

For citations, use Author-Year whenever possible

Don't use `\right` and `\left` unless you are in display mode. Consider `\bigl` `\bigr` and variants `\biggr`. [See more](https://tex.stackexchange.com/questions/19480/why-use-the-control-sequences-bigl-biggl-bigr-or-biggr-as-i-can-always-us) 

### Submitting to ArXiv 

- use the arXiv minimal license. 

## Making nice looking plots.

You absolutely need to understand the difference between vector and raster formats.

Vector formats should be used whenever possible. 

You absolutely need to understand the interaction between figure dimensions (inches, centimeters) and programatic sizes (points, pixels) and package dimensions. 

Some helpful knowledge
- a _point_ is 1/72th of an inch. One point is a good generalize size for a line; a two point line is thick. 
- a _pixel_ is 1/96th of an inch. 
- 3 points is a small marker, 6-8 points is a medium marker, 10-15 points is a large marker. Why are you using larger than 15 points? 
- 12 point type (12/72") is very readable. 10 point type is readable. 8 point type is usable (footnotesize). 

As a rough guide, start by making 3in by 3in figures (8cm by 8cm). Use 10 or 11 point font sizes for axis labels. Use 8-9 point font sizes for axis ticks. 

Style info. 
- Look at [Observable's Plot library](https://observablehq.com/plot/) for beautiful designs.
- Look at [ggplot](https://ggplot2.tidyverse.org) for beautiful designs.

_Keep it simple._ Complexity should be used as a last resort. Use package defaults if they look good. 

### Examples

#### Here's a minimal example
```
using CairoMakie
# Makie uses "pixels" as the default unit, so 3in = 3*96
f=Figure(; size=(3*96, 3*96), figure_padding=0) # set padding to 0
ax = Axis(f[1, 1])
lines!(ax, randn(10), randn(10))
save("test.pdf", f) 
```


#### Here is an example of something like Observable Plot in Makie

```
using CairoMakie
f=Figure(; size=(3*96, 3*96), figure_padding=0) # set padding
ax = Axis(f[1, 1], alignmode=Outside())
lines!(ax, randn(10), randn(10), label="Line 1")
lines!(ax, randn(10), randn(10), label="Line 2")
lines!(ax, randn(10), randn(10), label="Line 3")
hidespines!(ax)
lblt = Label(f[0,1], "↑ Response", 
  rotation=0, halign=:left, valign=:bottom,
  tellwidth=false, fontsize=11,
  alignmode = Outside())
lblr = Label(f[2,1], "Variable →", 
  rotation=0, halign=:right, valign=:top,
  tellwidth=false, fontsize=11)
rowgap!(f.layout, 0)  
ax.xticklabelsize[] = 11
ax.yticklabelsize[] = 11
#Legend(f[3,1], ax, fontsize=11, halign=:right, valign=:top)
f[-1, 1] = Legend(f, ax, framevisible = false, orientation = :horizontal,
  labelsize=11, padding=0)
Label(f[3,1], "This could be some explanatory text", halign=:left,
  tellwidth=false, fontsize=11, font=:bold)
rowgap!(f.layout, 0)
f
```

## Travel

## Travel

Use the [Concur portal](https://one.purdue.edu/task/all/concur) to submit a travel request. You enter the dates and destination, and Concur will give you recommended hotels/flights and travel info. Follow the instructions to submit an official request through the portal. To submit, you will need an an account code specifying where the funding is coming from (ask David for this). A person has to go in and approve the request, so it isn't instantaneous.

Concur requests: Try to book with the Concur-recommended hotels/flights as they generally give better rates. You can either book through the portal or book separately, though in either case you have to fill out a request. 

Per diem: You get a per diem calculated by Concur for meals for the days you are out of town (including the travel days to and from). 

Reimbursement: Email the CS business office (csbo@groups.purdue.edu) with receipts and the expense report (see below). You always need to submit receipts for the hotel, flights, and rental cars. You don't need to submit receipts for meals, etc. unless an expense is over $75. Reimbursement is by direct deposit and usually takes a couple weeks. 

Expense report: answer the following along with a list of expenses.
- Full Name
- Date & time you left home
- Date \& time you returned
- Each city you stayed overnight in
- Business Purpose
- How did you get to the airport
- Airport Used
- Did you use a Rental vehicle?
- Did you drive to place of business? If yes, please list business location address
- Dates of meals provided by the conference/host
- Department name \& account number (IO or WBSE) to charge travel

See the [official travel regulations](https://www.purdue.edu/procurement/travel/regulations/index.php) for more info.

## Reviewing

TBD 

### Reviewing for journals
Please don't accept an invitation to review at a journal without telling me. And definitely ask. 

### Serving on PCs at conferences
I don't feel it's appropriate for PhD students to be PC members at conferences. This is, evidently, not a widely shared opinion. If you are in your final year and _all but defence_ I am open to suggesting you as a reviewer / PC member as a conference. 

## Collaboration (inside and outside group)
Collaboration is encouraged! Tell people about your research. If you think you can do more with a team 

- I should generally be an author on anything you do. There can be exceptions but you want to discuss these with me as early as possible. 

## Access to computers / servers

TBD

- This needs to be requested from David, it is not automatically given.
- Information on David's computers is given in the `#computers` channel on slack.

## Coding

Apparently, ``David Likes Julia'' is a meme in the CS department.

This is true.

But what you don't know is that ``David Likes Matlab'' was a meme when David was a grad student. I've had many discussions with Cleve Moler about why Matlab is fantastic. 

Julia is now better than Matlab for the types of research I like to do. Why?

- Almost as easy as python
- Almost as fast as C++
- No weird interfaces between C code and higher level languages
- You won't spend your time dealing with compilers, or JIT packages, or ...
- It scales up to big problems. 

There are still loads of issues with Julia. 
- You will spend a lot of time _precompiling_
- Plotting is always an issue (but as of 2024, [`Makie.jl`](XXX) solves most of the issues).

But the rule is: 
- You may use whatever language you feel like using, but Julia is probably the best for the kind of work we do.

### Software packages
Make sure things have good documentation! Make them easy to use! 

### Be idiomatic

Always write software like the other software around it. Le


## General advice to students

### Be skeptical of your own ideas

### Figure out how to figure out ideas that won't work quickly
In my observation, what often distinguishes the most successful students from others is not that they have _better_ ideas, but it's that they are able to _eliminate_ ideas from a search space more quickly. This is a skill you can try and cultivate. Try and show that an idea _won't_ possibly work and _isn't_ worth investing further time in. 

### Kanban boards are super duper helpful
Read the [Phoenix project](https://www.amazon.com/Phoenix-Project-DevOps-Helping-Business/dp/1942788290)

Do then on paper first. Then consider apps. I still use paper when I need to really get things done. 

### [Embrace the grind](https://jacobian.org/2021/apr/7/embrace-the-grind/)

## Group meetings

## Questions over the years

### Are we encouraged to do internships?

### How open should we be to people outside the group about our research?

### Any general advice on how to speed up typing?
- Practice, practice, practice
- Use voice dictation software
- Don't type equations, type what you want the equations to say, then fill them in later. 

### Do you have any recommendations for general research/career philosophy?

Here are some books/articles that may be helpful, they have their own bias, but they offer more perspectives.

A PhD is not enough.
