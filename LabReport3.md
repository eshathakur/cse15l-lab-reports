I used chatGPT to research 4 different command line options for the command `find`, here is the link: [ChatGPT](https://chat.openai.com)
<br>
<br>1. `-type` : this option searches for specific files, for example, `-type d` would search only for directories, while `-type f` would search for regular files. This option is useful because it narrows down the general `find` command to a certain type and you can then perform commands only on that certain type.
<br>
<br>I show how to use `-type d` below, this searches for all the directories in `./technical`, as you can see `./government` has its own sub-directories: 
```
find stringsearch-data/technical -type d

stringsearch-data/technical
stringsearch-data/technical/government
stringsearch-data/technical/government/About_LSC
stringsearch-data/technical/government/Env_Prot_Agen
stringsearch-data/technical/government/Alcohol_Problems
stringsearch-data/technical/government/Gen_Account_Office
stringsearch-data/technical/government/Post_Rate_Comm
stringsearch-data/technical/government/Media
stringsearch-data/technical/plos
stringsearch-data/technical/biomed
stringsearch-data/technical/911report
```
<br>I show how to use `-type f` below (I shortened the output by a lot, because this command prints out every single file in the techincal directory which is too much to even show on an entire terminal): 
```
find stringsearch-data -type f

stringsearch-data/technical/plos/pmed.0020257.txt
stringsearch-data/technical/plos/journal.pbio.0020013.txt
stringsearch-data/technical/plos/pmed.0020055.txt
stringsearch-data/technical/plos/pmed.0020082.txt
stringsearch-data/technical/plos/pmed.0010021.txt
stringsearch-data/technical/plos/pmed.0010034.txt
stringsearch-data/technical/plos/pmed.0010008.txt
stringsearch-data/technical/plos/pmed.0020120.txt
stringsearch-data/technical/plos/journal.pbio.0020172.txt
stringsearch-data/technical/plos/pmed.0020040.txt
stringsearch-data/technical/plos/pmed.0020068.txt
stringsearch-data/technical/plos/journal.pbio.0020012.txt
stringsearch-data/technical/plos/pmed.0020281.txt
stringsearch-data/technical/plos/pmed.0020242.txt
stringsearch-data/technical/biomed/1472-6807-2-2.txt
stringsearch-data/technical/biomed/1471-2350-4-3.txt
stringsearch-data/technical/biomed/1471-2156-2-3.txt
stringsearch-data/technical/biomed/1471-2156-3-11.txt
stringsearch-data/technical/biomed/1471-2121-3-10.txt
stringsearch-data/technical/biomed/1471-2172-3-4.txt
stringsearch-data/technical/biomed/gb-2002-4-1-r2.txt
stringsearch-data/technical/biomed/gb-2003-4-6-r41.txt
stringsearch-data/technical/biomed/1471-2466-1-1.txt
stringsearch-data/technical/biomed/1471-2199-2-10.txt
stringsearch-data/technical/biomed/1471-2202-2-9.txt
stringsearch-data/technical/biomed/cc991.txt
stringsearch-data/technical/biomed/1471-2369-3-9.txt
stringsearch-data/technical/biomed/bcr620.txt
```

<br>2. `-size` : this option allows you to search for files based on their size. This option is useful because it allows you to search for files based on a characteristic. It can help with things like file cleanup or optimizing storage space by finding files that are too large or too small like empty files.
<br> For example, I searched for files less than 1 megabyte. All files in this directory were less than 1 megabyte so I shortened the output:
```
find stringsearch-data/technical -size -1M

stringsearch-data/technical/plos/pmed.0010036.txt
stringsearch-data/technical/plos/journal.pbio.0020400.txt
stringsearch-data/technical/plos/journal.pbio.0020401.txt
stringsearch-data/technical/plos/pmed.0010023.txt
stringsearch-data/technical/plos/pmed.0020123.txt
stringsearch-data/technical/plos/pmed.0020094.txt
stringsearch-data/technical/plos/journal.pbio.0020213.txt
stringsearch-data/technical/plos/pmed.0020257.txt
stringsearch-data/technical/plos/journal.pbio.0020013.txt
stringsearch-data/technical/plos/pmed.0020055.txt
stringsearch-data/technical/plos/pmed.0020082.txt
stringsearch-data/technical/plos/pmed.0010021.txt
stringsearch-data/technical/plos/pmed.0010034.txt
stringsearch-data/technical/plos/pmed.0010008.txt
stringsearch-data/technical/plos/pmed.0020120.txt
stringsearch-data/technical/plos/journal.pbio.0020172.txt
stringsearch-data/technical/plos/pmed.0020040.txt
stringsearch-data/technical/plos/pmed.0020068.txt
stringsearch-data/technical/plos/journal.pbio.0020012.txt
stringsearch-data/technical/plos/pmed.0020281.txt
stringsearch-data/technical/plos/pmed.0020242.txt
stringsearch-data/technical/biomed
stringsearch-data/technical/biomed/1472-6807-2-2.txt
stringsearch-data/technical/biomed/1471-2350-4-3.txt
stringsearch-data/technical/biomed/1471-2156-2-3.txt
stringsearch-data/technical/biomed/1471-2156-3-11.txt
stringsearch-data/technical/biomed/1471-2121-3-10.txt
stringsearch-data/technical/biomed/1471-2172-3-4.txt
stringsearch-data/technical/biomed/gb-2002-4-1-r2.txt
stringsearch-data/technical/biomed/gb-2003-4-6-r41.txt
stringsearch-data/technical/biomed/1471-2466-1-1.txt
stringsearch-data/technical/biomed/1471-2199-2-10.txt
stringsearch-data/technical/biomed/1471-2202-2-9.txt
stringsearch-data/technical/biomed/cc991.txt
```
<br> In this example, I search for files greater than 1 megabyte (since all files were less than 1 megabyte there was no output):
```
find stringsearch-data/technical -size +1M

```

<br> Here is the prompt I gave to chatGPT to gather information about the command line options `-type` and `-size`: 

<br>3. `-iname` : this option is very similar to name, except it performs a case-insensitive search. This option is useful because it saves you from having to remember the exact case of filenames and your searches will be more consistent across different platforms and filesystems.
<br> For example, `-iname "*.TXT"` and `-iname "*.txt"` will find the same files.
<br> (again, I shortened the output as all files in this directory were .txt files)
```
find stringsearch-data/technical -iname "*.TXT"

stringsearch-data/technical/biomed/1471-2202-4-2.txt
stringsearch-data/technical/biomed/1471-2172-3-9.txt
stringsearch-data/technical/biomed/gb-2001-2-3-research0007.txt
stringsearch-data/technical/biomed/1471-2199-2-6.txt
stringsearch-data/technical/biomed/bcr567.txt
stringsearch-data/technical/biomed/gb-2002-3-10-research0055.txt
stringsearch-data/technical/biomed/1471-2121-2-3.txt
stringsearch-data/technical/biomed/1471-213X-1-11.txt
stringsearch-data/technical/biomed/1472-684X-1-5.txt
stringsearch-data/technical/biomed/1476-4598-1-6.txt
stringsearch-data/technical/911report/chapter-13.4.txt
stringsearch-data/technical/911report/chapter-13.5.txt
stringsearch-data/technical/911report/chapter-13.1.txt
stringsearch-data/technical/911report/chapter-13.2.txt
stringsearch-data/technical/911report/chapter-13.3.txt
stringsearch-data/technical/911report/chapter-3.txt
stringsearch-data/technical/911report/chapter-2.txt
stringsearch-data/technical/911report/chapter-1.txt
stringsearch-data/technical/911report/chapter-5.txt
stringsearch-data/technical/911report/chapter-6.txt
stringsearch-data/technical/911report/chapter-7.txt
stringsearch-data/technical/911report/chapter-9.txt
stringsearch-data/technical/911report/chapter-8.txt
stringsearch-data/technical/911report/preface.txt
stringsearch-data/technical/911report/chapter-12.txt
stringsearch-data/technical/911report/chapter-10.txt
stringsearch-data/technical/911report/chapter-11.txt
```

```
find stringsearch-data/technical -iname "*.txt"

stringsearch-data/technical/biomed/1471-2202-4-2.txt
stringsearch-data/technical/biomed/1471-2172-3-9.txt
stringsearch-data/technical/biomed/gb-2001-2-3-research0007.txt
stringsearch-data/technical/biomed/1471-2199-2-6.txt
stringsearch-data/technical/biomed/bcr567.txt
stringsearch-data/technical/biomed/gb-2002-3-10-research0055.txt
stringsearch-data/technical/biomed/1471-2121-2-3.txt
stringsearch-data/technical/biomed/1471-213X-1-11.txt
stringsearch-data/technical/biomed/1472-684X-1-5.txt
stringsearch-data/technical/biomed/1476-4598-1-6.txt
stringsearch-data/technical/911report/chapter-13.4.txt
stringsearch-data/technical/911report/chapter-13.5.txt
stringsearch-data/technical/911report/chapter-13.1.txt
stringsearch-data/technical/911report/chapter-13.2.txt
stringsearch-data/technical/911report/chapter-13.3.txt
stringsearch-data/technical/911report/chapter-3.txt
stringsearch-data/technical/911report/chapter-2.txt
stringsearch-data/technical/911report/chapter-1.txt
stringsearch-data/technical/911report/chapter-5.txt
stringsearch-data/technical/911report/chapter-6.txt
stringsearch-data/technical/911report/chapter-7.txt
stringsearch-data/technical/911report/chapter-9.txt
stringsearch-data/technical/911report/chapter-8.txt
stringsearch-data/technical/911report/preface.txt
stringsearch-data/technical/911report/chapter-12.txt
stringsearch-data/technical/911report/chapter-10.txt
stringsearch-data/technical/911report/chapter-11.txt
```

<br>4. `-user` : this option allows you to search for a file owned by a specific user. This option is most useful in multi-user environments because it can find and filter files owned by a specific user.
<br> For example, since I cloned the directory under my user EshaThakur on vscode on my mac, all the files were owned by me. So when I did this command, all files under the ./techincal directory were in the outout (which I shortened).
```
EshaThakur$ find stringsearch-data/technical -user EshaThakur

stringsearch-data/technical/biomed/1471-2164-2-4.txt
stringsearch-data/technical/biomed/1471-2210-1-3.txt
stringsearch-data/technical/biomed/1476-9433-1-3.txt
stringsearch-data/technical/biomed/1471-2334-1-13.txt
stringsearch-data/technical/biomed/1471-2407-3-16.txt
stringsearch-data/technical/biomed/1471-2164-4-2.txt
stringsearch-data/technical/biomed/cvm-2-4-187.txt
stringsearch-data/technical/biomed/1471-2105-3-4.txt
stringsearch-data/technical/biomed/1471-2121-3-21.txt
stringsearch-data/technical/biomed/1471-2202-4-2.txt
stringsearch-data/technical/biomed/1471-2172-3-9.txt
stringsearch-data/technical/biomed/gb-2001-2-3-research0007.txt
stringsearch-data/technical/biomed/1471-2199-2-6.txt
stringsearch-data/technical/biomed/bcr567.txt
stringsearch-data/technical/biomed/gb-2002-3-10-research0055.txt
stringsearch-data/technical/biomed/1471-2121-2-3.txt
stringsearch-data/technical/biomed/1471-213X-1-11.txt
stringsearch-data/technical/biomed/1472-684X-1-5.txt
stringsearch-data/technical/biomed/1476-4598-1-6.txt
stringsearch-data/technical/911report
stringsearch-data/technical/911report/chapter-13.4.txt
stringsearch-data/technical/911report/chapter-13.5.txt
stringsearch-data/technical/911report/chapter-13.1.txt
stringsearch-data/technical/911report/chapter-13.2.txt
stringsearch-data/technical/911report/chapter-13.3.txt
stringsearch-data/technical/911report/chapter-3.txt
stringsearch-data/technical/911report/chapter-2.txt
```
<br> When I searched for any other user this is the output: 
```
EshaThakur$ find stringsearch-data/technical -user JoePolitz

find: -user: JoePolitz: no such user
```
