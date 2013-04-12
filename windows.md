
The whole code is written in Perl, so it should work on all platforms where Perl runs.
Getting things to work on Windows is a bit tricky.

* First, install perl. I used [Strawberry Perl](http://strawberryperl.com/).
* The script uses ANSI escape sequences to highlight  the problematic text. The default Windows terminal 
(cmd) does not support ANSI escapes. Instead, download [ConEmu](https://code.google.com/p/conemu-maximus5/).
* Turn on support for [ANSI escapes in ConEmu](https://code.google.com/p/conemu-maximus5/wiki/AnsiEscapeCodes). I only
had to turn on ''Inject ConEmuHk'' in ''Features''

After this, download checkwriting to any directory of your choice and run
```bash
perl checkwriting <path to tex file>
```
