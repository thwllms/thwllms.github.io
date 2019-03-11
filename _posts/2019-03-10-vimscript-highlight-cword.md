---
layout:     post
title:      "Vimscript: auto-highlight matching words"
date:       2019-03-10 11:00:00
summary:    Script to toggle auto-highlighting of matching words in normal mode.
categories: blog
---

![:q]({{ site.images }}/toggle-highlight-480.gif)

Here's a small script I cobbled together for my `~/.vimrc`. I use it every single day.
Press `<c-h>` to toggle auto-highlighting of matching words in normal mode.

```vimscript
function! ToggleAutoHighlightMatchingWord()
  if !exists('#ToggleAutoHighlightMatchingWordGroup#CursorMoved')
    exe printf('match IncSearch /\V\<%s\>/',
      \ escape(expand('<cword>'), '/\'))
    augroup ToggleAutoHighlightMatchingWordGroup
      autocmd!
      autocmd CursorMoved * exe printf('match IncSearch /\V\<%s\>/',
            \ escape(expand('<cword>'), '/\'))
    augroup END
  else
    let currentTab = tabpagenr()
    let currentWindow = tabpagewinnr(currentTab)
    exe 'tabdo windo match IncSeach //'
    exe currentTab 'tabn'
    exe currentWindow . 'wincmd w'
    augroup ToggleAutoHighlightMatchingWordGroup
      autocmd!
    augroup END
  endif
endfunction
noremap <c-h> :call ToggleAutoHighlightMatchingWord()<CR>
```
