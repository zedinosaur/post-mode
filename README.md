This is a fork of [post-mode](https://github.com/zedinosaur/post-mode), providing updates, minor bug fixes, improved documentation and configuration information. The url of this fork is: https://github.com/Boruch-Baum/post-mode

post-mode
=========

This is a major mode for use with [mutt](http://www.mutt.org/),
neomutt (https://neomutt.org), slrn (http://slrn.sourceforge.net/), or
most email and newsreaders that allow you to use an external editor.

Installation
------------

1] Add a few lines to emacs init file (usually ~/.emacs).

1.1] If you manually downloaded this file and want to make this
     package available to all your users, type "C-h v load-path
     RET", pick an appropriate system-wide directory for `post.el',
     and modify your sitewide default.el to include:

       (require 'post).

1.2] If you installed this package using your distribution's
     package manager (eg. for debian, apt-get post-el) or using
     the emacs package manager, or if you manually copied this
     file to a directory already on your emacs load path ("C-h v
     load-path" to see):

       (require 'post)

1.3] If you manually copied this file elsewhere and want to
     add that directory to your emacs load path:

       (add-to-list 'load-path "path/to/directory/")
       (require 'post)

1.4] If you manually copied this file elsewhere and don't want
     to add that directory to your emacs load path:

       (load "/your/local/path/to/this/file/post")

     Note that you can omit the ".el" from the file name when
     calling load.

2] Optionally, here are some additional settings to consider
   adding after the above, as a good start to making your user
   experience a bit nicer:

     (defun my-post-mode-hook()
       (setq
         fill-column 72    ; rfc 1855 for usenet messages
         post-signature-source-is-file t
         post-variable-signature-source "~/mutt/.signatures.fortune"
         post-fixed-signature-source    "~/mutt/.signature"
         post-signature-directory       "~/mutt/.signatures/"
         post-signature-wildcard        "sig*"
         post-random-signature-command  "fortune ~/mutt/.signatures.fortune"
         post-kill-quoted-sig t
         post-should-prompt-for-attachment "Smart")
       (footnote-mode)
       (flyspell-mode))
     (add-hook 'post-mode-hook 'my-post-mode-hook)

New in this fork
================

I'm only starting this list in December 2019, so this list will be
missing changes of the previous few years until I go back and look at
the diffs.

* Improved quoting and unquoting of regions: You can now use the
  prefix argument to perform either operation multiple times, and the
  operation automatically autfills, so the result is properly
  formatted.
