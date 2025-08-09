Over the wire.   Bandit Level 0 → Level 1
Level Goal
The password for the next level is stored in a file called readme located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.

1. ssh bandit0@bandit.labs.overthewire.org -p 2220
2. use the ls command once you login.
3. you will see a file called readme
4. use the cat command to see the content of the file and you will get the answer. see the picture below.

￼<img width="879" height="204" alt="Screenshot 2025-05-30 at 1 17 53 PM" src="https://github.com/user-attachments/assets/9e279e4a-83b3-48eb-9aed-c48c07d4379a" />


Bandit Level 1 → Level 2
Level Goal
The password for the next level is stored in a file called - located in the home directory

1. ssh bandit1@bandit.labs.overthewire.org -p 2220
2. use the password which you find in the previous level and you will get successful login
3. use the cat command and it will show you a file “ - “
4. in order to read the file who has special character you have use ./ before the file name. In this case you will use the command cat ./ - and you will get the password. see the picture below

￼
<img width="1440" height="111" alt="Screenshot 2025-05-30 at 1 20 21 PM" src="https://github.com/user-attachments/assets/dd9338ea-2349-4043-9666-55a12992ed85" />


Bandit Level 2 → Level 3
Level Goal
The password for the next level is stored in a file called spaces in this filename located in the home directory

1. ssh bandit2@bandit.labs.overthewire.org -p 2220
2. use the password which you find in the previous level and you will get successful login
3. use the ls command and it will show you the file name
4. Here the file name contain spaces in between in it, so if you use the cat command and simply type the name of the file you will get error, so whenever there is empty spaces in the file name you would use “” in order to read the content of the file, so here we will use the command cat “spaces in this filename” and this “” will tell the cat command this is all a single file name and we will get our answer. see the picture below.

￼<img width="1440" height="111" alt="Screenshot 2025-05-30 at 1 24 14 PM" src="https://github.com/user-attachments/assets/92905f60-95fb-4688-aac3-23a6e6df9928" />



Bandit Level 3 → Level 4
Level Goal
The password for the next level is stored in a hidden file in the inhere directory.

1. ssh bandit3@bandit.labs.overthewire.org -p 2220
2. Use the password which you find in the previous level and you will get successful login
3. As it’s mention in the question that the password is stored in the hidden directory, to find the hidden directory we will use the command ls -la it will show all the hidden files in the result. as we have got inhere directory.
4. we will go into the inhere directory by using the command cd inhere
5. then if we use ls it will not any command, so we will use the ls -la to check the hidden file and we get the hidden file it’s name is ….Hiding-From-You.
6. we will use the cat ….Hiding-From-You and we will get the password for next level.see the picture below.

￼<img width="628" height="501" alt="File Actions Edit View Help" src="https://github.com/user-attachments/assets/9b451c8d-96fd-4a63-b064-2c71309d7872" />


Bandit Level 4 → Level 5
Level Goal
The password for the next level is stored in the only human-readable file in the inhere directory. Tip: if your terminal is messed up, try the “reset” command.

