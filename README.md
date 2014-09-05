filename-toolkit
================

A toolkit for editing multiple filenames at the same time.

Usage: `filename-toolkit [-r <string|regex> [-w <string>]] [-p <string>] [-a <string>] [-d <dir>] [-l] [-m <regex>] [-h] [-t]`
```
-d | --dir <directory>        Directory to work on. Defaults to current.
-m | --match <regex>          Only process files with filename matching regex.
-l | --list                   Show a list of the files processed.
-r | --replace <string|regex> [-w | --with <string>]
                              Replace first string|regex with second string.
                              If -w | --with isn't present, replaces with "".
                              You may use named groups on the firstone and refer
                              to them on the second one \g<name>, or use
                              annonymous groups, they're named in order starting
                              from 1.
                              Examples: 21-03 => 03-21
                              -r "(?P<d>\d+)-(?P<m>\d+)" -w "\g<m>-\g<d>"
                              -r "(\d+)-(\d+)" -w "\g<2>-\g<1>"
-p | --prepend <string>       Insert string at the beginning of filename.
-a | --append <string>        Insert string at the end of filename.
-t | --test                   Changes won't be applied. 
                              To see changes to be applied use -l.
-h | --help                   Show this text.
```
