Overall writing
==============

How to write
------------

**Just write.** Don't try to be 'efficient' and write only what you think you need. This is a recipe for failure and delay. 

**Don't get attached to your words.** Be ready to throw away all your writing. Words are cheap. Prize clarity of thought and expression. 

**Learn how to edit.** Give your text to an LLM and have them delete big patches. What needs to be added back is essential. Everything else can go!  

**Revisit, revise, and repeat.** Keep refining, editing. 

**If possible, articulate the structure.** See below on hierarchical writing. 

Hierarchical / inverted pyramid writing
------------------------------

Your title summarizes the main point succinctly. 

Your abstract explains your title.

Your intro explains your abstract.

The rest of the paper explains your intro. 

**More information** 
* <https://www.nngroup.com/articles/inverted-pyramids-in-cyberspace/>
  > One of the occupational hazards of getting a Ph.D. is a distinct predilection for the traditional pyramid style of exposition. I normally write the way I was trained to write: starting with the foundation and gradually building to the conclusion. Most research papers and engineering reports open with a problem statement, then review the prior art, and move into a detailed discussion of the different options that are considered and the methods that are used. After plowing through twenty pages of basics the patient reader may find a section entitled results with detailed tables, charts, and statistical tests; and after an additional five pages of this, a page or so of conclusions is reached. Phew...

  I agree. This was one of the things Chen Greif taught me. Get to the point. Most readers are not 
  
* <https://www.poynter.org/reporting-editing/2003/writing-from-the-top-down-pros-and-cons-of-the-inverted-pyramid/>

  > It’s also an extremely useful tool for thinking and organizing because it forces the reporter to sum up the point of the story in a single paragraph. Journalism students who master it and then go on to other fields say it comes in handy for writing everything from legal briefs to grant applications.

  On the other hand
  > The inverted pyramid, its critics say, is the anti-story. It tells the story backward and is at odds with the storytelling tradition that features a beginning, middle, and end. Rather than rewarding a reader with a satisfying conclusion, the pyramid loses steam and peters out, in a sense defying readers to stay awake, let alone read on.

  After writing hundreds of papers, I agree with the first point. Clarity of thought is most important. A useful narrative arc in an academic paper is harder to do well.

The DARPA Questions
-------------------
See <https://www.darpa.mil/about/heilmeier-catechism>. These are useful to help organize your thoughts and ideas. 

1. What are you trying to do? Articulate your objectives using absolutely no jargon.
2. How is it done today, and what are the limits of current practice?
3. What is new in your approach and why do you think it will be successful?
4. Who cares? If you are successful, what difference will it make?
5. What are the risks?
6. How much will it cost?
7. How long will it take?
8. What are the mid-term and final “exams” to check for success? 

Writing frames
--------------

You basically need to pick which frame you are writing in.
* High level where you expect someone with basic knowledge to be able to fill in relevant details without mentioning them.
* Mid level where you expect someone with some expertise knowledge to be to fill in relevant details without mentioning them
* Low level where you are giving all the information to be able to reproduce what you did.

So I like to think of it as:
* People outside the area
* People inside the area
* People who want to do exactly what you did.

So you’d write at a high level in the abstract/intro.
Mid/low level in a methods section.
Low level in an appendix/supplement/etc.

Latex 
=====

All of these are guidelines. There are reasons to ignore them, but they'd better be good reasons. 

* Don't ever use `\epsilon` in latex. Use `\varepsilon`. In fact, define `\newcommand{\eps}{\varepsilon}` and use `\eps`. 

* Don't use subsubsections. Two levels of hierarchy is almost always good enough (unless you are writing a thesis). See <https://web.archive.org/web/20070205200717/http%3A//blogs.sun.com/MartinHardee/date/20040624> 

  This was one of my first notes in the #latex channel on slack. 
  > Just a quick note, I strongly dislike subsubsections in papers… A paper should have two levels of organization: sections, subsections.
  > Books have 3/4 parts/chapters + sections + subsections
  > But try and organize things to avoid sub-sub-sections… A lot of times, these can be replaced with “paragraph” labels as a a section is 1-2 pages, a subsection is 1-2 columns, so a sub-subsection would be 1-2 paragraphs...
  > So try and set things up to use that as your 3rd level (if you need it…)

* Don't have just a single sub-section. i.e. If you have Section 5, Section 5.1. Then you need Section 5.2. Otherwise, Section 5.1 isn't a real subsection. 

* Don't put in extra line breaks between equations. 

* Don't use math in headings

* Don't start sentences with math/equations

* Don't start sentenes with acronyms. 

* Learn how to setup good tables. See <https://www.tug.org/pracjourn/2007-1/mori/mori.pdf>

  Simple idea: 
  Use booktabs, \toprule, \midrule, \bottomrule
  Use tabularx and X columns.

  Generally, multicol and multirow aren't needed.

  Use \smash and \llap and \rlap to just get little adjustments. 

* Learn how to use latexdiff

* Learn when to use package subdepth

  You need subdepth if you have a ton of mixed superscript, subscript pairs.
  Compare $A_X$ vs $A_X^T$ vs $A_X^{}$. Note the alignment on the subscript $X$.
  If you don't want to think about this, just use subdepth. 


