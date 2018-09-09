function HeaderPython()
	call setline(1, "#!/usr/bin/env python3")
	call append(1, "# -*- coding: utf-8 -*-")
        call append(2, "# Hyt @ " . strftime('%Y-%m-%d %T', localtime()))
        normal G
	normal o
	normal o
endf
autocmd bufnewfile *.py call HeaderPython()


set nocompatible              " be iMproved, required
filetype off                  " required

set number
" set ruler
" autocmd InsertLeave * se nocul
" autocmd InsertLeave * se cul

set showcmd
syntax on

set cursorline
set cursorcolumn

set encoding=utf-8

" About Search
set hlsearch
set incsearch
set ignorecase

" About Indent
set autoindent
set cindent


"""""""""""""""""""""""""""""""""""""""""""""""""""""""
"
" set the runtime path to include Vundle and initialize
"
"""""""""""""""""""""""""""""""""""""""""""""""""""""""
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()

" let Vundle manage Vundle, required
Plugin 'VundleVim/Vundle.vim'

" Auto-Completion
Plugin 'Valloric/YouCompleteMe'
Plugin 'Raimondi/delimitMate'

" Beautiful Status bar
Plugin 'bling/vim-airline'
set laststatus=2

" All of your Plugins must be added before the following line
call vundle#end()            " required
filetype plugin indent on    " required

" Brief help
" :PluginList       - lists configured plugins
" :PluginInstall    - installs plugins; append `!` to update or just :PluginUpdate
" :PluginSearch foo - searches for foo; append `!` to refresh local cache
" :PluginClean      - confirms removal of unused plugins; append `!` to auto-approve removal

" see :h vundle for more details or wiki for FAQ
" Put your non-Plugin stuff after this line.
