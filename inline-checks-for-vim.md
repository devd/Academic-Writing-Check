
This is a short how-to on how to integrate awc and vim to get automatic checking
of your latex files in vim, as you type. This is a very hacky way, and any
suggestions for a cleaner mechanism are welcome. Please send a patch or email
me.

* First, install [Syntastic](http://www.vim.org/scripts/script.php?script_id=2736)
* Overwrite the default tex syntax checker with AWC. There is a tex.vim present in this repository that you can use directly.

    wget https://raw.github.com/devd/Academic-Writing-Check/master/sample.awc_wordlist ~/.vim/bundle/syntastic/syntax_checkers/tex.vim 
    # Note that this will overwrite the default lacheck syntax checker.

* Make sure that the checkwriting file is executable and exists somewhere in your $PATH


Syntastic will mark the erroneous lines with red double arrow at the left, and scrolling to
that line should show the error at the bottom of the screen, with the errors
marked with a double asterisk.

If someone knows how to make vim show the errors in color, that would be great!


