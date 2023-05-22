# Lab Report 3

In this lab report, I will find 4 interesting ways to use the command line options of the `grep` command.

# grep -R [pattern]
The -R flag allows us to search for a pattern recursively in current directory and all subdirectories. 

### Example 1: Searching for all instances of "monkeypox" in the biomed folder

```bash
grep -R "monkeypox" biomed
 ``` 

 ```
biomed/1471-2334-3-9.txt:        (vaccinia), 27 μM (monkeypox) and 58 μM (cowpox) [ 40 41 ]
 ```

 In this use of the grep command, I am searching recursively in the biomed folder for anyline that 
 contains the "monkeypox" in it. Our command found the file `biomed/1471-2334-3-9.txt` to contain an instance of 
 the word monkeypox, and outputted the line that contained it. This command is useful because we didn't have to look 
 through each file within the biomed folder for occurences of "monkeypox". Instead, we searched for all instances at once 
 with a short and quick command.  
 
### Suppose we wan all  
 ```bash 
grep -iR "heroin" . 
 ```

 ```
 ./plos/pmed.0020061.txt:        cocaine, alcohol, phenytoin, heroin, methadone, and ionizing radiation) and developed rules
./biomed/1471-2369-3-10.txt:          potential overdoses for heroin, but not for cocaine or
./biomed/1471-2458-2-25.txt:              "I was using heroin and crack
./911report/chapter-13.5.txt:                against drug warehouses and heroin laboratories." United States Institute of Peace
./911report/chapter-3.txt:                through trade in heroin. Nor had Massoud shown much aptitude for governing except as
```
In this grep command, I searched all my current directory recursively for any instances of the word "heroin", while ignoring all cases. 
The command outputted everyline that contained the word "heroin". This is an powerful command because it allows you to search through every file in your current directory for a specific word.

I found how to use this command with the following link:

