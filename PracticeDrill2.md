# PIPES
## 1.Download the book from the link.
1. `curl -O https://raw.githubusercontent.com/bobdeng/owlreader/master/ERead/assets/books/ Harry%20Potter%20and%20the%20Goblet%20of%20Fire.txt`
    - `curl -O` command helps us to download the content and save it in our system with the same name with which it appears in the server.

2. `mv Harry%20Potter%20and%20the%20Goblet%20of%20Fire.txt HarryPotter.txt`
    - rename the book to a shorter and readable name

----------------------------------------------------------------------------
## 2.Print the first three lines in the book
Ans: `head -n 3 HarryPotter.txt`
    head command helps us to print 'n' lines from the top


----------------------------------------------------------------------------
## 3.Print the last 10 lines in the book
Ans: `tail -n 10 HarryPotter.txt`
    tail command helps us to print 'n' lines from the bottom

----------------------------------------------------------------------------
## 4.How many times do the following words occur in the book?   
- Harry
- Ron
- Hermione
- Dumbledore
        
Ans:
1. "grep -o" helps us to search every matching occurence of the word
2. Then we use pipe "|" command to filter the output of one command to another command
3. "wc -w" command takes the output of "grep" and prints out the count of occurences.


`grep -o "Harry" HarryPotter.txt | wc -w`      -   3169 occurences

`grep -o "Ron" HarryPotter.txt | wc -w`        -   1044 occurences

`grep -o "Hermione" HarryPotter.txt | wc -w`   -   872  occurences

`grep -o "Dumbledore" HarryPotter.txt | wc -w` -   872  occurences


-----------------------------------------------------------------------------
## 5.Print lines from 100 through 200 in the book
Ans: `sed -n "100, 200p" HarryPotter.txt`

Here, `sed -n` command helps us to print out the specified lines from the file.



-----------------------------------------------------------------------------
## 6.How many unique words are present in the book?
Ans:
195587 unique words

`sort HarryPotter.txt | uniq | wc -w`

- `uniq` command filters out all the duplicates but it relies on **sorted** input. 
- Then `wc -w` counts the unique words present in the book.
<<<<<<< HEAD
=======

-----------------------------------------------------------------------------

# PROCESSES AND PORTS

## List your browser's process ids (pid) and parent process ids(ppid)
`ps -ef | grep firefox | awk '{print $2, $3, $8}'`
- `ps -ef` generates the process list with all columns.
- `grep firefox` helps us to find the results specifically for our browser.
- `awk` helps us to print 2nd(PID), 3rd(PPID) and 8th(COMMAND/PROCESS) columns.

## Stop the browser application from the command line
- We use commands `pidof firefox` or `pgrep firefox` to find the parent PID.
- And then use `kill -9 2806` to terminate the process instantly.

## List the top 3 processes by CPU usage.
`ps aux --sort=-%cpu | head -n 4`

- `ps aux`
    - ps: Displays information about running processes.
    - a: Shows processes for all users.
    - u: Displays processes in a user-oriented format, including user, CPU usage, memory usage, etc.
    - x: Includes processes not attached to a terminal (background processes).

- `--sort=-%cpu`
    - Sorts the output of ps by CPU usage in descending order.
- `head -n 4`
    - head -n 4: Displays only the first 4 lines.

## List the top 3 processes by memory usage.
`ps aux --sort=-%mem | head -n 4`

- `ps aux`
    - ps: Displays information about running processes.
    - a: Shows processes for all users.
    - u: Displays processes in a user-oriented format, including user, CPU usage, memory usage, etc.
    - x: Includes processes not attached to a terminal (background processes).
- `--sort=-%mem`
    - Sorts the output of ps by MEM usage in descending order.
- `head -n 4`
    - head -n 4: Displays only the first 4 lines.

## Start a Python HTTP server on port 8000
`python3 -m http.server 8000`

- `m http.server 8000`
    - The -m flag runs a specified Python module as a script.
    - http.server starts a HTTP server in the current directory and it listens on port 8000.


