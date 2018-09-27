|<td rowspan=1>   | **keys** | **description**
| -  | -           |-
| <td rowspan=16>**best-searching**
| 1  | `/joe/e`     | cursor set to End of match 
| 2  | `3/joe/e+1`  | find 3rd joe cursor set to End of match plus 1 [C]
| 3  | `/joe/s-2`   | cursor set to Start of match minus 2
| 4  | `/joe/+3`    | find joe move cursor 3 lines down
| 5  | `/^joe.*fred.*bill/` | find joe AND fred AND Bill (Joe at start of line)
| 6  | `/^[A-J]/` | search for lines beginning with one or more A-J
| 7  | `/begin\_.*end` | search over possible multiple lines
| 8  | `/fred\_s*joe/` | any whitespace including newline [C]
| 9  | `/fred\|joe`    | Search for FRED OR JOE
| 10 | `/.*fred\&.*joe` | Search for FRED AND JOE in any ORDER!
| 11 | `/\<fred\>/`     | search for fred but not alfred or frederick [C]
| 12 | `/\<\d\d\d\d\>`  | Search for exactly 4 digit numbers
| 13 | `/\D\d\d\d\d\D`  | Search for exactly 4 digit numbers
| 14 | `/\<\d\{4}\>`    | same thing
| 15 | `/\([^0-9]\|^\)%.*%` | Search for absence of a digit or beginning of line
| 16 | `/^\n\{3}`                    | find 3 empty lines
| 17 | `/^str.*\nstr`                | find 2 successive lines starting with str
| 18 | `/\(^str.*\n\)\{2}`           | find 2 successive lines starting with str
| 19 | `/\(fred\).*\(joe\).*\2.*\1`  | using rexexp memory in a search find fred.*joe.*joe.*fred *C*
| 20 | `/^\([^,]*,\)\{8}`            | Repeating the Regexp (rather than what the Regexp finds)
| 22 | `:vmap // y/<C-R>"<CR>`       | search for visually highlighted text
| 23 | `:vmap <silent> //    y/<C-R>=escape(@", '\\/.*$^~[]')<CR><CR>` | with spec chars 
| 24 | `/<\zs[^>]*\ze>`              | search for tag contents, ignoring chevrons(\zs and \ze regex delimiters :h /\zs) 
| 25 | `/<\@<=[^>]*>\@=`             | search for tag contents, ignoring chevrons(zero-width :h /\@=)
| 26 | `/<\@<=\_[^>]*>\@=`           | search for tags across possible multiple lines(\_ means including newline)
| 27 | `/<!--\_p\{-}-->`                   : search for multiple line comments
| 28 | `/fred\_s*joe/`                     : any whitespace including newline *C*
| 29 | `/bugs\(\_.\)*bunny`                : bugs followed by bunny anywhere in file
| 30 | `:h \_`                             : help
| 31 | `:nmap gx yiw/^\(sub\<bar>function\)\s\+<C-R>"<CR>` | search for declaration of subroutine/function under cursor
| 32 | `:bufdo /searchstr/`                | multiple file search, use :rewind to recommence search
| 33 | `:bufdo %s/searchstr/&/gic`   | multiple file search better but cheating, say n and then a to stop
| 34 | `?http://www.vim.org/`        | search for a URL without backslashing, (first) search BACKWARDS!!! clever huh!
| 35 | `/\c\v([^aeiou]&\a){4}`       | search for 4 consecutive consonants, Specify what you are NOT searching for (vowels)
| 36 | `/\%>20l\%<30lgoat`           | Search for goat between lines 20 and 30 [N]
| 37 | `/^.\{-}home.\{-}\zshome/e`   | match only the 2nd occurence in a line of "home" [N]
| 38 | `:%s/home.\{-}\zshome/alone`  | Substitute only the 2nd occurrence of home in any line [U]
| 39 | `^\(.*tongue.*\)\@!.*nose.*$` | find str but not on lines containing tongue
| 40 | `\v^((tongue)@!.)*nose((tongue)@!.)*$` | ..
| 41 | `.*nose.*\&^\%(\%(tongue\)\@!.\)*$` | ..
| 42 | `:v/tongue/s/nose/&/gic`      | 
| 43 | `'a,'bs/extrascost//gc`       | trick: restrict search to between markers (answer n) [N]
| 44 | `/integ<C-L>`                 | Control-L to complete search term [N]


[Best of Vim Tips](http://zzapper.co.uk/vimtips.html)