[cyberciti](https://www.cyberciti.biz/faq/howto-use-grep-command-in-linux-unix/)

# grep -l [pattern] 
Display list of filenames that matches a specific pattern 

```bash 
grep -l "sun" plos/pmed*.txt
```
```
plos/pmed.0020120.txt
plos/pmed.0020155.txt
plos/pmed.0020236.txt
```
In this grep command, I used the -l tag to list all text files from the plos folder that started with "pmed" and contained
the word sun. The command outputted every file within `plos` that contained the word sun somewhere in the text file. This is an important 
command line option because it allows you to identify all the file that contain a match to some sort of pattern. We can then pipe these files 
into a new command such as the `wc ` command to count the words in each of the text files that contains the word "sun" somewhere.

```bash
grep -ilR "George Washington" . 
``` 

```bash 
./government/Gen_Account_Office/pe1019.txt
./government/Gen_Account_Office/ai00134.txt
./plos/pmed.0020067.txt
./biomed/bcr602.txt
./911report/chapter-13.4.txt
./911report/chapter-13.5.txt
```
In this grep command, I recursively searched through my current directory to find every file that contain an instance of George Washington, ignoring cases. The command then output every file within my current directory that contains "George Washington". This is an important use of grep because it allows us to quickly identify all files that matches some sort of specified pattern within our current directory. Like I said earlier, we can then pipe this files into another command. 

I found how to use this command with the following link:

[geeksforgeek](https://www.geeksforgeeks.org/grep-command-in-unixlinux/)


# grep -f [file] 
Another command line argument for grep is the -f flag. This flag allows you to pass in a file containing all the patterns 
you want to identify. The command then takes the pattern from the file, with one pattern per line, greps all the patterns together. 

### Example
Suppose the `technical` directory contains a new text file called `patterns.txt` with the following contents: 
``` 
cannabis 
cocaine 
```
If we run the command 
```
grep -f patterns.txt -R government
```
the command will output the following: 

```
government/Alcohol_Problems/Session3-PDF.txt:for cocaine dependence: delayed emergency of psychotherapy effects.
government/Media/Eviction_law.txt:was caught with cocaine three blocks from the apartment she shared
```
In this grep command, we recursively searched for every instance of the "cannabis" and "cocaine" in the government 
directory. The command will then output every line that matched either one of these words. This is an important 
command line option because it allows us to specify a long list of patterns without having to manually type 
each of the pattern in the command line. 

### Example 
```
grep -C 3 -f patterns.txt -R government 
```

```
government/Alcohol_Problems/Session3-PDF.txt-1996;53:217-24.
government/Alcohol_Problems/Session3-PDF.txt-12. Carroll K, Rounsaville BJ, Nich C, Gordon LT, Wirtz PW,
government/Alcohol_Problems/Session3-PDF.txt-Gawin F. One-year follow-up of psychotherapy and pharmacotherapy
government/Alcohol_Problems/Session3-PDF.txt:for cocaine dependence: delayed emergency of psychotherapy effects.
government/Alcohol_Problems/Session3-PDF.txt-Arch Gen Psychiatry 1994;51:989-97.
government/Alcohol_Problems/Session3-PDF.txt-
government/Alcohol_Problems/Session3-PDF.txt-
--
government/Media/Eviction_law.txt-received eviction notices because of the drug use of relatives or
government/Media/Eviction_law.txt-caregivers.
government/Media/Eviction_law.txt-Rucker was ordered out because her mentally disabled daughter
government/Media/Eviction_law.txt:was caught with cocaine three blocks from the apartment she shared
government/Media/Eviction_law.txt-with her mother and other family members, court records show.
government/Media/Eviction_law.txt-An appeals court blocked enforcement of the law.
government/Media/Eviction_law.txt-At issue is whether housing directors are being more aggressive
```
In this grep command, we search for all instances of the word "cannabis" and cocaine" recursively in the government directory. We then 
outputted 3 lines above and below every line that match the patterns in patterns.txt, along with the line the matched. This is an important
use of the command -f because it allows us to see the context of why each of our pattern in `patterns.txt` show up in the governmnet
directory. 

I found how to use this command with the following links:

[cyberciti](https://www.cyberciti.biz/faq/howto-use-grep-command-in-linux-unix/)


[geeksforgeek](https://www.geeksforgeeks.org/grep-command-in-unixlinux/)


# grep [regex] filepath
Another powerful use of the grep command is to use grep to identify a regex pattern. Regex, or regular expressions are 
special strings representing a pattern to be matched in a search operation. 

## Example: Matching years in the 2010s 
For instance, suppose we want to search for instances of alcohol problem in the 2010s. We need to run a separate grep command with 
2010, 2011, 2012, ..., 2019. However, with regex, we can create a pattern that is equivalent to all the years in the 2010s by using `"201[0-9]" `. This string matches with all lines containing 201 following up with another number.
```bash 
grep "201[0-9]" -R government/Alcohol_Problems
``` 
outputs: 
``` 
government/Alcohol_Problems/Session3-PDF.txt:2010: Understanding and Improving Health. 2nd ed. Washington (DC):
government/Alcohol_Problems/DraftRecom-PDF.txt:Li suggested that adding a reference to the Healthy People 2010
government/Alcohol_Problems/Session4-PDF.txt:public policy objectives of Healthy People 2010 include routine
government/Alcohol_Problems/Session4-PDF.txt:2010: Hospital and Emergency Department Referrals. Washington (DC):
``` 
In this command, all lines within the `government/Alcohol_Problems` directory containing a year within the 2010s is outputted. 
In our example, all of the lines were outputted because these lines contained an instance of "2010". 

## Mathing letters 
Suppose we want to find text files that are personal letter from one person to another. One way we could do this is to find all text file that contains a line that starts with the word Dear.  
```bash
grep "^Dear" . 
```
Outputted the following: 
```
./government/Gen_Account_Office/og97032.txt:Dear Mr. Chairman:
./government/Gen_Account_Office/Letter_Walkeraug17let.txt:Dear Mr. Vice President:
./government/Gen_Account_Office/Sept14-2002_d011070.txt:Dear Senator Voinovich:
./government/Gen_Account_Office/Oct15-2001_d0224.txt:Dear Senator Bennett:
./government/Post_Rate_Comm/Gleiman_gca2000.txt:Dear Santa, Thanks so much for all you did last Christmas.
```
In this grep command, I outputted all the lines recursively within my current directory that contains a line beginning with 
"Dear". 

I learned about this option with the following link: 

[cyberciti](https://www.cyberciti.biz/faq/howto-use-grep-command-in-linux-unix/)