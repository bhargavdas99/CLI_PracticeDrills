## 1.Delete all the files having .log extensions.
Ans: `find . -name "*.log" | xargs rm`
     //"find" command helps us to find a directory or files
     //"-name "*.log"" helps to find files with ".log" in its name
     //"xargs rm" (after we find the ".log" files, "xargs rm" deletes all of them)

------------------------------------------------------------------
## 2.Add the following content to a.txt
Ans: 
     1. `nano a.text`  (open a text editor inside the terminal)
     2. paste the "content" (Ctrl + Shift + V)
     3. Ctrl + X to exit
     4. Press "Y" to save

------------------------------------------------------------------
## 3.Delete the directory named five
Ans:
     1. go to the parent dir of "five"
     2. rm -r five   //"rm -r" command helps us to recursively delete all the files and dir in "five"
     

------------------------------------------------------------------
## 4.Rename the one directory to uno
Ans: mv one uno  ("mv" command renames the "one" directory to "uno")

------------------------------------------------------------------
## 5.Move a.txt to the two directory
Ans: mv a.txt ./two/ ("mv" command also moves files. Here, it moves a.txt to the directory two)







