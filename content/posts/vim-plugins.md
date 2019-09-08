
---
title: "Vim config"
date: 2019-09-07T21:42:23-07:00
draft: true
---

These days, I do most of my work in vim.  In times gone by I would heavily
modify my configuration with snippets of vimscript that I didn't clearly
understand, but recent years have seen the rise of plugin management software;
now I install plugins whose code I don't understand, which seems somehow
better.  I document here my typical plugins, so I may get started quickly in a
fresh environment.

# Plugin manager

I use [VimPlug](https://github.com/junegunn/vim-plug) to manage my plugins.
I've used [Pathogen](https://github.com/tpope/vim-pathogen) and
[Vundle](https://github.com/gmarik/Vundle.vim) in the past, but have settled on
VimPlug for ill-defined reasons.  Installation is simple, as per the README:

```bash
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```

From there, insert a `call plug#begin('~/.vim/plugged')` and a `call
plug#begin('~/.vim/plugged')` in your `.vimrc`, and some `Plug` statements
between them.  Here are some of my favorites.  (All hail tpope.)

# Plug 'tpope/vim-sensible'

Everyone wants all of these settings.  Just a hundred lines of vimscript that
sets great options (indent, syntax, ai, smarttab, wildmenu, etc).

# Plug 'tpope/vim-unimpaired'

Awesome mappings which, unsurprisingly, come in pairs.  Some favorites of mine
include adding blank lines above and below in normal mode, toggling line
numbers, toggling paste, and various encodings/decodings.

# Plug 'tpope/vim-surround'

Surround text with other text (like brackets).  Remove or change surrounding
text.

# Plug 'tpope/vim-vinegar'

Make netrw handier.  (I like the mapping of `-` to go to netrw, or up in the
directory hierarchy, most.)

# Plug 'tpope/vim-rsi'

Use Emacs bindings in insert and command mode.

# Plug 'tpope/vim-abolish'

Smart search/replace.

# Plug 'tpope/vim-commentary'

Use `gcc` to toggle whether something is commented.

# Plug 'mattn/emmet-vim'

Use emmet shortcuts in vim.
