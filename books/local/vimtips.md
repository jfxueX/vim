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


[Best of Vim Tips](http://zzapper.co.uk/vimtips.html)
