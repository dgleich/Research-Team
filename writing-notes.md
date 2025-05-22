Latex notes

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

* Learn how to use latexdiff

* Learn when to use package subdepth 


