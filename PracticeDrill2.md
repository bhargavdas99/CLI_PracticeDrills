## 1.Download the book from the link.
Ans:
    1. curl -O https://raw.githubusercontent.com/bobdeng/owlreader/master/ERead/assets/books/ Harry%20Potter%20and%20the%20Goblet%20of%20Fire.txt
    ("curl" command helps us to download the content from the link and saves it into a file in our local system)

    2. mv Harry%20Potter%20and%20the%20Goblet%20of%20Fire.txt HarryPotter.txt
    (rename the book to a shorter and readable name)

----------------------------------------------------------------------------
## 2.Print the first three lines in the book
Ans: `head -n 3 HarryPotter.txt`
    //head command helps us to print 'n' lines from the top


----------------------------------------------------------------------------
## 3.Print the last 10 lines in the book
Ans: `tail -n 10 HarryPotter.txt`
    //tail command helps us to print 'n' lines from the bottom

----------------------------------------------------------------------------
## 4.How many times do the following words occur in the book?
        Harry
        Ron
        Hermione
        Dumbledore
Ans:
    1. "grep -o" helps us to search every occurence of the word
    2. Then we use pipe "|" command to filter the output of one command to another command
    3. "wc -w" command takes the output of "grep" and prints out the count of occurences.


    `grep -o "Harry" HarryPotter.txt | wc -w`      -   3169 occurences

    `grep -o "Ron" HarryPotter.txt | wc -w`        -   1044 occurences

    `grep -o "Hermione" HarryPotter.txt | wc -w`   -   872  occurences

    `grep -o "Dumbledore" HarryPotter.txt | wc -w` -   872  occurences


-----------------------------------------------------------------------------
## 5.Print lines from 100 through 200 in the book
Ans: `sed -n "100, 200p" HarryPotter.txt`
    //"sed" command helps us to print out the lines which we want from the content of a file.



-----------------------------------------------------------------------------
## 6.How many unique words are present in the book?
Ans:
    195646 unique words

    `cat HarryPotter.txt | uniq | wc -w`
    //"uniq" command filters out all the duplicates and then "wc" counts the unique words present in the book






