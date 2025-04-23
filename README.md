# OS-Linux-commands-Shell-scripting
Operating systems Lab exercise
# Linux commands-Shell scripting
Linux commands-Shell scripting

# AIM:
To practice Linux Commands and Shell Scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Execute the following commands

### Step 3:

Testing the commands for the desired output. 

# COMMANDS:
### Create the following files file1, file2 as follows:
cat > file1
```
chanchal singhvi
c.k. shukla
s.n. dasgupta
sumit chakrobarty
^d
```
cat > file2
```
anil aggarwal
barun sengupta
c.k. shukla
lalit chowdury
s.n. dasgupta
^d
```
### Display the content of the files
cat < file1
## OUTPUT
```
chanchal singhvi
c.k. shukla
s.n. dasgupta
sumit chakrobarty
```


cat < file2
## OUTPUT
```
anil aggarwal
barun sengupta
c.k. shukla
lalit chowdury
s.n. dasgupta
```

# Comparing Files
cmp file1 file2
## OUTPUT
```
file1 file2 differ: byte 1, line 1
```
comm file1 file2
 ## OUTPUT
 ```
 anil aggarwal
	barun sengupta
chanchal singhvi
		c.k. shukla
	lalit chowdury
		s.n. dasgupta
sumit chakrobarty
comm: file 1 is not in sorted order
^d
```

 
diff file1 file2
## OUTPUT
```
1c1,2
< chanchal singhvi
---
> anil aggarwal
> barun sengupta
2a4
> lalit chowdury
4,8d5
< sumit chakrobarty
< ^d
```


#Filters

### Create the following files file11, file22 as follows:

cat > file11
```
Hello world
This is my world
^d
```
cat > file22
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
^d
```


cut -c1-3 file11
## OUTPUT
```
Hel
Thi
```

cut -d "|" -f 1 file22
## OUTPUT
```
1001 
1002 
1003 
```


cut -d "|" -f 2 file22
## OUTPUT
```
Ram 
 tom 
 Joe 
```

cat < newfile 
```
Hello world
hello world
^d
````
cat > newfile 
Hello world
hello world
 
grep Hello newfile 
## OUTPUT
```
Hello world

```



grep hello newfile 
## OUTPUT
```
hello world

```




grep -v hello newfile 
## OUTPUT
```
Hello world

```


cat newfile | grep -i "hello"
## OUTPUT
```
Hello world
hello world

```




cat newfile | grep -i -c "hello"
## OUTPUT
```
2
```



grep -R ubuntu /etc
## OUTPUT



grep -w -n world newfile   
## OUTPUT
```
1:Hello world
2:hello world

```


cat < newfile 
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
^d
```

cat > newfile
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
^d
 ```
egrep -w 'Hello|hello' newfile 
## OUTPUT
```
Hello world
hello world

```