1. ssh bandit4@bandit.labs.overthewire.org -p 2220
2. Use the password which you find in the previous level and you will get successful login
3. Then we will us the command ls and we find out there is a directory it’s name is inhere, we move to the directory cd inhere
4. and then we will use ls -la command and we get the result in which we can see there is number of files.
5. The challenge is to find the human readable format file, so we will use the command file ./* this will show the type of the files in which data is present. as we can see the file07 is in the ASCII format so this will give the password for next level
6. we will use the cat ./-file07 and we get the result.  see the picture below.


￼<img width="554" height="653" alt="File Actions Edit View Help" src="https://github.com/user-attachments/assets/3b71a973-2ee9-40b9-a345-175b47ce52a8" />


Bandit Level 5 → Level 6
Level Goal
The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties:
* human-readable
* 1033 bytes in size
* not executable

1. ssh bandit5@bandit.labs.overthewire.org -p 2220
2. Use the password which you find in the previous level and you will get successful login
3. As the question mentioned in it the file we have to find it’s inhere directory, we will use ls command and we find the inhere directory.
4. use cd inhere command to go into the directory then use the ls command find so many directories, it will be a waste of time to go through each directory and in that go through every file.
5. the hint in the question is that we have to find the 1033 bytes of file in size. so we can use the grep command and in order to check the size we will use the du -ab command.
6. combining this we get the command to find our file is du -ab | grep 1033, this command will list out the file in size of 1033 bytes only.
7. and we get the file name, we use the cat command to get the password for next question. see the picture below.
￼

<img width="1042" height="457" alt="Screenshot 2025-05-30 at 4 13 36 PM" src="https://github.com/user-attachments/assets/44e8f2c7-0d4d-4de1-b65c-9a4236df72fa" />


Bandit Level 6 → Level 7
Level Goal
The password for the next level is stored somewhere on the server and has all of the following properties:
* owned by user bandit7
* owned by group bandit6
* 33 bytes in size

1. ssh bandit6@bandit.labs.overthewire.org -p 2220
2. Use the password which you find in the previous level and you will get successful login
3. Now we have to find a specific file in which belong to user bandit7 group bandit6 and file size should be 33 bytes. Oh for this we have to use a lengthy command, no worries I will explain it to you.
4. the command we use is find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null you will get the result where you can find the password file.
5. The above command searches the entire system (/) for regular files (-type f) that are exactly 33 bytes in size (-size 33c), owned by user bandit7 (-user bandit7) and belonging to group bandit6 (-group bandit6), while hiding all error messages like "Permission denied" using 2>/dev/null to keep the output clean.
6. we got the path we use the command cat before it and we get the password of the next challenge . see the picture below. 

￼
<img width="763" height="376" alt="Screenshot 2025-05-30 at 4 24 38 PM" src="https://github.com/user-attachments/assets/777695a2-67a4-4098-b724-85bf9428d9b7" />


Bandit Level 7 → Level 8
Level Goal
The password for the next level is stored in the file data.txt next to the word millionth

1. ssh bandit7@bandit.labs.overthewire.org -p 2220
2. Use the password which you find in the previous level and you will get successful login
3. Use the ls command and you can see the data.txt file. If you use cat data.txt you will see a high bunch of username and their passwords. but we need only one in which millionth should be involved
4. Actually if you look into the question it’s really easy, when i first check the file data.txt it’s contains many username and password, so what i did is. I use a single command and i got the answer.
5. so I use cat data.txt | grep millionth. This will highlight only the part where millionth is present. see the picture below

￼<img width="754" height="331" alt="File Actions Edit View Help" src="https://github.com/user-attachments/assets/9213bade-146a-43db-a5f7-f7e110397585" />


Bandit Level 8 → Level 9
Level Goal
The password for the next level is stored in the file data.txt and is the only line of text that occurs only once

1. ssh bandit8@bandit.labs.overthewire.org -p 2220
2. Use the password which you find in the previous level and you will get successful login
3. use the ls command and we get the data.txt file, now we use the cat command to see the content cat data.txt, wow again there are so many passwords, we have to filter out and want the only line which is not repeated.
4. so we will use the commands sort , uniq , so sort command sort out the number of lines then uniq command will find out the uniq line which is only represent 1 time. so the final command to find the correct output is cat data.txt | sort | uniq -u,   where “ -u” flag will print the result of the line from the file which appears only 1 time and wallah, we got our answer. see the picture below.

￼<img width="545" height="445" alt="File Actions Edit View Help" src="https://github.com/user-attachments/assets/abfd4a8c-516a-4e2e-aaba-d5aeb1636b52" />


Bandit Level 9 → Level 10
Level Goal
The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.

1. ssh bandit9@bandit.labs.overthewire.org -p 2220
2. Use the password which you find in the previous level and you will get successful login
3. use the ls command and we get the data.txt file, now we use the cat command to see the content cat data.txt, we can see that  gibberish language is used in the file and we want only the human readable format.
4. Now instead of cat command we will use the strings command to see the content of the file, which is only in the human readable format and we have the find the password for next challenge and hint is, the password is beside several  = characters . so our final command will be strings data.txt | sort | grep = . it will show you the password, you can only use strings data.txt | grep =. see the picture below.

￼
<img width="804" height="468" alt="Screenshot 2025-05-30 at 4 58 45 PM" src="https://github.com/user-attachments/assets/7d7bb17a-04b2-46e2-a8c5-cec3dd5725f6" />


Bandit Level 10 → Level 11
Level Goal
The password for the next level is stored in the file data.txt, which contains base64 encoded data

1. ssh bandit10@bandit.labs.overthewire.org -p 2220
2. Use the password which you find in the previous level and you will get successful login
3. use the ls command and we get the data.txt file,  Here we have to use the command base64 to decode the password that is in data.txt. so if you want to know more about the base64 command how to use it and for what purpose it’s used for , use the man command before it and it will give you the information.
4. Here we will use the command base64 -d data.txt and we get our password for the next challenge, see the picture below.

￼<img width="878" height="301" alt="Screenshot 2025-05-30 at 6 14 17 PM" src="https://github.com/user-attachments/assets/a4e5fde0-0dd7-4f47-9af1-ec33f0dab1e2" />


Bandit Level 11 → Level 12
Level Goal
The password for the next level is stored in the file data.txt, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions


1. ssh bandit11@bandit.labs.overthewire.org -p 2220
2. Use the password which you find in the previous level and you will get successful login
3. use the ls command and we get the data.txt file,  as we know that we have to decode the text from the file by shifting the character to 13 position so like A should be M, B should be N so on…..  For this we will use the command tr which help us to shift the character we will use the full command like tr “A-Za-z” “N-ZA-Mn-za-m” Translate each letter A–Z and a–z to the letter 13 places ahead in the alphabet, wrapping around after Z (ROT13)
4. The full command will be like cat data.txt | tr “A-Za-z” “N-ZA-Mn-za-m”   and in future if you want to move the character to 13 position away then you can build a alias command like rot13="tr 'A-Za-z' 'N-ZA-Mn-za-m'"
5. You will get the password for next challenge. See the picture below
￼

<img width="646" height="433" alt="File Actions Edit View Help" src="https://github.com/user-attachments/assets/112ce239-0bed-43d4-b98c-0a86831e1111" />


Bandit Level 12 → Level 13
Level Goal
The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv (read the manpages!)



1. ssh bandit12@bandit.labs.overthewire.org -p 2220
2. Use the password which you find in the previous level and you will get successful login
3. use the ls command and we get the data.txt file,  when we use the command cat data.txt we can see the file content in Hexadecimal format. to decode this we will follow the steps which are mentioned in the question.
4. Creating a Temporary Workspace cd /tmp Changes the current directory to /tmp (a temporary directory where users can create files). Then mktemp -d Creates a uniquely named temporary directory tmp/tmp.IKY9wJu5gk (your directory name may vary).  cd /tmp/tmp.IKY9wJu5gk Moves into the newly created temporary directory. cp ~/data.txt /tmp/tmp.IKY9wJu5gk Copies data.txt from the home directory to the temporary directory.  This allows us to work on the file without modifying the original. ls Lists files in the current directory. 
5. Decoding the Hexdump  xxd -r data.txt comdata.txt Reverses the hexdump (xxd -r) to convert it back to binary and saves it as comdata.txt xxd -r is used to reconstruct binary data from a hexdump. Then ls command and we can see comdata.txt data.txt cat comdata.txt Displays the contents of comdata.txt.  Garbled binary data (not human-readable) The file is still compressed/encoded, so it needs further processing.
6. First Decompression (Gzip) mv comdata.txt comdata.gz Renames comdata.txt to comdata.gz to indicate it's a Gzip file. The .gz extension helps tools like gzip recognize the file type.gzip -d comdata.gz Decompresses the Gzip file (-d flag) Creates comdata (the decompressed file) The file is now decompressed, but it's still not plaintext. xxd comdata Another hexdump (indicating the file is still binary) The file is likely compressed again (Bzip2 format)
7. Second Decompression (Bzip2)  mv comdata comdata.bz2 Renames comdata to comdata.bz2 to indicate it's a Bzip2 file Prepares the file for Bzip2 decompression. bzip2 -d comdata.bz2 ecompresses the Bzip2 file (-d flag) creates comdata (decompressed file) The file is now further decompressed. Then ls command to see comdata data.txt. cat comdata Contains references to data5.bin and data6.bin (a tar archive) The file is a tar archive, which needs extraction.
8. Extracting the Tar Archive mv comdata comdata.tar Renames comdata to comdata.tar to indicate it's a tar archive  Prepares the file for extraction with tar. tar -xf comdata.tar Extracts the contents of the tar archive (-x for extract, -f for file) Creates data5.bin. tar -xf data5.bin Extracts the contents of data5.bin (another tar archive) Extracts the next file (data6.bin) then ls comdata.tar data5.bin data6.bin data.txt Shows the extracted file data6.bin
9. Third Decompression (Bzip2 Again) xxd data6.bin shows binary data with a Bzip2 header (BZh91) tar -xf data6.bin Extracts the contents of data6.bin (another tar archive)  Creates data8.bin 
10. Final Decompression (Gzip) : xxd data8.bin  Displays the hexdump of data8.bin shows binary data with a Gzip header (1f8b) mv data8.bin data8.gz Renames data8.bin to data8.gz to indicate it's a Gzip file Prepares the file for Gzip decompression gzip -d data8.gz Creates data8 The file is now decompressed and contains the password ls comdata.tar data5.bin data6.bin data8 data.txt. cat data8  Displays the contents of data8  The password for the next level is revealed. See the pictures below.
￼
￼<img width="831" height="837" alt="Screenshot 2025-06-02 at 11 55 04 AM" src="https://github.com/user-attachments/assets/1f8f6b1e-77eb-402e-9340-3dd39d2bfe84" />

<img width="1123" height="815" alt="Screenshot 2025-06-02 at 11 56 45 AM" src="https://github.com/user-attachments/assets/0a70eeca-1cb2-4fd7-a1e5-1177120ef7c7" />

<img width="1435" height="805" alt="Screenshot 2025-06-02 at 11 57 34 AM" src="https://github.com/user-attachments/assets/dad0c3ef-63f1-4f39-80f9-608e4dd66eb6" />

<img width="1407" height="314" alt="Screenshot 2025-06-02 at 11 58 21 AM" src="https://github.com/user-attachments/assets/86485a84-ec20-4363-b587-3438bba5a8cc" />

￼
￼


Bandit Level 13 → Level 14
Level Goal
The password for the next level is stored in /etc/bandit_pass/bandit14 and can only be read by user bandit14. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. Note: localhost is a hostname that refers to the machine you are working on

1. ssh bandit13@bandit.labs.overthewire.org -p 2220
2. Use the password which you find in the previous level and you will get successful login
3. use the ls command and we get the file sshkey.private, we will see the content of the file cat sshkey.private and we get the result. As in the question it’s already mention that the file /etc/bandit_pass/bandit14  can only accessible by user bandit14. We will use this private key to login as bandit14.
4. as the private key it’s already in a file format, we will use the command ssh -i sshkey.private bandit14@localhost  -p 2220 Login as user bandit14 on the same machine (localhost = 127.0.0.1) so we get the option to login as bandit14 user on the same machine.
5. As we login as bandit14 we will use this command to get the password from the file /bandit14, cat /etc/bandit_pass/bandit14 and wallah we get the password. See the picture below.

￼
<img width="1440" height="900" alt="Screenshot 2025-06-02 at 12 30 11 PM" src="https://github.com/user-attachments/assets/04860fcd-490b-453d-8d9a-36d3b0ac7e92" />

<img width="1440" height="146" alt="Screenshot 2025-06-02 at 12 42 43 PM" src="https://github.com/user-attachments/assets/38bcd6db-d63b-4cbd-a46a-a03b4d102eab" />

￼

Bandit Level 14 → Level 15
Level Goal
The password for the next level can be retrieved by submitting the password of the current level to port 30000 on localhost.

1. As we already login as bandit14 user we just have to submit the password which we achieved in previous challenge, so for that we use netcat command nc localhost 30000 so we are submitting the previous challenge password on the port 30000 by using the netcat command and get the password for next challenge, see the picture below.
￼

<img width="1390" height="129" alt="Screenshot 2025-06-02 at 12 55 06 PM" src="https://github.com/user-attachments/assets/00d62df0-9eb1-4fca-8b3e-aa309da4d960" />


Bandit Level 15 → Level 16
Level Goal
The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL/TLS encryption.
Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.

1. ssh bandit15@bandit.labs.overthewire.org -p 2220
2. Use the password which you find in the previous level and you will get successful login.
3. Now we have to connect through SSL/TLS so for this we will use the command openssl s_client -connect localhost:30001 and then it will give the space to enter the password which we get from previous challenge and then it will give you the password for next challenge. See the picture below.
￼
￼<img width="1321" height="311" alt="Screenshot 2025-06-02 at 1 04 40 PM" src="https://github.com/user-attachments/assets/1f2c40d8-fb6b-475f-8088-11179ac5f86e" />

<img width="1440" height="140" alt="Screenshot 2025-06-02 at 1 07 48 PM" src="https://github.com/user-attachments/assets/d806734b-eef1-4702-bc14-86ebab1bf6a8" />


Bandit Level 16 → Level 17
Level Goal
The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. First find out which of these ports have a server listening on them. Then find out which of those speak SSL/TLS and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.
Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage.

1. ssh bandit15@bandit.labs.overthewire.org -p 2220
2. Use the password which you find in the previous level and you will get successful login.
3. as we have to figure it out, which ports are open we will use the commnad nmap -sV localhost -p 31000-32000, this will give us the port with the services name that they are running on, as we can see port 31790 look obvious that it will have the password for the next level.
4. we will use the ncat -ssl localhost 31790 command to listen on that port, we use ncat instead of nc because nc won’t work on ssl ports , so enter the command and enter the password of the previous level and we get the SSH RSA key.
5. we will make a temporary directory in tmp directory and in that directory create a file and save the SSH RSA key which we got.
6. Then use the -ssh -i  private.key { which is the file name we created } bandit17@localhost -p 2220 and wallah we are in the bandit17 which is next level.


￼<img width="1440" height="900" alt="Screenshot 2025-06-10 at 5 25 29 PM" src="https://github.com/user-attachments/assets/29f26b53-b86a-460b-8555-5e42d1aec85c" />

<img width="1440" height="900" alt="Screenshot 2025-06-10 at 5 25 42 PM" src="https://github.com/user-attachments/assets/42662bc8-7fbd-4b72-a94c-79e545a1ecb4" />


￼

Bandit Level 17 → Level 18
Level Goal
There are 2 files in the homedirectory: passwords.old and passwords.new. The password for the next level is in passwords.new and is the only line that has been changed between passwords.old and passwords.new
NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19

1. As we have already login as bandit17 user we will use the ls command to see the files passwords.old and passwords.new.
2. As per the question we have to find a line which is in the passwords.new but not in the passwords.old
3. We will use the command diff  passwords.old  passwords.new it will check all the files lines and carry out the difference and you will get the password for the next challenge
4. Moreover what you can do is you can use the sort command how sort passwords.old  passwords.new  | uniq -u . See the picture below.

￼<img width="1115" height="220" alt="Screenshot 2025-06-10 at 6 11 00 PM" src="https://github.com/user-attachments/assets/908efe07-ca0d-48c4-bf7f-afaef5b52158" />


Bandit Level 18 → Level 19
Level Goal
The password for the next level is stored in a file readme in the homedirectory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.

1. As soon as you login ssh bandit18@bandit.labs.overthewire.org -p 2220 , it runs the pre-configured command and kicks you out. You don’t get a usable shell. So what we can do here instead of normal login we will try to use the remote shell in order to access this level.
2. First we will check if it works or not, so we will use this command ssh bandit18@bandit.labs.overthewire.org -p 2220 ls, at the end we have use “ls” command in order to check if its working or not, as we can see we get the result.
3. Now we will use a command which initiate a remote shell so we can use multiple commands and not have to repeat   ssh bandit18@bandit.labs.overthewire.org -p 2220 {command } . How we can initiate that.
4. We will use this command ssh bandit18@bandit.labs.overthewire.org -p 2220 -t /bin/sh -t /bin/sh forces the SSH server to give you a shell instead of running and quitting a restricted command. It's a common trick in CTFs and security games like OverTheWire to bypass limited shells. We get the access of the shell.
5. now we will use ls and we get the readme file, we will use the cat command to read the content of the file and hurray we got the results.  See the picture below.

￼
<img width="667" height="719" alt="bandit" src="https://github.com/user-attachments/assets/802c931e-3865-489a-8c5a-7029df2eefdb" />


Bandit Level 19 → Level 20
Level Goal
To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.


1. ssh bandit19@bandit.labs.overthewire.org -p 2220
2. Use the password which you find in the previous level and you will successful login. we have to find out the password for the next level and upon reading the challenge setuid binary file is there to homedirectory so we can execute it and find the password for next challenge which is in the (/etc/bandit_pass).
3. But main question what is the setuid let’s learn about it first When an executable file has the setuid bit set, it runs with the permissions of the file's owner, not the user who runs it. It allows normal users to temporarily perform tasks with higher privileges, safely, without giving them full access.
4. so first we will use the ls command and we see the bandit20-do file, in order to check the permission of the file and we can see “s” in the user permission which means it has setuid permission only root can access it.
5. so in order to check the id we will use the command ./{filename} id it will give the result of id which can access the files. so we can 11020 is the bandit20 user access so we will use it.
6. ./bandit20-do cat /etc/bandit_pass/bandit20 and we get the content of the file 


<img width="951" height="264" alt="Screenshot 2025-06-15 at 11 44 19 AM" src="https://github.com/user-attachments/assets/23f7495d-e130-4f91-b546-6ec75b83928f" />

￼


Bandit Level 20 → Level 21
Level Goal
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).
NOTE: Try connecting to your own network daemon to see if it works as you think.


1. ssh bandit19@bandit.labs.overthewire.org -p 2220
2. Use the password which you find in the previous level and you will successful login. With the question we have to setup a server in which we have to setup the password of level 20 challenge and we will use the command echo -n “ password “ | nc -lp 1234 & 	•	echo prints the string to standard output. -n tells echo not to add a newline (\n) at the end — this is crucial because the binary might expect an exact string match. So this part is preparing to send the password string exactly as-is. ” | “Pipes the output of echo (the password) into the next command (nc), meaning the password will be sent into the TCP connection once it's made.nc -l -p 1234 nc is netcat, a powerful networking tool. -l tells it to listen (act like a server). -p 1234 tells it to listen on port 1234. 
3. As we have setup the server now we will use the file suconnect in order to get the password for next level.
4. we will use the command ./suconnect 1234 and wallah we get the password for next level, see the picture below.



￼<img width="1440" height="900" alt="Screenshot 2025-06-17 at 5 55 35 PM" src="https://github.com/user-attachments/assets/32c2f73e-b602-4e56-bee9-6d7776b11f71" />


Bandit Level 21 → Level 22
Level Goal
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.


1. bandit21@bandit:/etc/cron.d$ ls → Lists all files in /etc/cron.d, showing scheduled cron jobs including cronjob_bandit22.
2. Output: clean_tmp cronjob_bandit22 cronjob_bandit23 cronjob_bandit24 e2scrub_all otw-tmp-dir sysstat → Shows the names of all cron job files in this directory.
3. cat cronjob_bandit22 → Displays the contents of the file cronjob_bandit22, showing how and when the cron script is executed.
4. Output: 
      @reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
      * * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
 → First line runs the script once on reboot; second line runs it every minute — both as user bandit22, with all output hidden.
5. cat /usr/bin/cronjob_bandit22.sh → Shows the full shell script that the cron job is executing.
6. Output: #!/bin/bash
       chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
       cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
  → The script runs with Bash, makes a temp file world-readable, and writes the password of bandit22 into that file.
7. As we get the tmp file we will look into that file by using the cat command cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv and we get the password for the next level.


￼<img width="948" height="327" alt="Screenshot 2025-06-17 at 6 28 39 PM" src="https://github.com/user-attachments/assets/1c1b75fb-3aed-428b-be7e-fd75d34c1c4c" />

￼<img width="608" height="68" alt="bandit21@bandit~$ cat tmpt706lds9S0RqQh9aMcz6ShpAoZKF7fgv" src="https://github.com/user-attachments/assets/b81fecba-bea9-473a-850e-dc9ce152f08a" />


Bandit Level 22 → Level 23
Level Goal
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.
NOTE: Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.

1. Log in to bandit22 using SSH. → You're now inside the server as the user bandit22.
2. Go to the /etc/cron.d directory. → This is where scheduled cronjob files are stored.
3. Open the file named cronjob_bandit23. → This file shows a script that runs every minute as bandit23.
4. See that the script it runs is located at /usr/bin/cronjob_bandit23.sh. → This tells you which script is being executed automatically.
5. Open and read the contents of cronjob_bandit23.sh. → You'll find a bash script that uses variables to build a file path.
6. The script gets the username using 'whoami'. → Since the cron runs as bandit23, the username stored is bandit23.
7. It creates a hashed string using 'I am user bandit23' and md5sum. → This creates a unique filename based on the username.
8. It uses that hash to name a file in the /tmp directory. → The script will store something in /tmp/<hash>.
9. It copies the password file of bandit23 into that tmp file. → This step stores the secret password in a file you can access.
10. You re-create the hash by running the same 'echo I am user bandit23 | md5sum' logic. → This gives you the filename where the password was saved.
11. You go to the /tmp directory and read the file with that hash name. → You now have access to the password that was hidden there.
12. Use that password to log in as bandit23. → Mission accomplished — you're ready for the next level!

￼<img width="916" height="379" alt="Screenshot 2025-06-26 at 7 22 47 PM" src="https://github.com/user-attachments/assets/8913db14-2149-4cea-8d34-177f2371aad6" />


Bandit Level 23 → Level 24
Level Goal
A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in /etc/cron.d/ for the configuration and see what command is being executed.
NOTE: This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!
NOTE 2: Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…


1. Log in to bandit23 using SSH. → You are now inside the server as the user bandit23.
2. Go to the directory /etc/cron.d. → This is where all the system's cron job definitions are stored.
3. List the files in that directory and find cronjob_bandit24. → This file contains the cron task for the bandit24 user.
4. Open and read cronjob_bandit24. → You'll see that it runs a script /usr/bin/cronjob_bandit24.sh every minute and at reboot, as user bandit24.
5. Open and read the script /usr/bin/cronjob_bandit24.sh. → The script gets the current username (whoami), which would be bandit24 when cron runs it.
6. The script changes directory to /var/spool/bandit24/foo. → It then loops through all files in that folder and checks if the owner is bandit23.
7. If a file is owned by bandit23, the script executes it with a 60-second timeout. → After running, the file is deleted.
8. You can exploit this by putting a script into /var/spool/bandit24/foo as user bandit23, which will be executed by bandit24's cron.
9. Create a simple bash script that reads the bandit24 password and writes it into /tmp. → For example, a script that runs: cat /etc/bandit_pass/bandit24 > /tmp/certa_test.txt.
10. Make the script executable using chmod +x.
11. Copy that script into /var/spool/bandit24/foo/.
12. Wait a minute for the cronjob to run, then check /tmp/certa_test.txt.
13. Read the contents of /tmp/certa_test.txt. → You will find the password for bandit24.
14. Use that password to log in as bandit24. → Done! You're now ready to proceed to the next level.


<img width="972" height="491" alt="Screenshot 2025-06-29 at 2 01 15 PM" src="https://github.com/user-attachments/assets/89925963-bea7-4264-880a-4007659c86b0" />

￼<img width="1163" height="145" alt="Screenshot 2025-06-29 at 2 01 29 PM" src="https://github.com/user-attachments/assets/e88833d7-1338-404a-8823-f59409caebd9" />

￼


Bandit Level 24 → Level 25
Level Goal
A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing. You do not need to create new connections each time

1. Log in to bandit24 using SSH with the password gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8. → You are now inside the server as the user bandit24.
2. Create a temporary working directory using the command: mktemp -d → This will create something like /tmp/tmp.ABCD1234.
3. Move into the newly created directory: cd /tmp/tmp.ABCD1234
4. Create a file named brute.sh using any text editor like vim or nano.
5. Paste the following script into brute.sh:
#!/bin/bash

# Known password for bandit24
PASSWORD="gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8"

# Output files
COMBO_FILE="possibilities.txt"
OUTPUT_FILE="file.txt"

# Clean up any old files
rm -f "$COMBO_FILE" "$OUTPUT_FILE"

echo "[*] Generating password + PIN combinations..."

# Generate all combinations like: <password> <PIN>
for PIN in $(seq -w 0000 9999); do
    echo "$PASSWORD $PIN" >> "$COMBO_FILE"
done

echo "[*] All combinations saved to $COMBO_FILE"
echo "[*] Sending all 10,000 attempts through netcat..."

# Send all attempts in one go with a timeout (to avoid hanging)
cat "$COMBO_FILE" | timeout 15s nc localhost 30002 > "$OUTPUT_FILE"

echo "[✔] Brute-force finished. All responses saved to $OUTPUT_FILE"

# Try to find the correct password line
CORRECT_LINE=$(grep "Correct!" "$OUTPUT_FILE")

if [[ -n "$CORRECT_LINE" ]]; then
    echo ""
    echo "✅ SUCCESS! Found valid combination:"
    echo "$CORRECT_LINE"
else
    echo ""
    echo "❌ No correct PIN found. Try increasing timeout or check server behavior."
fi

→ This script loops through all 4-digit PINs from 0000 to 9999. → It tests each PIN with the known password by using the bandit24-do wrapper.
6. Make the script executable: chmod +x brute.sh
7. Run the brute-force script: ./brute.sh
→ The script will try every PIN until it sees the word "Correct!" → When that happens, it prints the password of bandit25.
8. Once the script finds the correct combo, you will see output like: Correct! The password of user bandit25 is iCi86ttT4KSNe1armKiwbQNmB3YJP3q4
9. Use this password to SSH into bandit25 for the next level. → Done!

￼
￼<img width="715" height="531" alt="bandit24@bandittmptmp uYan4wdwjz$ vim brute st" src="https://github.com/user-attachments/assets/593dc7df-2006-4a83-af0f-eb1051007252" />

<img width="676" height="396" alt="Wrong! Please enter the correct current password and pincode  Try again" src="https://github.com/user-attachments/assets/23aa4bfc-a1b4-499b-b4dc-5db8af9ab652" />



Bandit Level 25 → Level 26
Level Goal
Logging in to bandit26 from bandit25 should be fairly easy… The shell for user bandit26 is not /bin/bash, but something else. Find out what it is, how it works and how to break out of it.
NOTE: if you’re a Windows user and typically use Powershell to ssh into bandit: Powershell is known to cause issues with the intended solution to this level. You should use command prompt instead.

1. Log in to bandit25 using SSH. → You are now inside the server as the user bandit25.
2. Check the default shell for bandit26 using /etc/passwd. → You will see that bandit26 uses /usr/bin/showtext as its shell instead of /bin/bash.
3. View the contents of /usr/bin/showtext. → This script sets the terminal type and uses more to display a file called text.txt, then exits.
4. Look inside your home directory as bandit25. → You will find a private key file named bandit26.sshkey.
5. Use cat to print the contents of bandit26.sshkey. → Copy the entire private key (from -----BEGIN to -----END) to your local machine.
6. On your local machine, create a file named bandit26.key and paste the copied key into it. → Save the file and run chmod 600 bandit26.key to set correct permissions.
7. Resize your terminal window to be very short, around 5–10 lines tall. → This ensures that more will enter interactive mode when the text is shown.
8. SSH into bandit26 from your local machine using the key. → Use the command ssh -i bandit26.key bandit26@bandit.labs.overthewire.org -p 2220.
9. Wait for the --More-- prompt to appear. → This means more is now in interactive mode and is waiting for input.
10. Press v while in the interactive mode of more. → This will open the file in vim, the text editor.
11. Inside vim, type :set shell=/bin/bash and press Enter. → This sets the shell that vim will use when spawning a terminal.
12. Then type :shell and press Enter. → You now have a real interactive shell as bandit26.
13. Run cat /etc/bandit_pass/bandit26. → This will display the password for the next level, bandit27.

￼
￼<img width="763" height="774" alt="bandit25abandit-$ cat etcpassad grep bandit26" src="https://github.com/user-attachments/assets/5868d76d-6c13-493d-bcc5-8775cac6861a" />

<img width="794" height="198" alt="Screenshot 2025-06-30 at 6 20 49 PM" src="https://github.com/user-attachments/assets/1555f91e-cc18-4817-92b4-080007661fa5" />

<img width="645" height="408" alt="gef (httpsgithub comhugsygef) in optgef" src="https://github.com/user-attachments/assets/0fefbec3-9dbb-43f9-8e9b-2874fa6b15d5" />

￼

Bandit Level 26 → Level 27
Level Goal
Good job getting a shell! Now hurry and grab the password for bandit27!



1. Log in to bandit26 using SSH. → You are now inside the server as the user bandit26.
2. SSH into bandit26 from your local machine using the key. → Use the command ssh   bandit26@bandit.labs.overthewire.org -p 2220. use the password 
3. Wait for the --More-- prompt to appear. → This means more is now in interactive mode and is waiting for input.
4. Press v while in the interactive mode of more. → This will open the file in vim, the text editor.
5. Inside vim, type :set shell=/bin/bash and press Enter. → This sets the shell that vim will use when spawning a terminal.
6. Then type :shell and press Enter. → You now have a real interactive shell as bandit26.
7. List the files in the home directory of bandit26. → You will see a file named bandit27-do and text.txt.
8. Use the ls -la command to view detailed file permissions. → You will notice that bandit27-do is an executable file owned by bandit27, but it is set with the SUID bit, which means it runs as bandit27 when executed by bandit26.
9. Run the command ./bandit27-do to see its usage instructions. → The output tells you that you can run a command as bandit27, for example: ./bandit27-do id.
10. Run ./bandit27-do id. → The output confirms that although you are bandit26, the command is executed as bandit27 (euid=11027), proving that this program lets you run commands with bandit27’s privileges.
11. Run ./bandit27-do cat /etc/bandit_pass/bandit27. → This reads the password file for bandit27 and reveals the password: upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB.


￼<img width="1440" height="544" alt="Screenshot 2025-06-30 at 6 54 13 PM" src="https://github.com/user-attachments/assets/5b862524-2fd7-4e74-a1ff-756a47139db2" />

￼
<img width="1440" height="554" alt="Screenshot 2025-06-30 at 6 54 27 PM" src="https://github.com/user-attachments/assets/b1548306-16b9-4f38-9e52-e35f98b7d336" />

<img width="1440" height="631" alt="Screenshot 2025-06-30 at 6 54 47 PM" src="https://github.com/user-attachments/assets/aef02961-44ec-41fb-86bf-a0b137eee264" />

<img width="955" height="505" alt="Screenshot 2025-06-30 at 6 58 13 PM" src="https://github.com/user-attachments/assets/df40869e-d1ab-4b43-8500-763f5a81ac66" />


Bandit Level 27 → Level 28
Level Goal
There is a git repository at ssh://bandit27-git@localhost/home/bandit27-git/repo via the port 2220. The password for the user bandit27-git is the same as for the user bandit27.
Clone the repository and find the password for the next level.



Certainly! Here's the complete step-by-step guide from Bandit Level 26 → 27 in the exact format you requested, with each step and explanation written clearly:

1. Log in to bandit27 using SSH. → You are now inside the server as the user bandit27. → Use the command ssh bandit27@bandit.labs.overthewire.org -p 2220 and enter the password for bandit26.
2. Attempt to clone the Git repository directly to your home directory. → This will fail because you don’t have write permissions in the home directory. → Use the command git clone ssh://bandit27-git@localhost/home/bandit27-git/repo.
3. Create a temporary directory where you have full write access. → This is needed because you can't write in the home directory, but you can write in /tmp. → Use the command mktemp -d to create a temporary directory. It will return something like /tmp/tmp.jhix9uOi6F.
4. Change into the temporary directory that was just created. → You need to be in a directory where you can create files and folders. → Use the command cd /tmp/tmp.jhix9uOi6F (replace with your generated temp folder path).
5. Clone the repository from the localhost Git server on port 2220. → By default, SSH (used by Git) connects on port 22. Bandit’s SSH server uses port 2220, so you must specify it. → Use the command GIT_SSH_COMMAND='ssh -p 2220' git clone ssh://bandit27-git@localhost/home/bandit27-git/repo.
6. When prompted to confirm the SSH fingerprint, type "yes". → This confirms that you trust the remote server’s SSH key. → Then you'll be prompted for a password.
7. Enter the password for bandit27 when prompted. → This is required to authenticate as the git user bandit27-git.
8. Wait for the cloning process to complete. → Git will clone the repository into a folder called repo. You’ll see output like “Receiving objects... done.”
9. Verify that the repository has been cloned successfully. → Use the command ls to see the repo directory.
10. Change into the repo directory to view its contents. → Use the command cd repo.
11. List the contents of the repo directory. → Use the command ls -la to reveal all files, including hidden ones like .git.
12. Read the README file in the repository. → This file typically contains important instructions or information. → Use the command cat README.
13. Copy the password found inside the README file. → The output will show: The password to the next level is: see the picture below

￼<img width="1136" height="791" alt="Screenshot 2025-07-04 at 12 05 22 PM" src="https://github.com/user-attachments/assets/84b41b25-b379-41e8-bf8c-f5f8ba5cf71c" />



Bandit Level 28 → Level 29
Level Goal
There is a git repository at ssh://bandit28-git@localhost/home/bandit28-git/repo via the port 2220. The password for the user bandit28-git is the same as for the user bandit28.
Clone the repository and find the password for the next level.


1. Log in to bandit28 using SSH. → You are now inside the server as the user bandit28. → Use the command ssh bandit28@bandit.labs.overthewire.org -p 2220 and enter the password from level 27.
2. Attempt to clone the Git repository into your home directory. → This will fail due to permission issues, since you can't write files in the home directory. → Use the command git clone ssh://bandit28-git@localhost/home/bandit28-git/repo.
3. Create a temporary working directory in /tmp where you have write access. → This allows you to safely clone the repository. → Use the command mktemp -d. It returns something like /tmp/tmp.dhX3C3iYp9.
4. Change into the newly created temporary directory. → You need to run Git commands from within this location. → Use the command cd /tmp/tmp.dhX3C3iYp9.
5. Clone the Git repository from localhost using the correct port (2220). → Git uses SSH, which defaults to port 22, so we need to override it. → Use the command GIT_SSH_COMMAND='ssh -p 2220' git clone ssh://bandit28-git@localhost/home/bandit28-git/repo.
6. When prompted with the SSH fingerprint message, type "yes". → This accepts the host’s SSH key and allows the connection to proceed.
7. Enter the password for bandit28 when prompted. → This authenticates you for the Git operation.
8. Wait for the repository to be successfully cloned. → You’ll see output like “Cloning into ‘repo’... Receiving objects... done.”
9. Confirm the repository has been cloned. → Use the command ls and you should see a directory named repo.
10. Enter the cloned repository directory. → This is where the .git folder and project files are located. → Use the command cd repo.
11. List the contents of the repository. → Use the command ls -la to view the files. You will see a .git directory and a README.md file.
12. Read the contents of README.md. → This file appears to contain credentials, but the password is redacted. → Use the command cat README.md.
13. Review the Git commit history to investigate any previous changes. → This will help identify if the password was present in an earlier version. → Use the command git log.
14. Identify the commit that redacted the password. → The message for the latest commit says “fix info leak,” which suggests the password was removed there. → Note the commit hash: 674690a00a0056ab96048f7317b9ec20c057c06b.
15. Show the full changes introduced in that commit. → This reveals exactly what content was removed or changed. → Use the command git show 674690a00a0056ab96048f7317b9ec20c057c06b.
16. Read the diff output and recover the original password. → The diff will show that the line: - password: 4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7 was replaced with: + password: xxxxxxxxxx
17. Copy the revealed password for bandit29. → The real password is: see the pictures below.

￼
￼<img width="1126" height="733" alt="Screenshot 2025-07-04 at 12 25 53 PM" src="https://github.com/user-attachments/assets/11936306-e2c0-42be-a1c3-9d398e17c728" />

<img width="1055" height="719" alt="Screenshot 2025-07-04 at 12 26 23 PM" src="https://github.com/user-attachments/assets/3937c752-9eed-482c-8034-e6ada5f7a0e3" />


Bandit Level 29 → Level 30
Level Goal
There is a git repository at ssh://bandit29-git@localhost/home/bandit29-git/repo via the port 2220. The password for the user bandit29-git is the same as for the user bandit29.
Clone the repository and find the password for the next level.


1. Log in to bandit29 using SSH. → You are now inside the server as the user bandit29. → Use the command ssh bandit29@bandit.labs.overthewire.org -p 2220 and enter the password from the previous level.
2. Create a temporary directory in /tmp where you have write access. → This is necessary because you can’t write in your home directory. → Use the command mktemp -d. It will return a path like /tmp/tmp.3lsKj9zrJI.
3. Change into the newly created temporary directory. → This is where you’ll perform all Git operations. → Use the command cd /tmp/tmp.3lsKj9zrJI.
4. Clone the Git repository using the correct SSH port (2220). → Git uses SSH, which defaults to port 22. OverTheWire uses port 2220, so we override it. → Use the command GIT_SSH_COMMAND='ssh -p 2220' git clone ssh://bandit29-git@localhost/home/bandit29-git/repo.
5. When prompted to confirm the authenticity of the host, type yes. → This allows Git to proceed with the connection.
6. Enter the password for bandit29 when asked. → This authenticates the SSH connection and starts the cloning process.
7. Wait for the repository to clone successfully. → You’ll see a message like “Cloning into 'repo'…” and “Receiving objects… done.”
8. Verify that the repository has been cloned. → Use the command ls. You should see a folder named repo.
9. Change into the repo directory. → This is where the cloned Git project and history reside. → Use the command cd repo.
10. List the contents of the repo directory. → Use the command ls -la. You’ll see a README.md file and the .git folder.
11. Read the README.md file. → Use the command cat README.md. It shows that the password is redacted and replaced with <no passwords in production!>.
12. View the Git commit history. → Use the command git log. It shows two commits: one for the initial commit and one that changed the username.
13. View the diff of the latest commit to see what changed. → Use the command git show 3b8b91fc3c48f1a19d05670fd45d3e3f2621fcfa. → This shows that the username changed from bandit29 to bandit30, but the password was already redacted.
14. List all available branches in the repository. → Use the command git branch -a. → This will show you remote branches such as origin/dev and origin/sploits-dev.
15. Switch to the dev branch to see if it contains any hidden data. → Use the command git checkout dev. This checks out the branch and sets it to track origin/dev.
16. List the files again after switching branches. → Use the command ls -la. You’ll see a new folder named code and an updated README.md file.
17. Read the new README.md file. → Use the command cat README.md. It now reveals the actual password:
* username: bandit30
* password: see the pictures below


￼
￼
<img width="1116" height="785" alt="Screenshot 2025-07-04 at 12 49 37 PM" src="https://github.com/user-attachments/assets/f4775207-9f64-4acd-8ecb-d97e22d60a7a" />


￼


Bandit Level 30 → Level 31
Level Goal
There is a git repository at ssh://bandit30-git@localhost/home/bandit30-git/repo via the port 2220. The password for the user bandit30-git is the same as for the user bandit30.
Clone the repository and find the password for the next level.



1. Log in to bandit30 using SSH. → You are now inside the server as the user bandit30. → Use the command ssh bandit30@bandit.labs.overthewire.org -p 2220 and enter the password from the previous level.
2. Create a temporary working directory. → You need this because you don’t have write permissions in your home directory. → Use the command mktemp -d — it creates a folder like /tmp/tmp.At1cd6GT4Y.
3. Move into the new temporary directory. → Use the command cd /tmp/tmp.At1cd6GT4Y to enter it.
4. Clone the Git repository from the remote server using SSH on port 2220. → Use the command GIT_SSH_COMMAND='ssh -p 2220' git clone ssh://bandit30-git@localhost/home/bandit30-git/repo.
5. When asked to confirm the host authenticity, type yes. → This allows the SSH connection to proceed.
6. Enter the password for bandit30 when prompted. → This authenticates you to the repository.
7. Wait for the repository to be cloned successfully. → You’ll see “Cloning into 'repo'…” and “Receiving objects…” when it works.
8. List the contents of the directory. → Use the command ls to verify that the repo folder is present. You should see repo.
9. Change into the cloned repository directory. → Use the command cd repo.
10. List the contents of the repo to see what’s inside. → Use the command ls -la. → You’ll see a .git directory and a README.md file.
11. Read the README.md file. → Use the command cat README.md. → It says “just an epmty file... muahaha”, which is a trick.
12. List all available Git tags. → Use the command git tag. → You will see there is one tag called secret.
13. Attempt to check out the tag named secret. → Use the command git checkout secret. → Git returns an error: fatal: reference is not a tree: secret, which means it’s not pointing to a commit/branch — it's probably pointing to a blob.
14. Display the content that the tag secret is pointing to. → Use the command git show secret. → Git directly prints the password for the next level: see the picture below 


￼

Bandit Level 31 → Level 32
Level Goal
There is a git repository at ssh://bandit31-git@localhost/home/bandit31-git/repo via the port 2220. The password for the user bandit31-git is the same as for the user bandit31.
Clone the repository and find the password for the next level.

1. Log in to bandit31 using SSH. → You are now inside the server as the user bandit31. → Use the command ssh bandit31@bandit.labs.overthewire.org -p 2220 and enter the password from the previous level.
2. Create a temporary working directory. → This is needed because your home directory is restricted and not writable. → Use mktemp -d to create a directory like /tmp/tmp.qiF0nQsIvw.
3. Move into the new temporary directory. → Use the command cd /tmp/tmp.qiF0nQsIvw to switch into that location.
4. Clone the Git repository from the server on port 2220. → Use GIT_SSH_COMMAND='ssh -p 2220' git clone ssh://bandit31-git@localhost/home/bandit31-git/repo. → This will connect and clone the repository into a folder named repo.
5. You may see a host authenticity prompt. → Type yes to proceed. → You'll also see a warning that the known hosts file couldn’t be updated — this is fine and expected since you don’t have write permission in /home/bandit31.
6. Enter the password for bandit31-git (same as bandit31). → This authenticates your connection and clones the Git repository.
7. After cloning, check the contents. → Use ls and then cd repo to enter the repository folder. → Use ls -la to view hidden files as well.
8. Read the README.md file to understand the task. → It says you must push a file named key.txt with the exact content: May I come in? → It also specifies the branch: master.
9. Notice that the .gitignore file contains *.txt. → This would normally prevent key.txt from being added to the repository.
10. Force add the file using git add -f key.txt. → First, create the file using echo "May I come in?" > key.txt. → Then force it to be staged using git add -f key.txt.
11. Commit the changes. → Use git commit -m "Add key.txt as requested" to create the commit.
12. Push the commit to the remote repository using port 2220. → Use GIT_SSH_COMMAND='ssh -p 2220' git push. → Again, confirm host authenticity with yes if asked. → Enter the password for bandit31-git.
13. If the file contents were incorrect (like missing the ?), you’ll see:
remote: Wrong!
 ! [remote rejected] master -> master (pre-receive hook declined)
error: failed to push some refs
→ This means the Git server rejected your push due to incorrect file content.
14. Fix the file content and try again. → Make sure the file has exactly May I come in? (including the question mark). → Use echo "May I come in?" > key.txt again. → Then run git add -f key.txt, git commit -m "Fix content", and push again.
15. If the content is correct, you’ll see:
remote: Well done! Here is the password for the next level:
remote:
16. Save this password securely. → This is the password to log in as bandit32.

￼
￼
￼
￼


Bandit Level 32 → Level 33
Level Goal
After all this git stuff, it’s time for another escape. Good luck!



1. Log in to bandit32 using SSH. → You are now inside the server as the user bandit32. → Use the command: ssh bandit32@bandit.labs.overthewire.org -p 2220 and enter the password from the previous level.
2. Locate and examine the uppershell binary. → Run ls -la in your home directory. → You will see a file named uppershell with the SUID bit set: -rwsr-x--- 1 bandit33 bandit32 15140 ... uppershell. → This means the binary will run with bandit33's permissions when executed by bandit32.
3. Execute the uppershell binary. → Run ./uppershell to enter a restricted shell. → The shell will show: WELCOME TO THE UPPERCASE SHELL and give a prompt >>.
4. Try a basic command like ls. → Type ls and hit enter. → You’ll see an error: sh: 1: LS: Permission denied. → This tells you the shell only accepts uppercase commands, and doesn't support most lowercase shell syntax.
5. Attempt to break out using a shell trick. → Type $0 at the >> prompt and hit enter. → This returns you to a normal shell, now running as bandit33 due to the SUID permissions on uppershell.
6. Confirm your current user. → Run whoami. → It will output: bandit33, confirming you now have access as the next level.
7. Read the password for the next level (bandit34). → Run cat /etc/bandit_pass/bandit33 → This will display the password: t
8. Done! Save the password and move on to the next level.

￼


Bandit Level 33 → Level 34
At this moment, level 34 does not exist yet.


￼


