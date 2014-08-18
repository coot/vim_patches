[VIM](http://www.vim.rog) patches
=================================

This repository contains vim patches that I use.  Most of them I wrote and they are waiting in the famous `:help todo` file.

`argadd.patch`
--------------
by *Marcin Szamotulski*

Add default argument to `:argadd` command:  `:argadd` will work like
`:argadd%`.

`arglists.patch`
----------------
by *Marcin Szamotulski*

One of my patches, which was recenlty accepted (version `7.4.312`), adds
`arglistid()` function which returns arglist `ID` (0 for global arglist).  This
patch adds new syntax to `:arglocal` command: `:Narglocal` will use the arglist
with ID `N`.  There is also another command `:arglists` which lists argument
lists in the current tab page (or all tab pages) with theirs IDs.

`count.patch`
----------------
by *Marcin Szamotulski*

This patch adds counts for `:close`, `Ctrl_Wc`, `:hide`, `Ctrl_Wq`, `:only`,
`Ctrl_Wo`  ... commands (ex- and normal-).  For example `3<c-w>q` will quit
window number 3, you can also do `:3quit`, `:.quit` (quit current window),
`:-quit` (quit previous window), `:+quit'`, `:$quit` (quit last window).

It also changes the count for `:argedit`, `:argument`, `:argdelete`:
```
:$argu	" edit last argument
:-argu	" like :next
:+argu  " like :previous
:.,$argdelete	" delete all arguments from the current one till the last one
:.argdelete
:argdelete	" delete the current argument
:%argdelete	" delete all files from the current argument list
```

`buffer.patch`
--------------
by *Marcin Szamotulski*

This patch adds `+cmd` argument for `:buffer`, `:sbuffer`, `:bnext`,
`:bprevious`, ... and all friends.  See `:help +cmd`.

`color-digraph-list.patch`
-------------------------
by *Dominique Pellé*

Add colors to `:digraph` output, useful when searching for a digraph.
