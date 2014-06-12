
This is a short how-to on how to integrate awc and vim to get automatic checking
of your latex files in vim, as you type. This is a very hacky way, and any
suggestions for a cleaner mechanism are welcome. Please send a patch or email
me. Despite of the hacky nature, I find this extremely useful, and strongly
urge you to try it out.

* First, install [Syntastic](http://www.vim.org/scripts/script.php?script_id=2736)

* Put checkwriting.vim (from this repo) in ~/.vim/bundle/syntastic/syntax_checkers/tex/

* Make sure that the checkwriting file is executable and exists somewhere in your $PATH


Syntastic will mark the erroneous lines with red double arrow at the left, and scrolling to
that line should show the error at the bottom of the screen, with the errors
marked with a double asterisk. Note that you have to save the file once to get syntastic running.

If someone knows how to make vim show the errors in color, that would be great!


