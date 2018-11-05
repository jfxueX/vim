# [How to use Syntastic plugin for Vim][1]

Posts by Ashwin

November 6, 2014

[1]: https://codeyarns.com/2014/11/06/how-to-use-syntastic-plugin-for-vim/


[**Syntastic**](https://github.com/scrooloose/syntastic) is a plugin for
**Vim** that can check the currently displayed code for **syntax
errors** and mark those lines with the error messages. This is a type of
feature that is typically available in an IDE. This is useful since
compile or run-time errors in C++ (or any other language) can be
discovered while writing the code without going outside Vim.

  - I use Pathogen to install Syntastic. This is as simple as cloning
    the [Syntastic Github
    repository](https://github.com/scrooloose/syntastic) in my
    `.vim/bundle` directory.

  - If you have GCC and G++ installed to their default directories, then
    Syntastic should work immediately in any C++ file. Detailed help is
    available for Syntastic by using the command `:help syntastic`.

  - Open any C++ file and see what Syntastic knows about this file by
    using the command `:SyntasticInfo`.

  - Create a few syntax errors in a C++ file and save the changes with
    `:w`. You should be able to see those lines marked with special
    characters in the left column of the editor window. Navigating the
    cursor to that line shows its error at the bottom of Vim, below the
    statusline.

  - To jump between the lines with errors, the errors need to be first
    loaded into the Vim location list. To do that, use the command
    `:Errors`. A new subwindow appears at the bottom named *Location
    list* and you can see the errors listed there. Switch to that
    window, move to an error and press `Enter` to jump to that error
    line in your code.

  - Once the errors are loaded into the Vim location list, you can
    directly jump between the lines with errors in your code using the
    Vim commands `:lnext` and `:lprev`.

  - If you have installed Tim Pope’s unimpaired plugin, you can jump
    between errors using `]l` and `[l`.

  - To setup Syntastic to automatically load errors into the location
    list, add this line to your `.vimrc`:

```vim
let g:syntastic_always_populate_loc_list = 1
```

  - By default, Syntastic does not check for errors when a file is
    loaded into Vim. To enable that, add this line to your `.vimrc`:

```vim
let g:syntastic_check_on_open = 1
```

  - By default, Syntastic checks for errors whenever you save the file.
    To disable this, add this line to your `.vimrc`:

```vim
let g:syntastic_check_on_wq = 0
```

  - To explicitly invoke syntax check on the current file, use the
    command `:SyntasticCheck`.

  - By default, Syntastic uses arrow symbols to indicate line with
    error. To spice things up, you can specify any Unicode symbol as the
    symbol. For example:

```vim
let g:syntastic_error_symbol = "✗"
let g:syntastic_warning_symbol ="<img draggable="false" class="emoji" alt="⚠" src="https://s0.wp.com/wp-content/mu-plugins/wpcom-smileys/twemoji/2/svg/26a0.svg">"
```

