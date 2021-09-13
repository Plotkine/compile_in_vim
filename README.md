# compile_in_vim

## Create shortcuts to compile/execute your code from inside vim

So you like vim but you are tired of switching to another terminal to compile and run your code?

You can create a vim shortcut to map a key to vim and/or shell commands by adding a line in `~/.vimrc`:

`map <[key]> :[vim command 1]<CR>:[vim command 2]<CR>:...<CR>:![shell command 1]; [shell command 2]; ...<CR>`

This way you can bind your compile and run commands to shortcut keys and see the outputs directly from vim

### Tips
- Use `;` instead of `<CR>:!` between your shell commands if you want to see their outputs
- The variable `%` contains the name of the file

### Example with C code (program.c -> program.exe)

Write these lines into `~/.vimrc`

- `map <F8> :w<CR>:!name=$(echo % \|cut -d'.' -f 1); gcc ${name}.c -o ${name} -std=c89 -Wall<CR>` (saving and compiling)

- `map <F9> :w<CR>:!name=$(echo % \|cut -d'.' -f 1); ./${name}<CR>` (saving and running)

**Now press F8 or F9 from inside vim and voilà!**

![Alt text](./show.gif?raw=true "Title")
