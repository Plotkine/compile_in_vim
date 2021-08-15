# compile_in_vim

## How to create a shortcut to compile/execute your code from inside vim

So you like vim but you are tired of switching to another terminal to compile and run your code?

You can create vim shortcuts to map keys to vim and/or shell commands by writing into `~/.vimrc`:

`map <[key]> <CR>:[vim command 1]<CR>:[vim command 2]<CR>:...<CR>:![shell command 1]; [shell command 2]; ...<CR>`

### Tips
- Use `;` instead of `<CR>:!` between your shell commands if you want to see their outputs
- The variable `%` contains the name of the file

### Example with C code (program.c -> program.exe)

Write these lines into `~/.vimrc`:

- `map <F8> :w<CR>:!name=$(echo % \|cut -d'.' -f 1); gcc ${name}.c -o ${name}.exe -std=c89 -Wall<CR>` (saving and compiling)

- `map <F9> :w<CR>:!name=$(echo % \|cut -d'.' -f 1); ./${name}.exe<CR>` (saving and running)

**Now press F8 or F9 from inside vim and voilà!**

![Alt text](./show.gif?raw=true "Title")
