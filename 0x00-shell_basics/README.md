`The 0-current_working_directory script prints the current working directory`
`The 1-listit script prints the contents of a direcory`
`The 2-bring_me_home script takes a user to the home directory or root`
`The 3-listfiles script prints current directory contents in a long format`
`The 4-listmorefiles script prints more files including hidden ones`Task 4: ls -la === list directory contents in long form, including hidden files

Task 5: ls -la Note: Are files inherently ordered?

Task 6: mkdir /tmp/holberton Create a holberton directory inside the tmp directory

Task 7: mv /tmp/betty /tmp/holberton/betty Move file betty, which is located inside the tmp directory, to the holberton directory, which is also located inside the tmp directory. This exercise required some dir traversing.

Task 8: rm /tmp/holberton/betty Remove file betty located in tmp/holberton directory.

Task 9: rmdir /tmp/holberton Remove directory holberton located in directory tmp.

Task 10: cd - Change directory to the previous directory you were in.

Task 11: ls -la . .. /boot List all files/directories, including hidden files/directories, from 3 separate directories: current directory, parent of working directory, and /boot directory. The ls command allows multiple directories to be listed separated by spaces.

Task 12: file /tmp/iamafile Prints the type of file iamafile.

Task 13: ln -s /bin/ls ls Create a symbolic link named ls for /bin/ls

Task 14: cp -u *.html .. Copy all html files from the current directory to the parent directory, but only copy files that didn't exist in the parent directory or are newer versions than the ones that already exist in the parent directory. The -u option didn't show on the terminal manual page. The -u option copies the file into the directory if its a newer version. If the file doesn't exist in the directory, it will copy over. The -n option works for copying files that don't exist in the parent directory, but it doesn't check if the file is a newer version or not.

Task 15: mv [[:upper:]]* /tmp/u Move all files that begin with a capital letter to /tmp/u

Task 16: rm *~ Deletes all files in the current directory that end with a ~

Task 17: mkdir -p welcome/to/holberton Create directory welcome in current directory. Create directory to inside directory welcome. Create directory holberton inside directory to. The -p option creates any intermediate directories in the path argument.

Task 18: ls -pam List all files and directories of the current directory, separated by commas. Directory names should end with a /. The listing should be alph ordered, except for dot (.) or dot dot (..), which should be listed at the beginning. The -a option is to show any hidden files. The -p option writes a / at the end of directory names. The -m option streams the output, separating each listing with commas.

Task 19: 0 string HOLBERTON School data !:mime School Create a magic file called holberton.mgc that can be used with the command file to detect School data files. School data files always contain School at offset 0.

This exercise was much different from the previous exercises. From what I understand, the magic file is used to detect patterns in files and will give a specified output depending on a matching pattern. The first argument is a number representing the offset. The second argument is the data type you are searching for. In our case, it is a string. The third argument is the data you are searching for. In our case, School, which we specified as a string in the second argument. The fourth argument is the message you want to output on match. If the search matches, it will output this message. The last argument is separated by a line. Since the fourth argument can be long and contain multiple strings, we separate the fourth and fifth arguments with this new line. This last argument can be multiple different things. In this case, a MIME type. According to bash manual, a "MIME type is given on a separate line, which must be the next non-blank or comment line after the magic line that identifies the file type". I knew to search for a MIME type because the example provided: $ file --mime-type -m holberton.mgc * The above returns message "School" when matching a MIME ?? Not exactly sure, but this is what I can tell from what I've tested out and can see from the output and examples. $ file -m holberton.mgc * The above will return message "School data" for any offset 0 School matches. A cool thing to note is that the file command is compiling and running the magic file. So there is no need to compile to magic "permanently". NOTE: Compiling a magic source file: $ file -C -m .mgc This produces the compiled magic file. $ file -i -m .mgc * This allows you to use the compiled file by specifying its name using the -m switch again
