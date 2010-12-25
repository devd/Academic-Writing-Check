## Academic Writing Check ##

This script attempts to find common errors in academic writings. This is focused only on academic writing in latex, but most things should work on any ASCII text. We don't attempt to do any sort of latex parsing currently(maybe someday).

Currently the script tries to find the following issues:    

-  __passive__ : Passive voice
-  __dups__    : Duplicate words e.g. 'the the'
-  __weasel__  : Weasel words like {various, many}
-  __abbr__    : Wrong abbreviations like i.e and et. al.
-  __footnote__: Footnotes look better when written following punctuation instead of before
-  __number__  : Numbers are usually more readable when grouped into threes using commas
-  __url__     : You always want to typeset URLs via \url{}

The script accepts options via the standard UNIX style:
     
     --no-{option} 
     
where {option} is one of the things in __bold__ in the above list. The script also ignores lines beginning with a % as a helper. It outputs filename and line number with the offending issues marked in color. The colors aren't currently configurable, but you can edit the script for that.

The script can be called in multiple ways:
*  ./checkwriting <files>
*  ./checkwriting <directory> : In this case the script uses all *.tex and *.bbl files in the directory. If it doesn't find any, then it behaves as below
*  ./checkwriting : With no files, the script waits for input on STDIN.

The original idea and code for this came from Matt Might's [blog](http://matt.might.net/articles/shell-scripts-for-passive-voice-weasel-words-duplicates/)


