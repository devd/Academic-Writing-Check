## Academic Writing Check ##

### Introduction ###

This script attempts to find common errors in academic writings. This is focused only on academic writing in latex, but most things should work on any ASCII text. We don't attempt to do any sort of latex parsing currently(maybe someday).

Currently the script tries to find the following issues:    

-  __passive__ : Passive voice, colored red by default.
-  __dups__    : Duplicate words: 'the the' across 2 lines, colored purple by default
-  __weasel__  : Weasel words like {various, many}, colored green by default
-  __abbr__    : Wrong abbreviations like i.e and et. al., colored blue by default
-  __typography__: Common typography errors like \footnotes before a punctuation, numbers without comma, URLs not typeset with \url, and others. colored yellow default
- __strunk__ : Issues that Strunk and White refer to in their classic. Currently, only has a sublist of words from Chapter IV. colored cyan by default.

The script accepts options via the standard UNIX style:
     
     --no-{option} 
     
where {option} is one of the things in __bold__ in the above list. The script also ignores lines beginning with a % as a helper. It outputs filename and line number with the offending issues marked in color.

You can also send in a -d to disable all checks. Checks will need to be explicitly enabled. Thus -d --abbr will only look for abbr errors.

Colors can be specified with 

    --{option}_color={color} --def_color={color}

where {option} is one of the options above, and {color} is one of

    ('black','red','green','yellow','blue','purple','cyan','white').
    
You can also prefix the color name with dark to get a darker shade.
The def_color option sets the color of unmarked text.

Thus, 

    --passive_color=darkgreen

will mark passive words with dark green color.


The script can be called in multiple ways:

*  ./checkwriting &lt;files&gt;
*  ./checkwriting &lt;directory&gt; : In this case the script uses all &#42;.tex and &#42;.bbl files in the directory. If it doesn't find any, then it waits for input from stdin.
*  ./checkwriting : With no files, the script waits for diff style input on STDIN. I use it this way often. Say, you made some changes to the manuscript. Just do git diff | ./checkwriting and you only have to look at new errors.

### Notes on the warnings ###

Some of the warnings are obvious, some aren't. The non-obvious ones are discussed here.

* The typography warning: "add a \@" is to let LaTeX know when its end of line.
  LaTeX assumes that a period ends a sentence, unless it follows a capital
letter in which case it assumes that it is an abbreviation. So to let LaTex know that 'iOS.' is really end of sentence, write 'iOS\@.'


### Acks ###
The original idea and code for this came from Matt Might's [blog](http://matt.might.net/articles/shell-scripts-for-passive-voice-weasel-words-duplicates/)

Here are some other links that might be useful (and might be integrated
into awc someday):

* [Common Errors in Technical Writing](http://www.ece.ucdavis.edu/~jowens/commonerrors.html) - John Owens , UC Davis
* [Effective Scientific Electronic Publishing](http://www.cl.cam.ac.uk/~mgk25/publ-tips/) - Markus Kuhn, Cambridge
* Strunk and White is now [free online](http://www.bartleby.com/141/strunk1.html)
* [How to write a great research paper](http://research.microsoft.com/~simonpj/papers/giving-a-talk/writing-a-paper-slides.pdf) - Simon Peyton Jones, MSR Cambridge
* [Everyone Can Write Better (and You Are No Exception)](http://homepages.ed.ac.uk/martinc/msc/doc/hc.pdf) - Herbert H. Clark


And to put it all in perspective, [Stephen Fry's monologue on Language](http://www.youtube.com/watch?v=J7E-aoXLZGY)

Tip: If you want to pipe the output, less -R is useful to maintain the
colors.

