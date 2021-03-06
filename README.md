*Author: 
Bradley T. Martin, University of Arkansas; 
E-mail: btm002@email.uark.edu*

## Python package to add a population map to STRUCTURE, PHYLIP, and .ped (PLINK) files. Also can write just a PopMap file.  

Uses Python 2 or 3

The program reads STRUCTURE files by default; use the -a option if you want to use a .ped file commonly used in the ADMIXTURE program. Use the -t option to read in a PHYLIP file.  

By default, str2popmap.py uses the first four letters of each sample name to designate populations.  
However, the user can specify a range of characters for the popID search pattern (e.g., 2-5).  

The popID REGEX search range can be changed with the -s (start) and -e (end) command-line arguments (first character=1)  

example: `./str2popmap.py -f example_input.str -s 2 -e 5 -o output.str # Uses characters 2-5 as pattern
to make PopIDs`

-p option (Boolean; default = off) only writes two-column sample IDs and popIDs (POPMAP) separated by tabs

```
# -p option output
ind1\tpop1\n
ind2\tpop1\n
ind3\tpop2\n
ind4\tpop2\n
```

If you want the POPMAP to be inserted between sampleIDs and sequences in a PHYLIP file while keeping the sequences, use the -t option without -p.  

Default File Format = STRUCTURE.  
But you can use other formats instead by doing as shown below:  
-t option (Boolean; default = off) Uses PHYLIP format for input/output files  
-a option (Boolean; default = off) Uses .ped format for input/output files (commonly used in ADMIXTURE)  
-c option (Boolean; default = off) Outputs string as popID instead of integer  

### Optional arguments:

[-o OUTFILE (string); default = out.txt]  
[-s STARTCHAR (integer); default = 1]   
[-e ENDCHAR (integer); default = 4]  
[-p POPMAP (Boolean); default = False]  
[-t PHYLIP (Boolean); default = False]  
[-a ADMIXTURE (Boolean); default = False]  
[-c CHARREGEX (Boolean); default = False]  
