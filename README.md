filename-toolkit
================
```
usage: filename-toolkit [-h] [-d DIR] [-m MATCH [MATCH ...]] [-p PREPEND]
                        [-a APPEND] [-l] [-t] [-r REPLACE [REPLACE ...]]
                        [-w REPLACE_WITH [REPLACE_WITH ...]]

A toolkit for editing multiple filenames at once

optional arguments:
  -h, --help            show this help message and exit
  -d DIR, --dir DIR     Directory to work on. Defaults to current (default:
                        ./)
  -m MATCH [MATCH ...], --match MATCH [MATCH ...]
                        Process files with given regex (default: ['.*'])
  -p PREPEND, --prepend PREPEND
                        Insert string at the beggining of filename (default: )
  -a APPEND, --append APPEND
                        Insert string at the end of filename (default: )
  -l, --list            Show list of processed files (default: False)
  -t, --test            Changes won't be applied (default: False)
  -r REPLACE [REPLACE ...], --replace REPLACE [REPLACE ...]
                        Replace string/regex with -w/--with value, if
                        -w/--with not defined repace to '' (default: [''])
  -w REPLACE_WITH [REPLACE_WITH ...], --with REPLACE_WITH [REPLACE_WITH ...]
                        Value tu replace matching -r/--replace strings
                        (default: [''])

You may use named groups on the first one and refer to them on the second one
\g<name>, or use annonymous groups, they're named in order starting from 1.

Examples: change filename from 21-03 to 03-21
filename-toolkit -r "(?P<day>\d+)-(?P<month>\d+)" -w "\g<month>-\g<day>"
filename-toolkit -r "(\d+)-(\d+)" -w "\g<2>-\g<1>"
filename-toolkit -r "(\d+)-(\d+)" -w "\2-\1"
```
