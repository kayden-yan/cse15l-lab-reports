# CSE 15L Lab Report 3
___
## Exploring the Command Options for ```find```
___
## Option 1: ```-name```
By adding the ```-name``` after the ```find```, Bash utilize the -name option to look for files with certain names.
Example 1:
Input:
```
$ find -name ch1.txt
```
Output:
```
./written_2/non-fiction/OUP/Abernathy/ch1.txt
./written_2/non-fiction/OUP/Berk/ch1.txt
./written_2/non-fiction/OUP/Fletcher/ch1.txt
./written_2/non-fiction/OUP/Kauffman/ch1.txt
./written_2/non-fiction/OUP/Rybczynski/ch1.txt
```
Example 2:
Input:
```
$ find -name WhereToJapan.txt
```
Output:
```
./written_2/travel_guides/berlitz1/WhereToJapan.txt
```
___
## Option 2: ```-size```
By adding the ```-size``` after the ```find```, Bash search for files of a particular size.
Example 1:
Input:
```
$ find -size +200k
```
Find files that are bigger than 200 Kb.
Output:
```
./.git/objects/pack/pack-b98cb6a4ca64cc7b2944f0fa07d3e03927d66064.pack
./written_2/travel_guides/berlitz1/WhereToFrance.txt
./written_2/travel_guides/berlitz1/WhereToItaly.txt
./written_2/travel_guides/berlitz2/Canada-WhereToGo.txt
```
Example 2:
Input:
```
$ find -size +230k
```
Find files that are bigger than 230 Kb.
Output:
```
./.git/objects/pack/pack-b98cb6a4ca64cc7b2944f0fa07d3e03927d66064.pack
./written_2/travel_guides/berlitz1/WhereToFrance.txt
./written_2/travel_guides/berlitz1/WhereToItaly.txt
./written_2/travel_guides/berlitz2/Canada-WhereToGo.txt
```
___
## Option 3: ```-type```
By adding the ```-type``` after the ```find```, Bash search for particular file types using the -type option.
Example 1:
Input:
```
$ find -type d
```
Find type directories.
Output:
```
.
./.git
./.git/hooks
./.git/info
./.git/logs
./.git/logs/refs
./.git/logs/refs/heads
./.git/logs/refs/remotes
./.git/logs/refs/remotes/origin
......
./written_2/non-fiction/OUP/Fletcher
./written_2/non-fiction/OUP/Kauffman
./written_2/non-fiction/OUP/Rybczynski
./written_2/travel_guides
./written_2/travel_guides/berlitz1
./written_2/travel_guides/berlitz2
```
Example 2:
Input:
```
$ find -type f
```
Find files.
Output:
```
./.git/config
./.git/description
./.git/FETCH_HEAD
./.git/HEAD
./.git/hooks/applypatch-msg.sample
./.git/hooks/commit-msg.sample
......
./written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt
./written_2/travel_guides/berlitz2/Vallarta-History.txt
./written_2/travel_guides/berlitz2/Vallarta-WhatToDo.txt
./written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt
```
___
## Option 4: ```-path```
By adding the ```-path``` after the ```find```, Bash search for particular directory path using the ```-path``` option
Example 1:
Input:
```
$ find -path "*/*/Berk/*.txt"
```
Output:
```
./written_2/non-fiction/OUP/Berk/ch1.txt
./written_2/non-fiction/OUP/Berk/ch2.txt
./written_2/non-fiction/OUP/Berk/CH4.txt
./written_2/non-fiction/OUP/Berk/ch7.txt
```
Example 2:
Input:
```
$ find -path "*/OUP/Rybczynski/*.txt"
```
Output:
```
./written_2/non-fiction/OUP/Rybczynski/ch1.txt
./written_2/non-fiction/OUP/Rybczynski/ch2.txt
./written_2/non-fiction/OUP/Rybczynski/ch3.txt
```

___
## Source Cited:
https://linuxconfig.org/how-to-use-find-command-to-search-for-files-based-on-file-size
https://www.geeksforgeeks.org/find-command-in-linux-with-examples/
https://linuxize.com/post/how-to-find-files-in-linux-using-the-command-line/
