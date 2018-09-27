|<td rowspan=1>   | **keys** | **description**
| -  | -           |-
| <td rowspan=44>**best-searching**
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
| 27 | `/<!--\_p\{-}-->`                   | search for multiple line comments
| 28 | `/fred\_s*joe/`                     | any whitespace including newline *C*
| 29 | `/bugs\(\_.\)*bunny`                | bugs followed by bunny anywhere in file
| 30 | `:h \_`                             | help
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
| <td rowspan=70>**best-substitution**
| 1  | `:%s/fred/joe/igc`            | general substitute command
| 2 | `:%s//joe/igc`                | Substitute what you last searched for [N]
| 3 | `:%s/~/sue/igc`               | Substitute your last replacement string [N]
| 4 | `:%s/\r//g`                   | Delete DOS returns ^M
| 5 | `:%s/\r/\r/g`                 | Turn DOS returns ^M into real returns(if your Text File jumbled onto one line, use it)
| 6 | `:%s=  *$==`                  | delete end of line blanks
| 7 | `:%s= \+$==`                  | Same thing
| 8 | `:%s#\s*\r\?$##`              | Clean both trailing spaces AND DOS returns
| 9 | `:%s#\s*\r*$##`               | same thing
| 10 | `:%s/^\n\{3}//`               | delete blocks of 3 empty lines
| 11 | `:%s/^\n\+/\r/`               | compressing empty lines
| 12 | `:%s#<[^>]\+>##g`             | delete html tags, leave text (non-greedy)
| 13 | `:%s#<\_.\{-1,}>##g`          | delete html tags possibly multi-line (non-greedy)
| 14 | `:%s#.*\(\d\+hours\).*#\1#`   | Delete all but memorised string (\1) [N]
|    |                               | **parse xml/soap**
| 15 | `%s#><\([^/]\)#>\r<\1#g`      | split jumbled up XML file into one tag per line [N]
| 16 | `%s/</\r&/g`                  | simple split of html/xml/soap  [N]
| 17 | `:%s#<[^/]#\r&#gic`           | simple split of html/xml/soap  but not closing tag [N]
| 18 | `:%s#<[^/]#\r&#gi`            | parse on open xml tag [N]
| 19 | `:%s#\[\d\+\]#\r&#g`          | parse on numbered array elements [1] [N]
| 20 | `ggVGgJ`                      | rejoin XML without extra spaces (gJ) [N]
| 21 | `%s=\\n#\d=\r&=g`             | parse PHP error stack [N]
| 22 | `:%s#^[^\t]\+\t##`            | Delete up to and including first tab [N]
| 23 | `:'a,'bg/fred/s/dick/joe/igc` | **VERY USEFUL**
| 24 | `:%s= [^ ]\+$=&&=`            | duplicate end column
| 25 | `:%s= \f\+$=&&=`              | dupicate filename
| 26 | `:%s= \S\+$=&&`               | usually the same memory
| 27 | `:%s#example#& = &#gic`       | duplicate entire matched string [N]
| 28 | `:%s#.*\(tbl_\w\+\).*#\1#`    | extract list of all strings tbl_* from text  [NC]
| 29 | `:s/\(.*\):\(.*\)/\2 \| \1/`   | reverse fields separated by :
| 30 | `:%s/^\(.*\)\n\1$/\1/`        | delete duplicate lines
| 31 | `:%s/^\(.*\)\(\n\1\)\+$/\1/`  | delete multiple duplicate lines [N]
|    |                               | **non-greedy matching \{-}**
| 32 | `:%s/^.\{-}pdf/new.pdf/`     | delete to 1st occurence of pdf only (non-greedy)
| 33 | `%s#^.\{-}\([0-9]\{3,4\}serial\)#\1#gic` | delete up to 123serial or 1234serial [N]
| 34 | `:%s#\<[zy]\?tbl_[a-z_]\+\>#\L&#gc` | lowercase with optional leading characters("use of optional atom \?")
| 35 | `:%s/<!--\_.\{-}-->//`       | delete possibly **multi-line** comments
|    | `:help /\{-}`                | help non-greedy
|    |                              | **substitute using a register**
| 36 | `:s/fred/<c-r>a/g`           | substitute "fred" with contents of register "a"
| 37 | `:s/fred/<c-r>asome_text<c-r>s/g` |
| 38 | `:s/fred/\=@a/g`             | better alternative as register not displayed (not *) [C]
| 39 | `:s/fred/\=@*/g`             | replace string with contents of paste register [N]
|    |                              | **multiple commands on one line**
| 40 | `:%s/\f\+\.gif\>/\r&\r/g \| v/\.gif$/d \| %s/gif/jpg/`
| 41 | `:%s/a/but/gie<Bar>:update<Bar>:next` | then use @: to repeat
| 42 | `:%s/goat\|cow/sheep/gc`     | **ORing** (must break pipe)
| 43 | `:'a,'bs#\[\\|\]##g`          | remove [] from lines between markers a and b [N]
| 44 | `:%s/\v(.*\n){5}/&\r`        | insert a blank line every 5 lines [N]
|    |                              | **Calling a VIM function**
| 45 | `:s/__date__/\=strftime("%c")/` | insert datestring
| 46 | `:inoremap \zd <C-R>=strftime("%d%b%y")<CR>`   | insert date eg 31Jan11 [N]
| 47 | `:%s:\(\(\w\+\s\+\)\{2}\)str1:\1str2:` | Working with Columns sub any str1 in col3
| 48 | `:%s:\(\w\+\)\(.*\s\+\)\(\w\+\)$:\3\2\1:` | Swapping first & last column (total 4 columns)
| 49 | `:%s#\<from\>\\|\<where\>\\|\<left join\>\\|\<\inner join\>#\r&#g` | format a mysql query 
| 50 | `:redir @*\|sil exec 'g#<\(input\\|select\\|textarea\\|/\=form\)\>#p'\|redir END` | filter all form elements into paste register
| 51 | `:nmap ,z :redir @*<Bar>sil exec 'g@<\(input\<Bar>select\<Bar>textarea\<Bar>/\=form\)\>@p'<Bar>redir END<CR>` |
| 52 | `:%s/^\(.\{30\}\)xx/\1yy/` | substitute string in column 30 [N]
| 53 | `:%s/\d\+/\=(submatch(0)-3)/` | decrement numbers by 3
| 54 | `:g/loc\\|function/s/\d/\=submatch(0)+6/` | increment numbers by 6 on certain lines only
| 55 | `:%s#txtdev\zs\d#\=submatch(0)+1#g` | better `:h /\zs`
| 56 | `:%s/\(gg\)\@<=\d\+/\=submatch(0)+6/` | increment only numbers `gg\d\d` by 6 (another way)
|    |                                          | **rename a string with an incrementing number**
| 57 | `:let i=10 | 'a,'bg/Abc/s/yy/\=i/ |let i=i+1` | convert yy to 10,11,12 etc
| 58 | `:let i=10 | 'a,'bg/Abc/s/xx\zsyy\ze/\=i/ |let i=i+1` | convert xxyy to xx11,xx12,xx13(as above but more precise)
| 59 | `:%s/"\([^.]\+\).*\zsxx/\1/` | find replacement text, put in memory, then use \zs to simplify substitute
| 60 | `:nmap <leader>z :%s#\<<c-r>=expand("<cword>")<cr>\>#` | Pull word under cursor into LHS of a substitute
| 61 | `:vmap <leader>z :<C-U>%s/\<<c-r>*\>/` | Pull Visually Highlighted text into LHS of a substitute
| 62 | `:'a,'bs/bucket\(s\)*/bowl\1/gic` | substitute singular or plural [N]

[Best of Vim Tips](http://zzapper.co.uk/vimtips.html)
