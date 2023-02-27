# CSE 15L Lab Report 3
___
## Exploring the Command Options for ```find```
___
## Option 1: ```-name```
By adding the ```-name``` after the ```find```, Bash utilize the -name option to look for files with certain names. 
It is useful when you want to search for files with specific filenames or patterns. It's one of the most used option for the ```find``` command.
Example 1:
Input:
```
$ find written_2 -name ch1.txt
```
Output:
```
written_2/non-fiction/OUP/Berk/ch1.txt
written_2/non-fiction/OUP/Abernathy/ch1.txt
written_2/non-fiction/OUP/Rybczynski/ch1.txt
written_2/non-fiction/OUP/Kauffman/ch1.txt
written_2/non-fiction/OUP/Fletcher/ch1.txt
```
Example 2:
Input:
```
$ find written_2 -name WhereToJapan.txt
```
Output:
```
written_2/travel_guides/berlitz1/WhereToJapan.txt
```
___
## Option 2: ```-size```
By adding the ```-size``` after the ```find```, Bash search for files of a particular size.
It is a useful option because it can filters out very large files when you want to clean up your disk or filters out very small files that could be cache files.
Example 1:
Input:
```
$ find written_2 -size +200k
```
Find files that are bigger than 200 Kb.
Output:
```
written_2/travel_guides/berlitz1/WhereToItaly.txt
written_2/travel_guides/berlitz1/WhereToFrance.txt
written_2/travel_guides/berlitz2/Canada-WhereToGo.txt
```
Example 2:
Input:
```
$ find written_2 -size +230k
```
Find files that are bigger than 230 Kb.
Output:
```
written_2/travel_guides/berlitz1/WhereToFrance.txt
written_2/travel_guides/berlitz1/WhereToItaly.txt
written_2/travel_guides/berlitz2/Canada-WhereToGo.txt
```
___
## Option 3: ```-type```
By adding the ```-type``` after the ```find```, Bash search for particular file types using the -type option.
It is useful when you know the file type you want to search, it can be used to count how many files in the target file type in the search folder.
Example 1:
Input:
```
$ find written_2 -type d
```
Find type directories.
Output:
```
written_2
written_2/non-fiction
written_2/non-fiction/OUP
written_2/non-fiction/OUP/Berk
written_2/non-fiction/OUP/Abernathy
written_2/non-fiction/OUP/Rybczynski
written_2/non-fiction/OUP/Kauffman
written_2/non-fiction/OUP/Fletcher
written_2/non-fiction/OUP/Castro
written_2/travel_guides
written_2/travel_guides/berlitz1
written_2/travel_guides/berlitz2
```
Example 2:
Input:
```
$ find written_2 -type f
```
Find files.
Output:
```
written_2/non-fiction/.DS_Store
written_2/non-fiction/OUP/Berk/ch2.txt
written_2/non-fiction/OUP/Berk/ch1.txt
written_2/non-fiction/OUP/Berk/CH4.txt
written_2/non-fiction/OUP/Berk/ch7.txt
......
written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt
written_2/travel_guides/berlitz2/Vallarta-History.txt
written_2/travel_guides/berlitz2/Vallarta-WhatToDo.txt
written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt
```
___
## Option 4: ```-path```
By adding the ```-path``` after the ```find```, Bash search for particular directory path using the ```-path``` option
It is useful when you only know part of the path or you know the path but don't know the exact name of the target file.
Example 1:
Input:
```
$ find written_2 -path "*/*/Berk/*.txt"
```
Output:
```
written_2/non-fiction/OUP/Berk/ch2.txt
written_2/non-fiction/OUP/Berk/ch1.txt
written_2/non-fiction/OUP/Berk/CH4.txt
written_2/non-fiction/OUP/Berk/ch7.txt
```
Example 2:
Input:
```
$ find written_2 -path "*/OUP/Rybczynski/*.txt"
```
Output:
```
written_2/non-fiction/OUP/Rybczynski/ch2.txt
written_2/non-fiction/OUP/Rybczynski/ch3.txt
written_2/non-fiction/OUP/Rybczynski/ch1.txt
```

___
## Source Cited:

[External link to linuxconfig.org](https://linuxconfig.org/how-to-use-find-command-to-search-for-files-based-on-file-size)

[External link to geeksforgeeks.org](https://www.geeksforgeeks.org/find-command-in-linux-with-examples/)

[External link to linuxize.com](https://linuxize.com/post/how-to-find-files-in-linux-using-the-command-line/)

