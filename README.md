post-mode
=========

This is a major mode for use with [mutt](http://www.mutt.org/), slrn, or most
email and newsreaders that allow you to use an external editor.

Installation
------------

Add the following line to the .emacs(.el) file in your home directory:

    (load "/your/local/path/to/this/file/post")

Note that you can omit the ".el" from the file name when calling load.

If you want to make it available to all your users, type `\C-h v
load-path RET`, pick an appropriate directory for `post.el`, and modify
your sitewide `default.el` to `(require 'post)`.

You may find the latest version of this mode at
http://github.com/zedinosaur/post-mode/
