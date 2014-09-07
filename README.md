filename-toolkit
================
A toolkit for editing multiple filenames at once.  

### Usage
```
filename-toolkit [-h] [-d DIR] [-m MATCH [MATCH ...]] [-p PREPEND]
                        [-a APPEND] [-l] [-t] [-r REPLACE [REPLACE ...]]
                        [-w REPLACE_WITH [REPLACE_WITH ...]]
```

### Help
```
optional arguments:
  -h, --help            show this help message and exit
  -d DIR, --dir DIR     Directory to work on. Defaults to current
  -m MATCH, --match MATCH
                        Process files with given regex
  -p PREPEND, --prepend PREPEND
                        Insert string at the beggining of filename
  -a APPEND, --append APPEND
                        Insert string at the end of filename
  -l, --list            Show list of processed files
  -t, --test            Changes won't be applied
  -r REPLACE [REPLACE ...], --replace REPLACE [REPLACE ...]
                        Replace string/regex with other string, defaults
                        repace to ''
  -c COPY, --copy COPY  Don't rename but copy files with new name to specified
                        dir.
  --version             show program's version number and exit
```
In `-r/--replace`, you may use named groups in the first one and refer to them in the second one `\g<name>`, or use annonymous groups, they're named in order starting from `1` (`\g<1>` or `\1`).

### Examples
##### Remove substring from filenames
`filename-toolkit -r "substring"`

##### Change filename from 21-03 to 03-21
`filename-toolkit -r "(?P<day>\d+)-(?P<month>\d+)" -w "\g<month>-\g<day>"`  
`filename-toolkit -r "(\d+)-(\d+)" -w "\g<2>-\g<1>"`  
`filename-toolkit -r "(\d+)-(\d+)" -w "\2-\1"`  

##### Remove 5 characters from beginning of filename
`filename-toolkit -r "^.*{5}"`