egrep -w '(H|h)ello' newfile 
## OUTPUT
![image](https://github.com/user-attachments/assets/30e0dd49-910d-43ba-b297-947a7440d448)





egrep -w '(H|h)ell[a-z]' newfile 
## OUTPUT
```
Hello world
hello world

```




egrep '(^hello)' newfile 
## OUTPUT
```
hello world

```



egrep '(world$)' newfile 
## OUTPUT
```
Hello world
hello world


```


egrep '(World$)' newfile 
## OUTPUT
```
Linux is best in this World



```

egrep '((W|w)orld$)' newfile 
## OUTPUT
`![image](https://github.com/user-attachments/assets/092dab05-1d97-4f43-bf08-d8b0e5507c7c)
``


```


egrep '[1-9]' newfile 
## OUTPUT
```
![image](https://github.com/user-attachments/assets/2bf4ccd3-a3f7-4fe6-ba2c-51cb61790e47)

```


egrep 'Linux.*world' newfile 
## OUTPUT
```
![image](https://github.com/user-attachments/assets/d6ec0a20-8ad6-4ac5-b453-bd2c9ab68b76)

```

egrep 'Linux.*World' newfile 
## OUTPUT
```
![image](https://github.com/user-attachments/assets/ed665f5b-83f4-43aa-9914-511da4d6f302)
```

egrep l{2} newfile
## OUTPUT
```
![image](https://github.com/user-attachments/assets/2ef71454-5d89-4e7e-bf98-6ed3cb15b8af)
```


egrep 's{1,2}' newfile
## OUTPUT 
```
![image](https://github.com/user-attachments/assets/1c9f8945-7002-406a-ad76-fa1dce04118b)
```

cat > file23
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR
^d
```


sed -n -e '3p' file23
## OUTPUT
```
![image](https://github.com/user-attachments/assets/c8e89eac-0811-4941-ba27-f622e6094b44)
```



sed -n -e '$p' file23
## OUTPUT
```
![image](https://github.com/user-attachments/assets/09468150-12d5-40d3-b3b6-c7e889b94e7f)
```



sed  -e 's/Ram/Sita/' file23
## OUTPUT
```
![image](https://github.com/user-attachments/assets/ddb8943e-2994-4e00-b245-7acafa0684a1)

```


sed  -e '2s/Ram/Sita/' file23
## OUTPUT
```
![image](https://github.com/user-attachments/assets/1ddb5557-4246-4bae-8869-d1b2356f6aa4)
```



sed  '/tom/s/5000/6000/' file23
## OUTPUT
```
![image](https://github.com/user-attachments/assets/bf350d24-8100-48a5-b169-a258c1aef2b1)
```


sed -n -e '1,5p' file23
## OUTPUT
```
![image](https://github.com/user-attachments/assets/5d2519c1-5880-4ab1-b8fc-bf2e4d65421b)
```



sed -n -e '2,/Joe/p' file23
## OUTPUT

```
![image](https://github.com/user-attachments/assets/6e892265-5bd3-4389-ae97-2b9ef192ddac)

```





sed -n -e '/tom/,/Joe/p' file23
## OUTPUT
```
![image](https://github.com/user-attachments/assets/21adee9f-08b0-4a4a-9268-0ec408327073)

```


seq 10 
## OUTPUT
```
![image](https://github.com/user-attachments/assets/dd3a6f39-cea1-401e-bce3-a9ded55d1929)

```


seq 10 | sed -n '4,6p'
## OUTPUT
```
![image](https://github.com/user-attachments/assets/9c506667-b038-4828-a923-4de0ffc950c5)

```



seq 10 | sed -n '2,~4p'
## OUTPUT
```
![image](https://github.com/user-attachments/assets/827c3181-3bfb-4c45-8837-d8ab7fbedde0)

```


seq 3 | sed '2a hello'
## OUTPUT
```
![image](https://github.com/user-attachments/assets/2de12e3a-ef9d-4c7e-ba5b-24b806dbb225)

```



seq 2 | sed '2i hello'
## OUTPUT
```
![image](https://github.com/user-attachments/assets/d381034a-8a19-4d35-af9a-37a16f17c684)

```

seq 10 | sed '2,9c hello'
## OUTPUT
```
![image](https://github.com/user-attachments/assets/104b03be-9692-4e4f-8fbf-ca58626e09c1)

```

sed -n '2,4{s/^/$/;p}' file23
## OUTPUT
```
![image](https://github.com/user-attachments/assets/03206e04-e91d-4497-9ee7-8769e19bf042)

```


sed -n '2,4{s/$/*/;p}' file23
## OUTPUT
```
![image](https://github.com/user-attachments/assets/e26a288b-fa9c-4ae7-9e0c-b176bb3d86bb)

```


#Sorting File content
cat > file21
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
``` 
sort file21
## OUTPUT
```
![image](https://github.com/user-attachments/assets/0f8b3009-9300-40f6-adf2-7e99a62e2ce7)

```

cat > file22
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
``` 
uniq file22
## OUTPUT
```
![image](https://github.com/user-attachments/assets/eef3b162-b211-41ae-9257-c980ae2845e5)

```


#Using tr command

cat file23 | tr [:lower:] [:upper:]
 ## OUTPUT
```
![image](https://github.com/user-attachments/assets/5a3b86e0-1f23-4d6c-b8ec-2cca55155b39)

```
cat < urllist.txt
```
www. yahoo. com
www. google. com
www. mrcet.... com
^d
 ```
cat > urllist.txt
```
www. yahoo. com
www. google. com
www. mrcet.... com
 ```
cat urllist.txt | tr -d ' '
 ## OUTPUT
```
![image](https://github.com/user-attachments/assets/8082705d-0d29-44ff-a3c7-2499bd15d084)

```

 
cat urllist.txt | tr -d ' ' | tr -s '.'
## OUTPUT
```
![image](https://github.com/user-attachments/assets/aa4199d8-8855-44f6-a225-c47a8ee24d68)

```


#Backup commands
tar -cvf backup.tar *
## OUTPUT
```
![image](https://github.com/user-attachments/assets/4ee9e14b-a80c-4bce-916b-0fdb3a8df352)

```

mkdir backupdir
 
mv backup.tar backupdir
 
tar -tvf backup.tar
## OUTPUT
```
![image](https://github.com/user-attachments/assets/c552e161-8e8c-4da1-b9c4-91122bf8c110)

```

tar -xvf backup.tar
## OUTPUT
```
![image](https://github.com/user-attachments/assets/82f697f4-ad3d-45df-9262-46f1a7092b6a)

```
gzip backup.tar

ls .gz
## OUTPUT
 
gunzip backup.tar.gz
## OUTPUT

 
# Shell Script
```
echo '#!/bin/sh' > my-script.sh
echo 'echo Hello World‘; exit 0 >> my-script.sh
```
```
![image](https://github.com/user-attachments/assets/790bd1aa-46ab-45ee-8f7c-62a7624334f6)

```
chmod 755 my-script.sh
./my-script.sh
## OUTPUT
```
![image](https://github.com/user-attachments/assets/ffa76409-01df-45b2-b181-a713d45ae02d)

```

 
cat << stop > herecheck.txt
```
hello in this world
i cant stop
for this non stop movement
stop
```

cat herecheck.txt
## OUTPUT
```
![image](https://github.com/user-attachments/assets/3f51e102-ee52-4fd4-9f38-3387ccc9d8d8)

```

cat < scriptest.sh 
```bash
\#!/bin/sh
echo “File name is $0 ”
echo "File name is " `basename $0`
echo “First arg. is ” $1
echo “Second arg. is ” $2
echo “Third arg. is ” $3
echo “Fourth arg. is ” $4
echo 'The $@ is ' $@
echo 'The $\# is ' $1#
echo 'The $$ is ' $$
ps
^d
 ```

cat scriptest.sh 
```bash
\#!/bin/sh
echo “File name is $0 ”
echo "File name is " `basename $0`
echo “First arg. is ” $1
echo “Second arg. is ” $2
echo “Third arg. is ” $3
echo “Fourth arg. is ” $4
echo 'The $@ is ' $@
echo 'The $\# is ' $\#
echo 'The $$ is ' $$
ps
```
 
chmod 777 scriptest.sh
 
./scriptest.sh 1 2 3

## OUTPUT
```

```
 
ls file1
## OUTPUT


echo $?
## OUTPUT 
```
![image](https://github.com/user-attachments/assets/188401e7-6283-4d38-9dae-9230a16f15ad)

```
./one
bash: ./one: Permission denied
 
echo $?
## OUTPUT 
```
![image](https://github.com/user-attachments/assets/88c384bf-fcc5-41e7-a6fc-45a13e81599f)

```
abcd
 
echo $?
 ## OUTPUT
```
![image](https://github.com/user-attachments/assets/24a4a6b8-3e9b-4799-afb1-8bd482daba0a)

```

 
# mis-using string comparisons

cat < strcomp.sh 
```bash
\#!/bin/bash
val1=baseball
val2=hockey
if [ $val1 \> $val2 ]
then
echo "$val1 is greater than $val2"
else
echo "$val1 is less than $val2"
fi
^d
```

cat strcomp.sh 
```bash
\#!/bin/bash
val1=baseball
val2=hockey
if [ $val1 \> $val2 ]
then
echo "$val1 is greater than $val2"
else
echo "$val1 is less than $val2"
fi
```
##OUTPUT
```
![image](https://github.com/user-attachments/assets/a6f5e967-09a3-43d8-9d61-9b0acc1e9cbc)


```


chmod 755 strcomp.sh
 
./strcomp.sh 
## OUTPUT
```
![image](https://github.com/user-attachments/assets/436f0be7-4c9e-4dae-bf6b-8b5466026155)

```

# check file ownership
cat < psswdperm.sh 
```bash
\#!/bin/bash
if [ -O /etc/passwd ]
then
echo “You are the owner of the /etc/passwd file”
else
echo “Sorry, you are not the owner of the /etc/passwd file”
fi
^d
```

cat psswdperm.sh 
```bash
/#!/bin/bash
if [ -O /etc/passwd ]
then
echo “You are the owner of the /etc/passwd file”
else
echo “Sorry, you are not the owner of the /etc/passwd file”
fi
 ```
./psswdperm.sh
## OUTPUT
```
![image](https://github.com/user-attachments/assets/cf7d2839-03cf-4417-8375-82380cf64c28)

```

# check if with file location
cat>ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
^d
```
cat ifnested.sh 
```
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
```

./ifnested.sh 
## OUTPUT

![Screenshot 2024-03-01 232449](https://github.com/RAGULRAAJAN/OS-Linux-commands-Shell-script/assets/147473144/be26ce19-6dd8-4160-904a-55004860593c)


# using numeric test comparisons
cat > iftest.sh 
```bash
\#!/bin/bash
val1=10
val2=11
if [ $val1 -gt 5 ]
then
echo “The test value $val1 is greater than 5”
fi
if [ $val1 -eq $val2 ]
then
echo “The values are equal”
else
echo “The values are different”
fi
^d
```


cat iftest.sh 
```bash
\#!/bin/bash
val1=10
val2=11
if [ $val1 -gt 5 ]
then
echo “The test value $val1 is greater than 5”
fi
if [ $val1 -eq $val2 ]
then
echo “The values are equal”
else
echo “The values are different”
fi
```

$ chmod 755 iftest.sh
 
$ ./iftest.sh 
##OUTPUT
![Screenshot 2024-03-01 232502](https://github.com/RAGULRAAJAN/OS-Linux-commands-Shell-script/assets/147473144/bffb9936-3585-48c3-a587-911a8e628d37)

# check if a file
cat > ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
^d
```

cat ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
```

$ chmod 755 ifnested.sh
 
$ ./ifnested.sh 
##OUTPUT
![Screenshot 2024-03-01 232939](https://github.com/RAGULRAAJAN/OS-Linux-commands-Shell-script/assets/147473144/bd2057f0-f0fd-49fa-bd6e-f30e6d48c62b)

# looking for a possible value using elif
cat elifcheck.sh 
```bash
\#!/bin/bash
if [ $USER = Ram ]
then
echo "Welcome $USER"
echo "Please enjoy your visit"
elif [ $USER = Rahim ]
then
echo "Welcome $USER"
echo "Please enjoy your visit"
elif [ $USER = Robert ]
then
echo "Special testing account"
elif [ $USER = gganesh ]
then
echo "$USER, Do not forget to logout when you're done"
else
echo "Sorry, you are not allowed here"
fi
```

$ chmod 755 elifcheck.sh
 
$ ./elifcheck.sh 
## OUTPUT
![Screenshot 2024-03-01 232953](https://github.com/RAGULRAAJAN/OS-Linux-commands-Shell-script/assets/147473144/7ebd4cf9-99c6-4081-a7bc-bfaed03a2e17)


# testing compound comparisons
cat> ifcompound.sh 
```bash
\#!/bin/bash
if [ -d $HOME ] && [ -w $HOME ]
then
echo "The file exists and you can write to it"
else
echo "I cannot write to the file"
fi
```
$ chmod 755 ifcompound.sh
$ ./ifcompound.sh 
## OUTPUT
![Screenshot 2024-03-01 233023](https://github.com/RAGULRAAJAN/OS-Linux-commands-Shell-script/assets/147473144/584ef834-c04a-4afd-b92e-318deba3d677)

# using the case command
cat >casecheck.sh 
```bash
case $USER in
Ram | Robert)
echo "Welcome, $USER"
echo "Please enjoy your visit";;
Rahim)
echo "Special testing account";;
gganesh)
echo "$USER, Do not forget to log off when you're done";;
*)
echo "Sorry, you are not allowed here";;
esac
```
$ chmod 755 casecheck.sh 
 
$ ./casecheck.sh 
 
cat > whiletest
```bash
#!/bin/bash
#while command test
var1=10
while [ $var1 -gt 0 ]
do
echo $var1
var1=$[ $var1 - 1 ]
done
```
$ chmod 755 whiletest.sh
 
$ ./whiletest.sh
 
 ![Screenshot 2024-03-01 233107](https://github.com/RAGULRAAJAN/OS-Linux-commands-Shell-script/assets/147473144/81d3e9d1-aef2-4da1-889e-ace086eb57ee)

cat untiltest.sh 
```bash
\#using the until command
var1=100
until [ $var1 -eq 0 ]
do
echo $var1
var1=$[ $var1 - 25 ]
done
``` 
$ chmod 755 untiltest.sh
 
 ![Screenshot 2024-03-01 233203](https://github.com/RAGULRAAJAN/OS-Linux-commands-Shell-script/assets/147473144/7f3f4232-c556-487d-845d-36ad26360a71)

 
cat forin1.sh 
```bash
\#!/bin/bash
\#basic for command
for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo The next state is $test
done
 ```
 
$ chmod 755 forin1.sh
 ![Screenshot 2024-03-01 233216](https://github.com/RAGULRAAJAN/OS-Linux-commands-Shell-script/assets/147473144/00883fb1-6489-4163-99fc-b750d8b77ef1)

 
cat forin2.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don't know if this'll work
do
echo “word:$test”
done
 ```
 
$ chmod 755 forin2.sh
 
cat forin2.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don't know if this'll work
do
echo “word:$test”
done
```
$ chmod 755 forin2.sh
 
$ ./forin2.sh 
 ![Screenshot 2024-03-01 233228](https://github.com/RAGULRAAJAN/OS-Linux-commands-Shell-script/assets/147473144/848dac7e-3175-4701-bf4f-851386219d97)

cat forin3.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don\'t know if "this'll" work
do
echo "word:$test"
done
```
$ ./forin3.sh 
 ![Screenshot 2024-03-01 233242](https://github.com/RAGULRAAJAN/OS-Linux-commands-Shell-script/assets/147473144/29b13d20-62ba-4b80-8206-c4222a39156f)

cat forin1.sh 
```bash
#!/bin/bash
# basic for command
for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo The next state is $test
done
```
$ chmod 755 forin1.sh

## OUTPUT
![Screenshot 2024-03-01 233216](https://github.com/RAGULRAAJAN/OS-Linux-commands-Shell-script/assets/147473144/ca9c03f0-7d68-4586-9a4d-74bc315f2476)



cat forinfile.sh 
```bash
#!/bin/bash
# reading values from a file
file="cities"
for state in `cat $file`
do
echo "Visit beautiful $file“
done
```
$ chmod 777 forinfile.sh
$ cat cities
Hyderabad
Alampur
Basara
Warangal
Adilabad
Bhadrachalam
Khammam

## OUTPUT
![Screenshot 2024-03-01 233257](https://github.com/RAGULRAAJAN/OS-Linux-commands-Shell-script/assets/147473144/b87b1e50-b514-47b1-a331-cb30ed9cb224)



cat forctype.sh 
```bash
#!/bin/bash
# testing the C-style for loop
for (( i=1; i <= 5; i++ ))
do
echo "The value of i is $i"
done
````
$ chmod 755 forctype.sh
$ ./forctype.sh 
## OUTPUT
![Screenshot 2024-03-01 233312](https://github.com/RAGULRAAJAN/OS-Linux-commands-Shell-script/assets/147473144/4f0c3e69-7c5a-4776-887e-2fcabb80c203)

cat forctype1.sh 
```bash
#!/bin/bash
# multiple variables
for (( a=1, b=5; a <= 5; a++, b-- ))
do
echo "$a - $b"
done
```
$ chmod 755 forctype.sh
$ ./forctype1.sh 
## OUTPUT
![Screenshot 2024-03-01 233326](https://github.com/RAGULRAAJAN/OS-Linux-commands-Shell-script/assets/147473144/b5770276-5696-4194-ac63-87877583c233)

cat fornested1.sh 
```bash
#!/bin/bash
# nesting for loops
for (( a = 1; a <= 3; a++ ))
do
echo "Starting loop $a:"
for (( b = 1; b <= 3; b++ ))
do
echo " Inside loop: $b"
done
done
```
$ chmod 755 fornested1.sh
 
$ ./fornested1.sh 
 ## OUTPUT
![Screenshot 2024-03-01 233340](https://github.com/RAGULRAAJAN/OS-Linux-commands-Shell-script/assets/147473144/8fe0ee36-6320-41e3-8fa6-0712430dcfbd)

 
cat forbreak.sh 
```bash
#!/bin/bash
# breaking out of a for loop
for var1 in 1 2 3 4 5
do
if [ $var1 -eq 3 ]
then
break
fi
echo "Iteration number: $var1"
done
echo "The for loop is completed“
```
## OUTPUT
![Screenshot 2024-03-01 233405](https://github.com/RAGULRAAJAN/OS-Linux-commands-Shell-script/assets/147473144/e936aa33-eb93-4f40-a02a-c6a049b62b56)

$ chmod 755 forbreak.sh
 
$ ./forbreak.sh 
 ![Screenshot 2024-03-01 233405](https://github.com/RAGULRAAJAN/OS-Linux-commands-Shell-script/assets/147473144/eb338c35-92de-41f7-b849-38e992330a68)

cat forbreak.sh 
```bash
![Screenshot 2024-03-01 233435](https://github.com/RAGULRAAJAN/OS-Linux-commands-Shell-script/assets/147473144/c97aa5a3-8d90-4017-96a3-824b17995ef4)

#!/bin/bash
# breaking out of a for loop
for var1 in 1 2 3 4 5
do
if [ $var1 -eq 3 ]
then
continue
fi
echo "Iteration number: $var1"
done
echo "The for loop is completed“
```

 
$ chmod 755 forcontinue.sh
 
$ ./forcontinue.sh 
## OUTPUT
 
cat exread.sh 
```bash
#!/bin/bash
# testing the read command
echo -n "Enter your name: "
read name
echo "Hello $name, welcome to my program. "
 ```
 
$ chmod 755 exread.sh 
 
$ ./exread.sh 
## OUTPUT
![Screenshot 2024-03-01 233448](https://github.com/RAGULRAAJAN/OS-Linux-commands-Shell-script/assets/147473144/c356b6f6-e74a-42c1-9f9f-6ed4474fcbd2)


 cat exread1.sh
```bash
#!/bin/bash
# testing the read command
read -p "Enter your name: " name
echo "Hello $name, welcome to my program. “
``` 
$ chmod 755 exread1.sh 

## OUTPUT

![Screenshot 2024-03-01 233501](https://github.com/RAGULRAAJAN/OS-Linux-commands-Shell-script/assets/147473144/6df3bd1f-1c31-40de-a208-c222cd15bbf9)


$ ./exread1.sh 
 
cat funcex.sh
```bash
#!/bin/bash
# trying to access script parameters inside a function
function func {
echo $[ $1 * $2 ]
}
if [ $# -eq 2 ]
then
value=`func $1 $2`
echo "The result is $value"
else
echo "Usage: badtest1 a b"
fi
```
## OUTPUT
 ./funcex.sh 
![Screenshot 2024-03-01 233511](https://github.com/RAGULRAAJAN/OS-Linux-commands-Shell-script/assets/147473144/a757a821-e021-4a27-8d50-f6574565ad67)

 
 ./funcex.sh 1 2

 
cat argshift.sh
```bash
#!/bin/bash 
 while (( "$#" )); do 
  echo $1 
  shift 
done
```
$ chmod 777 argshift.sh

## OUTPUT
$ ./argshift.sh 1 2 3
 ![Screenshot 2024-03-01 233522](https://github.com/RAGULRAAJAN/OS-Linux-commands-Shell-script/assets/147473144/405693cf-99d3-43a1-be48-e550763260de)

 cat argshift1.sh
```bash
 #/bin/bash 
 # store arguments in a special array 
args=("$@") 
# get number of elements 
ELEMENTS=${#args[@]} 
 # echo each element in array  
# for loop 
for (( i=0;i<$ELEMENTS;i++)); do 
    echo ${args[${i}]} 
done
```
$ chmod 777 argshift.sh
## OUTPUT
![Screenshot 2024-03-01 233532](https://github.com/RAGULRAAJAN/OS-Linux-commands-Shell-script/assets/147473144/74e4b687-6cc5-429b-b993-ad7db8f077f6)


$ ./argshift.sh 1 2 3
 
cat argshift.sh
```bash
#!/bin/bash 
set -x 
while (( "$#" )); do 
  echo $1 
  shift 
done
set +x
```
## OUTPUT
 ./argshift.sh 1 2 3
 
 
cat > nc.awk
```bash
BEGIN{}
{
print len=length($0),"\t",$0 
wordcount+=NF
chrcnt+=len
}
END {
print "total characters",chrcnt 
print "Number of Lines are",NR
print "No of Words count:",wordcount
}
 ```
cat>data.dat
```bash
bcdfghj
abcdfghj
bcdfghj
ebcdfghj
bcdfghj
ibcdfghj
bcdfghj
obcdfghj
bcdfghj
ubcdfghj
```
awk -f nc.awk data.dat
## OUTPUT 
 ![Screenshot 2024-03-01 233546](https://github.com/RAGULRAAJAN/OS-Linux-commands-Shell-script/assets/147473144/b13086bf-891d-40e8-953e-eb519fb98979)

cat > palindrome.sh
```bash
#num=545
echo "Enter the number"
read num
s=0
rev=""
temp=$num
while [ $num -gt 0 ]
do
	# Get Remainder
	s=$(( $num % 10 ))
	# Get next digit
	num=$(( $num / 10 ))
	# Store previous number and
	# current digit in reverse
	rev=$( echo ${rev}${s} )
done
if [ $temp -eq $rev ];
then
	echo "Number is palindrome"
else
	echo "Number is NOT palindrome"
fi
```
## OUTPUT 

![Screenshot 2024-03-01 233618](https://github.com/RAGULRAAJAN/OS-Linux-commands-Shell-script/assets/147473144/27199787-e397-4b51-b87d-e4736a1615fa)

# RESULT:
The Commands are executed successfully.
