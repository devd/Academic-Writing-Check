# Use with Emacs

To use checkwriting with compile mode and full coloring add the
following to your configuration.

```
;; enable ansi colors in compile-mode
(defun colorize-compilation-buffer ()
  (when (eq major-mode compilation-mode)
    (ansi-color-apply-on-region compilation-filter-start (point-max))))
(add-hook 'compilation-filter-hook 'colorize-compilation-buffer)
```

Then whenever editing a tex file, use `M-x compile` and type type
`checkwriting .` in the prompt to check all tex files in the
directory.

Also consider using [chktex](http://www.nongnu.org/chktex/) with
[flycheck](https://github.com/flycheck/flycheck).

TODO: Add instructions for checkwriting flycheck support.