## Start a Python HTTP server on port 90
`sudo python3 -m http.server 90`

- `sudo` gives us root privilege to listen to port 90.
- `m http.server 8000`
    - The -m flag runs a specified Python module as a script.
    - http.server starts a HTTP server in the current directory and it listens on port 90.

# PROCESSES AND PORTS
## List your browser's process ids (pid) and parent process ids(ppid)
`ps -ef | grep firefox | awk '{print $2, $3, $8}'`
- `ps -ef` generates the process list with all columns.
- `grep firefox` helps us to find the results specifically for our browser.
- `awk` helps us to print 2nd(PID), 3rd(PPID) and 8th(COMMAND/PROCESS) columns.

## Stop the browser application from the command line
- We use commands `pidof firefox` or `pgrep firefox` to find the parent PID.
- And then use `kill -9 2806` to terminate the process instantly.

## List the top 3 processes by CPU usage.
`ps aux --sort=-%cpu | head -n 4`

- `ps aux`
    - ps: Displays information about running processes.
    - a: Shows processes for all users.
    - u: Displays processes in a user-oriented format, including user, CPU usage, memory usage, etc.
    - x: Includes processes not attached to a terminal (background processes).

- `--sort=-%cpu`
    - Sorts the output of ps by CPU usage in descending order.
- `head -n 4`
    - head -n 4: Displays only the first 4 lines.

## List the top 3 processes by memory usage.
`ps aux --sort=-%mem | head -n 4`

- `ps aux`
    - ps: Displays information about running processes.
    - a: Shows processes for all users.
    - u: Displays processes in a user-oriented format, including user, CPU usage, memory usage, etc.
    - x: Includes processes not attached to a terminal (background processes).
- `--sort=-%mem`
    - Sorts the output of ps by MEM usage in descending order.
- `head -n 4`
    - head -n 4: Displays only the first 4 lines.

## Start a Python HTTP server on port 8000
`python3 -m http.server 8000`

- `m http.server 8000`
    - The -m flag runs a specified Python module as a script.
    - http.server starts a HTTP server in the current directory and it listens on port 8000.

## Display all active connections and the corresponding TCP / UDP ports.
`netstat -t -u`  or `ss -t -u`
- `netstat`
    Displays network connections, routing tables, interface statistics etc.

- `-t -u`: Displays TCP connections and UDP connections.

## Start a Python HTTP server on port 90
`sudo python3 -m http.server 90`

<<<<<<< HEAD
- `sudo` gives us root privilege to listen to port 90.
- `m http.server 8000`
    - The -m flag runs a specified Python module as a script.
    - http.server starts a HTTP server in the current directory and it listens on port 90.


## Display all active connections and the corresponding TCP / UDP ports.
`netstat -t -u`  or `ss -t -u`
- `netstat`
    Displays network connections, routing tables, interface statistics etc.

- `-t -u`: Displays TCP connections and UDP connections.


=======
## Find the pid of the process that is listening on port 5432
`sudo ss -tulnp | grep 5432`
- `sudo`: Executes the command with superuser privileges.
- `ss`: Displays detailed network socket information (modern replacement for netstat).
- ```
    -t: Shows TCP connections.
    -u: Shows UDP connections.
    -l: Lists only listening sockets.
    -n: Displays addresses and ports in numeric form (e.g., 5432 instead of resolving the service name).
    -p: Shows the process ID (PID) and program associated with the socket.
    ```
- `| grep 5432`: Filters the output to show only lines containing 5432, the port you're investigating.



# MISC
## What's your local IP address?
`ifconfig` command helps us to know our local IP address.

## Find the IP address of google.com
`ping google.com` command helps us to know IP address of `google.com`

## How to check if Internet is working using CLI?
- `ping` command along with a known web address or IP adress can help us to know if Internet is working or not.
- Example: `ping google.com`. If this returns some responses, Internet is working, otherwise not.

## Where is the node command located? What about code?
`which node` and `which code`
- The which command helps us to get the exact location of node and code.
- If it doesn't exist, it will not return anything.
