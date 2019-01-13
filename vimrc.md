func SetTitle()

    if &filetype == 'sh'
	call setline(1,"#!/bin/sh")

	call setline(2,"")

	call setline(3, ":<<!") 

	call setline(4, "Copyright (C) ".strftime("%Y")." Topotek Ltd. All rights reserved.")

	call setline(5, "")

	call setline(6, "Mail: hyt.lyy@gmail.com") 

	call setline(7, "")

	call setline(8, "File Name: ".expand("%:t"))

	call setline(9, "")
	
	call setline(10, "Author: hyt")

	call setline(11, "")

	call setline(12, "Created Time: ".strftime("%c")) 

	call setline(13, "")

	call setline(14, "Description: ") 

	call setline(15, "")

	call setline(16, "!")

	call setline(17, "")

	call setline(18, "")

	normal G

    elseif &filetype == 'python'

        call setline(1, "#!/usr/bin/env python3")

        call setline(2, "# -*- coding: utf-8 -*-")

	call setline(3, "'''") 

	call setline(4, "Copyright (C) ".strftime("%Y")." Topotek Ltd. All rights reserved.")

	call setline(5, "")

	call setline(6, "Mail: hyt.lyy@gmail.com") 

	call setline(7, "")

	call setline(8, "File Name: ".expand("%:t"))

	call setline(9, "")

        call setline(10, "Author: hyt")

	call setline(11, "")

	call setline(12, "Created Time: ".strftime("%c")) 

	call setline(13, "")

	call setline(14, "Description: ") 

	call setline(15, "")

	call setline(16, "'''")

	call setline(17, "")

	call setline(18, "")

	normal G

    endif

endfunc  

autocmd BufNewFile *.c,*.py,*.sh exec ":call SetTitle()"  

" ------------------- configure of YouCompleteMe -------------------

"call youcompleteme#GetErrorCount()
"call youcompleteme#GetWarningCount()

let g:ycm_log_level = 'info'
let g:ycm_auto_trigger = 1
let g:ycm_enable_diagnostic_signs = 1
let g:ycm_enable_diagnostic_highlighting = 1
let g:ycm_echo_current_diagnostic = 1
let g:ycm_error_symbol = '>>'
let g:ycm_warning_symbol = '>*'
let g:ycm_key_list_select_completion = ['<TAB>', '<Down>']
let g:ycm_semantic_triggers =  {'python':['.']}



set noswapfile                " I don't like swap file

set nocompatible              " be iMproved, required

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

" 解决插入模式下delete/backspce键失效问题
set backspace=2

" About NREDtree
" autocmd vimenter * NERDTree
" map <C-n> :NERDTreeToggle<CR>
map <F2> :NERDTreeToggle<CR>
let NERDTreeWinPos="right"
let g:NERDTreeDirArrowExpandable = '▸'
let g:NERDTreeDirArrowCollapsible = '▾'

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

Bundle 'scrooloose/nerdtree'

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
" Put your non-Plugin stuff after this line

