I used chatGPT to research 4 different command line options for the command `find`, here is the link: [ChatGPT](https://chat.openai.com)
<br>
<br>1. `-type` : this option searches for specific files, for examples, `-type d` would search only for directories, while `-type f` would search for regular files. 
<br>I show how to use `-type d` below: 
```
find stringsearch-data -type d

stringsearch-data
stringsearch-data/.git
stringsearch-data/.git/objects
stringsearch-data/.git/objects/pack
stringsearch-data/.git/objects/info
stringsearch-data/.git/info
stringsearch-data/.git/logs
stringsearch-data/.git/logs/refs
stringsearch-data/.git/logs/refs/heads
stringsearch-data/.git/logs/refs/remotes
stringsearch-data/.git/logs/refs/remotes/origin
stringsearch-data/.git/hooks
stringsearch-data/.git/refs
stringsearch-data/.git/refs/heads
stringsearch-data/.git/refs/tags
stringsearch-data/.git/refs/remotes
stringsearch-data/.git/refs/remotes/origin
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
<br>I show how to use `-type f` below (I shortened the output by a lot, because this command prints out everysingle file in the techincal directory which is too much to even show on an entire terminal): 
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
