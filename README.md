# compile_in_vim
## How to create a shortcut to compile your program from vim

So you like vim but you are tired of modifying your code, then switching to another terminal to compile it and run it?

You can create a shortcut to compile and/or run your code by adding shortcuts into ~/.vimrc:

`map <F8> :w<CR>:![compilation command]<CR> " save and compile`
`map <F9> :w<CR>:![compilation command]; [execution command]<CR> " save, compile and execute`

Example:

`map <F8> :w<CR>:!gcc % -o %.exe -std=c89 -Wall<CR> " save and compile`
`map <F9> :w<CR>:!gcc % -o %.exe -std=c89 -Wall; ./%.exe<CR> " save, compile and execute`

