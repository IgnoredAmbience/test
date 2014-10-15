Gitlab Has Bugs
===============

Let's try to find some!

## Blame mode weirdness ##
So, it is the case that lines beginning with backslash-n (ignoring leading whitespace and %s) strip everything before
them.
```
\n oh noes
```
This is particularly awkward in LaTeX documents due to the proliferation of macros, eg:
```tex
\newcommand{\eh}{??}
%\newcommand{\heh}{!!}
```

Does it do the same mid-line???
Let's try it! \n yep....

How about end of line?
Delete me \n

How about tabs? \t\t tabby good!

Hmm. NUL? \0 oops...
