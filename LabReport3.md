I chose grep command, where grep is a command that we can use to find certain string we are looking for in a text file.
here are 4 options I chose:

-v option:
1.
`[cs15lwi23awx@ieng6-203]:skill-demo1-data:36$ find written_2/ > find.txt
[cs15lwi23awx@ieng6-203]:skill-demo1-data:37$ grep ".txt" find.txt > grep.txt
[cs15lwi23awx@ieng6-203]:skill-demo1-data:38$ grep -v txt grep.txt`

here I wrote a text file called grep.txt that contained all the text files in written_2. Then by using `-v` option, we searched the lines without the string "txt". This returns nothing since this file only have text files and every line has the string "txt".
2.
`[cs15lwi23awx@ieng6-203]:skill-demo1-data:40$ grep -v Bahamas-History grep.txt
written_2/non-fiction/OUP/Abernathy/ch1.txt
written_2/non-fiction/OUP/Abernathy/ch14.txt
written_2/non-fiction/OUP/Abernathy/ch15.txt
written_2/non-fiction/OUP/Abernathy/ch2.txt
written_2/non-fiction/OUP/Abernathy/ch3.txt
written_2/non-fiction/OUP/Abernathy/ch6.txt
written_2/non-fiction/OUP/Abernathy/ch7.txt
written_2/non-fiction/OUP/Abernathy/ch8.txt
written_2/non-fiction/OUP/Abernathy/ch9.txt
...`

This is also a similar example except that we want to exclude the string "Bahamas-History" in our result. As a result, we get all the text files in written_2/ except the file contained the string "Bahamas-History". This command is pretty efficient when we have the need to find if there has something that is redundant that we might want to delete, we can just use `-v` and add the string after it.

https://www.youtube.com/watch?v=Tc_jntovCM0

-n option:
3.
`[cs15lwi23awx@ieng6-203]:skill-demo1-data:47$ grep -n Bahamas Bhms.txt
1:written_2/travel_guides/berlitz2/Bahamas-History.txt
2:written_2/travel_guides/berlitz2/Bahamas-Intro.txt
3:written_2/travel_guides/berlitz2/Bahamas-WhatToDo.txt
4:written_2/travel_guides/berlitz2/Bahamas-WhereToGo.txt`

Here we have the option `-n`, where we use it for showing the line numbers. As thie we can compare it with the last example, we can tell that there are numbers on the leftmost on each senetence and which is the usage of our option. When we have the need to see how many lines are there, this option is very useful.
4.
`[cs15lwi23awx@ieng6-203]:skill-demo1-data:49$ grep -n A A.txt
1:written_2/non-fiction/OUP/Abernathy
2:written_2/non-fiction/OUP/Abernathy/ch1.txt
3:written_2/non-fiction/OUP/Abernathy/ch14.txt
4:written_2/non-fiction/OUP/Abernathy/ch15.txt
5:written_2/non-fiction/OUP/Abernathy/ch2.txt
6:written_2/non-fiction/OUP/Abernathy/ch3.txt
7:written_2/non-fiction/OUP/Abernathy/ch6.txt
8:written_2/non-fiction/OUP/Abernathy/ch7.txt
9:written_2/non-fiction/OUP/Abernathy/ch8.txt
10:written_2/non-fiction/OUP/Abernathy/ch9.txt
11:written_2/non-fiction/OUP/Castro/chA.txt
12:written_2/travel_guides/berlitz1/HandRLosAngeles.txt
13:written_2/travel_guides/berlitz1/IntroLosAngeles.txt
14:written_2/travel_guides/berlitz1/WhatToLosAngeles.txt
15:written_2/travel_guides/berlitz1/WhereToLosAngeles.txt
16:written_2/travel_guides/berlitz2/Algarve-History.txt
17:written_2/travel_guides/berlitz2/Algarve-Intro.txt
18:written_2/travel_guides/berlitz2/Algarve-WhatToDo.txt
19:written_2/travel_guides/berlitz2/Algarve-WhereToGo.txt
20:written_2/travel_guides/berlitz2/Amsterdam-History.txt
21:written_2/travel_guides/berlitz2/Amsterdam-Intro.txt
22:written_2/travel_guides/berlitz2/Amsterdam-WhatToDo.txt
23:written_2/travel_guides/berlitz2/Amsterdam-WhereToGo.txt
24:written_2/travel_guides/berlitz2/Athens-History.txt
25:written_2/travel_guides/berlitz2/Athens-Intro.txt
26:written_2/travel_guides/berlitz2/Athens-WhatToDo.txt
27:written_2/travel_guides/berlitz2/Athens-WhereToGo.txt`

As we can see in this example, there are many lines in what we want to search. I created a file called A.txt that contains all the text files that has the string "A", where I grep them all out, we get 27 lines by using this command, otherwise, it is hard to look at which line is which and refering them.

https://www.youtube.com/watch?v=Tc_jntovCM0

-c option:
5.
`[cs15lwi23awx@ieng6-203]:skill-demo1-data:51$ grep -c "txt" grep.txt           
223
[cs15lwi23awx@ieng6-203]:skill-demo1-data:52$ wc grep.txt
  223   223 11215 grep.txt`

