When trying to list folders with many files sometimes we get an error 'Arg list too long', use find instead:

> find NAME_FOLDER/ -name *.gz | wc -l


Delete files by pattern: 
> find out -name *201212* | xargs rm


Replace a string in a text file (from Talk to Non Talk):

> sed -e 's/Talk/Non Talk/g' ORIGINAL_FILE > NEW_FILE 


Return the filename for a grep execution:

> grep -ln 61404160943 *


For DSV files return field value given field position and separator (this case a gz file with | separator and position 1): 

> gzcat FILE.dat.gz | awk -F\| '{print $1}'


Add a field to the end of a DSV file (this case | separator and add field 17 with string Hello):

> awk -F\|'BEGIN { OFS = "|" } {$17="Hello"; print}' ORIGINAL_FILE > NEW_FILE
