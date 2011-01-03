## Academic Writing Check ##

This script attempts to find common errors in academic writings. This is focused only on academic writing in latex, but most things should work on any ASCII text. We don't attempt to do any sort of latex parsing currently(maybe someday).

Currently the script tries to find the following issues:    

-  __passive__ : Passive voice
-  __dups__    : Duplicate words e.g. 'the the'
-  __weasel__  : Weasel words like {various, many}
-  __abbr__    : Wrong abbreviations like i.e and et. al.
-  __typography__: Common typography errors like \footnotes before a punctuation, numbers without comma, URLs not typeset with \url, and   others.
- __strunk__ : Issues that Strunk and White refer to in their classic. Currently, only has a sublist of words from Chapter IV.

The script accepts options via the standard UNIX style:
     
     --no-{option} 
     
where {option} is one of the things in __bold__ in the above list. The script also ignores lines beginning with a % as a helper. It outputs filename and line number with the offending issues marked in color. The colors aren't currently configurable, but you can edit the script for that.

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
*  ./checkwriting &lt;directory&gt; : In this case the script uses all
*  &#42;.tex and &#42;.bbl files in the directory. If it doesn't find any, then it behaves as below
*  ./checkwriting : With no files, the script waits for input on STDIN.

The original idea and code for this came from Matt Might's [blog](http://matt.might.net/articles/shell-scripts-for-passive-voice-weasel-words-duplicates/)

Here are some other links that might be useful (and might be integrated
into awc someday):

* [Common Errors in Technical Writing](http://www.ece.ucdavis.edu/~jowens/commonerrors.html) - John Owens , UC Davis
* [Effective Scientific Electronic Publishing](http://www.cl.cam.ac.uk/~mgk25/publ-tips/) - Markus Kuhn, Cambridge
* Strunk and White is now [free online](http://www.bartleby.com/141/strunk1.html)
* [How to write a great research paper](http://research.microsoft.com/~simonpj/papers/giving-a-talk/writing-a-paper-slides.pdf) - Simon Peyton Jones, MSR Cambridge


And to put it all in perspective, [Stephen Fry's monologue on Language](http://www.youtube.com/watch?v=J7E-aoXLZGY)



