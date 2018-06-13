# SourceCodeSniffer
The Source Code Sniffer is a poor man’s static code analysis tool (SCA) based on regular expressions. The Source Code Sniffer uses search patterns to score common high risk functions (Injection, LFI/RFI, file uploads etc) across multiple application development languages (C#, C/C++,Java, PHP, Perl, Python, JavaScript, HTML etc) in a highly configurable manner. When performing a source code review, it can help to prioritize the code files that should be reviewed. 

Source Code Sniffer is written in Python 2.7 and supports both Windows and Linux.

## Static Code Analysis Features and Languages
|Language   |SQL Injection|LFI/RFI |XSS     |File Traversal|File Uploads|Hard-coded Secrets|Command Injection|Buffer Overflow|
|----------:|------------:|-------:|-------:|-------------:|-----------:|-----------------:|----------------:|-------------:|
|PHP        |             |        |        |              |            |                  |    &#10004;     |              |
|Python     |             |        |        |              |            |                  |                 |              |
|Node.js    |             |        |        |              |            |                  |    &#10004;     |              |
|GO         |             |        |        |              |            |                  |                 |              | 
|ASP Classic| &#10004;    |&#10004;|&#10004;|              |            |                  |    &#10004;     |              | 
|C#         | &#10004;    |        |&#10004;|              |            |  &#10004;        |    &#10004;     |              | 
|JAVA       | &#10004;    |&#10004;|&#10004;|              |            |                  |    &#10004;     |              |     
|VisualBasic|             |        |&#10004;|              |            |                  |                 |              |   
|Ruby       |             |        |        |              |            |                  |                 |              |        
|Perl       |             |        |        |              |            |                  |                 |              |          
|C/C++      |             |        |        |              |            |                  |    &#10004;     |   &#10004;   | 


## Syntax help
```
python SourceCodeSniffer.py -h

- Command Line Usage
	``# C:/Users/Haxz0r/PycharmProjects/SourceCodeSniffer/SourceCodeSniff [options]``

Options
-------
====================== ==============================================================
-c --configFiles        specify the config files (default=['Default.ini', 'ASP.ini', 'CSharp.ini', 'Java.ini', 'VBScript.ini', 'C.ini'])
                        config files should be comma separated
-p --pathToScan         specify the path to scan (default=.)
                        use the forward slash / for both *nix and windows paths
-i --ignoreFiles        specify files to not scan (default=('.html', 'robots.txt'))
                        ignored files and file types should be comma separated
-v --verbose            verbose mode
-h --htmlReport         generate an html report (experimental)
-d --debug              show debug output
-l --log                output to log file
====================== ==============================================================
Example:
 python SourceCodeSniffer.py -c ASP.ini,CSharp.ini,Default.ini,VBScript.ini -p c:/testpath/test/ -i .html,robots.txt
```


## Commandline Output Example - C/C++ Scan
```
#python SourceCodeSniffer.py -c C.ini -p "C:\SRC"
  Source Code Sniffer Version: 0.6 Updated: June 12, 2018 (-h for help)
Using configuration files: ['C.ini']
Recursively sniffing path for dangerous code: C:\SRC
[################################] 3/3 - 00:00:39
Files sorted by potential risk level:
Risk		 File Path
0   		 C:\SRC\Small.c
2    		 C:\SRC\Gateway.c
2    		 C:\SRC\Library.c

Files sorted by number of potential issues:
Issues 		File Path
0    		C:\SRC\Small.c
2679 		C:\SRC\Gateway.c
12982 		C:\SRC\Library.c
```


## Report Output File Example - C/C++ Scan
```
Coming soon...

```