As what we have created in the grep.txt, there exist all the text files names in written_2. This option, `-c` is used for the number of times that the string we searched for occured in the text file. As we can tell, there are total 223 text files in written_2, which correctly gives how many times the string "txt" showed up.
6.
`[cs15lwi23awx@ieng6-203]:skill-demo1-data:54$ grep -c "travel_guides" grep.txt
178`

Here as we did in the last example, if we were to find out how many files are contained in the directory called "travel_guides", we can type this command which returns the number of times this occured in grep.txt. This is the great way of counting how many of the files are in the directory.

https://www.youtube.com/watch?v=Tc_jntovCM0

-i option:
7.
`[cs15lwi23awx@ieng6-203]:skill-demo1-data:57$ grep -i "A" A.txt
written_2/non-fiction/OUP/Abernathy
written_2/non-fiction/OUP/Abernathy/ch1.txt
written_2/non-fiction/OUP/Abernathy/ch14.txt
written_2/non-fiction/OUP/Abernathy/ch15.txt
written_2/non-fiction/OUP/Abernathy/ch2.txt
written_2/non-fiction/OUP/Abernathy/ch3.txt
written_2/non-fiction/OUP/Abernathy/ch6.txt
written_2/non-fiction/OUP/Abernathy/ch7.txt
written_2/non-fiction/OUP/Abernathy/ch8.txt
written_2/non-fiction/OUP/Abernathy/ch9.txt
written_2/non-fiction/OUP/Castro/chA.txt
written_2/travel_guides/berlitz1/HandRLosAngeles.txt
written_2/travel_guides/berlitz1/IntroLosAngeles.txt
written_2/travel_guides/berlitz1/WhatToLosAngeles.txt
written_2/travel_guides/berlitz1/WhereToLosAngeles.txt
written_2/travel_guides/berlitz2/Algarve-History.txt
written_2/travel_guides/berlitz2/Algarve-Intro.txt
written_2/travel_guides/berlitz2/Algarve-WhatToDo.txt
written_2/travel_guides/berlitz2/Algarve-WhereToGo.txt
written_2/travel_guides/berlitz2/Amsterdam-History.txt
written_2/travel_guides/berlitz2/Amsterdam-Intro.txt
written_2/travel_guides/berlitz2/Amsterdam-WhatToDo.txt
written_2/travel_guides/berlitz2/Amsterdam-WhereToGo.txt
written_2/travel_guides/berlitz2/Athens-History.txt
written_2/travel_guides/berlitz2/Athens-Intro.txt
written_2/travel_guides/berlitz2/Athens-WhatToDo.txt
written_2/travel_guides/berlitz2/Athens-WhereToGo.txt`

This option, `-i` is a good way to search without capital case-sensitive. As we can tell in this output, there contains some lines with "a" and without "A". This is to return a line that has a no matter it is A or a, where we can use for excluding some cases that when a word is at the beginning of the sentence, it is upper-cased.
8.
`[cs15lwi23awx@ieng6-203]:skill-demo1-data:61$ grep -i "O" A.txt
written_2/non-fiction/OUP/Abernathy
written_2/non-fiction/OUP/Abernathy/ch1.txt
written_2/non-fiction/OUP/Abernathy/ch14.txt
written_2/non-fiction/OUP/Abernathy/ch15.txt
written_2/non-fiction/OUP/Abernathy/ch2.txt
written_2/non-fiction/OUP/Abernathy/ch3.txt
written_2/non-fiction/OUP/Abernathy/ch6.txt
written_2/non-fiction/OUP/Abernathy/ch7.txt
written_2/non-fiction/OUP/Abernathy/ch8.txt
written_2/non-fiction/OUP/Abernathy/ch9.txt
written_2/non-fiction/OUP/Castro/chA.txt
written_2/travel_guides/berlitz1/HandRLosAngeles.txt
written_2/travel_guides/berlitz1/IntroLosAngeles.txt
written_2/travel_guides/berlitz1/WhatToLosAngeles.txt
written_2/travel_guides/berlitz1/WhereToLosAngeles.txt
written_2/travel_guides/berlitz2/Algarve-History.txt
written_2/travel_guides/berlitz2/Algarve-Intro.txt
written_2/travel_guides/berlitz2/Algarve-WhatToDo.txt
written_2/travel_guides/berlitz2/Algarve-WhereToGo.txt
written_2/travel_guides/berlitz2/Amsterdam-History.txt
written_2/travel_guides/berlitz2/Amsterdam-Intro.txt
written_2/travel_guides/berlitz2/Amsterdam-WhatToDo.txt
written_2/travel_guides/berlitz2/Amsterdam-WhereToGo.txt
written_2/travel_guides/berlitz2/Athens-History.txt
written_2/travel_guides/berlitz2/Athens-Intro.txt
written_2/travel_guides/berlitz2/Athens-WhatToDo.txt
written_2/travel_guides/berlitz2/Athens-WhereToGo.txt`

This example is the same as what we have in the last example. We search all the lines with "O" and also we get the lines that contains "o" in the file, returning everything that contains the letter O.

https://www.youtube.com/watch?v=Tc_jntovCM0