# savedataToSPSS
Convert Mplus savedata .dat file to SPSS .sav file

This and other SPSS Python Extension functions can be found at http://www.stat-help.com/python.html

## Usage
**savedataToSPSS(infile, outfile, varList, MplusVarList)**
* "infile" is the path and filename for the Mplus savedata file that is to be converted to SPSS. Ensure that you use forward slashes ("/") instead of backward slashes ("\") when defining the file path.
* "outfile" is the path and filename for the exported SPSS data file. Ensure that you use forward slashes ("/") instead of backward slashes ("\") when defining the file path. The file name should have a ".sav" extension. 
* "varList is a list of the variable names, in order, that are in the savedata file. This must be provided as a list of string variables. If you provide a varList, you can omit the MplusVarList argument.
* "MplusVarList" is another way of specifying the variable names in the file. When you ask Mplus to create a savedata file, it will provide a list of variable names and types at the bottom of the program. It will look something like:    
VAR00157       F10.3    
VAR00158       F10.3    
VAR00159       F10.3    
VAR00160       F10.3    
VAR00161       F10.3    
VAR00162       F10.3    
SSIS_AVG       F10.3    
S_EN_ATT       F10.3    
S_EN_BEH       F10.3    
QSOCCOMP       F10.3    
QSOCCOMP_SE    F10.3
* If you want to save time, you can just create a string variable whose value is this entire list, and the program can automatically extract the variable names for you. If you provide a value for MplusVarList, you do not need to provide a value for varList. If you provide both, the program will use the list of variables in varList.

## Example
**savedataToSPSS(infile = "D:/Dropbox/Study1/savedataToSPSS/fscores.dat",   
outfile = "D:/Dropbox/Study1/savedataToSPSS/fscores.sav",    
MplusVarList = """PID       F10.3    
CLASSID       F10.3    
PTAP       F10.3    
INTRO       F10.3    
EXTRO       F10.3    
KBIT       F10.3    
SSIS_AVG       F10.3    
S_EN_ATT       F10.3    
S_EN_BEH       F10.3    
QSOCCOMP       F10.3    
QSOCCOMP_SE    F10.3""")**
* This program reads the fscores.dat savedata file from Mplus and exports it to fscores.sav. The variable names were taken directly from the Mplus output file. 
* The program automatically assigns the values in the file to the names listed on the left side.
