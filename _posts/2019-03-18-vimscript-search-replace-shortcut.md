---
layout:     post
title:      "Vimscript: a search/replace shortcut"
date:       2019-03-18 08:11:00
summary:    How I avoid typing out super-long variable names.
categories: blog
---

I _love_ Vim, but one thing that drove me crazy for a long time was search/replace. It's easy to search for the the
current word under the cursor - just press `*` in normal mode to start cycling through matches. But replacing that
word can be annoying if it's really long. You end up with a lot of keystrokes.

```
:%s/mySuperLongVariableName/myNewSuperLongVariableName/gc
```

One way to save a few keystrokes is to yank `mySuperLongVariableName` and paste it into the search command. You can
do this by yanking the text you want to replace (e.g. select in visual mode and press `y`), typing `:%s/` to start the
search, then pressing `<c-r>` followed by `"` to paste the search text.

But that's still an annoying number of steps. I wrote the script below to start a search/replace command by
simply pressing `<c-s>`. It grabs the current word under the cursor and prompts for the rest of the replace command.
In other words, pressing `<c-s>` eliminates need to type `:%s/mySuperLongVariableName/`. Just fill out the rest. 

```vimscript
function! SearchReplaceCurrentWord()
  let cword = expand('<cword>')
  let userInput = input(':%s/' . cword . '/')
  if len(userInput) > 0
    exe '%s/' . cword . '/' . userInput
  endif
endfunction
noremap <c-s> :call SearchReplaceCurrentWord()<CR>
```
