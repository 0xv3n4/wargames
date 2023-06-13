<h1 align="center"> BANDIT </h1>


> This file contains the commands mentioned in the solutions. Main purpose of this game is gathering information about the level and performing requested ways for ensuring password of the next level. 
## ✨ What is Wargames 
<p align="center">
  The wargames are great way to begin security journey with gamified concepts offered by OverTheWire community mentioned down below.
  <br></br>
  You can find more https://overthewire.org/wargames/
  

> NOTE :
While you're challenging with those levels you should save your passwords already achieved by you in .txt file in your main device. You may need those passwords of previous levels . 

## 🚀 What is Bandit 
![Screenshot_7](https://github.com/boranakova/wargames/assets/56170942/49aa2eec-55b7-4eb3-9b96-59a23cbe70eb)
<br></br>
It designed by OverTheWire.org for complete beginners and newbies
<br></br>
It will teach the basics needed to be able to play other wargames

This game, like most other games, is organised in levels. You start at Level 0 and try to “beat” or “finish” it 

### 0-4 
In these levels you need to understand file , directory and folder concepts of Linux. 

```sh
cd , ls , file 
```

### 5-14
In these levels you're going to find specific requests given in the level. For example : Regular expressions , encoding&decoding (Base64 , rot13) 
```sh
find , grep , sort , base64
```
I solved <b>5-6</b> with this command ;
```sh
find * -size 1033c cat directory_path 
```

I solved  <b>6-7</b> with this command ;

```sh
find / -user bandit7 -group bandit6 -size 33c & ls-lrha
```
I solved <b>7-8</b> with this command ;
```sh
grep "millionth" data.txt 
```
I solved <b>13-14</b> with this command ;
```sh
ssh -i sshkey.private bandit14@localhost -p 2220 
```

I solved <b>16-17</b> with this command ;
```sh
nmap -sV localhost -p 31000-32000 
```
> NOTE :
I simply put <b>man</b> command to learn what I need for this situation. Then i decided to use <b>-sV</b> ( sV flag lets us do a service/version detection scan while listening these ports. ) using <b>-p</b> for scanning all ports given the range of between 31000-32000. The level wants us to find SSL response of any server. When I found the server I used <b>openssl s_client</b> command then retrieved the password for the next level.
```sh
openssl s_client -connect localhost:31790 
```


### 19-23
In these levels you're going to learn <b>setuid</b> and <b>cron</b> concepts of Linux 
> NOTE : I googled these concepts and learned deeply before solving the level.

I solved <b>20-21</b> with this command ;
```sh
echo -n 'GbKksEFF4yrVs6il55v6gwY5aVje5f0j' | nc -l -p 1234 & 
```
> NOTE : <b>&</b> let the process run in the background. While running this command. I execute the setuid binary in the homedirectory given by level. 
> And I entered the port I specified with <b>nc</b> ( <b>-l</b> flag listens of an incoming connection <b>-p</b> flag specifies a port ).
```sh
./suconnect 1234
```
### 24-26

I solved <b>24-25</b> with this command ;
> NOTE :
> This level wants us to use brute-force method for reaching next level. So I researched how to use <b>for-loop</b> in bash scripting. Then I created a bash file with for loop range between 0000..9999. After recording all these entries. I sorted the result file then found the correct one.
> 
```sh

#!/bin/bash

for i in {0000..9999}
do
        echo UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ $i >> possibilities.txt
done

cat possibilities.txt | nc localhost 30002 > result.txt
```
I named it bf_entries.sh then I executed the directory 

```sh
./bf_entries.sh 

```
```sh
sort result.txt
```
### 27-34
In these levels you're going to learn some of Git commands.

>NOTE:
> You'll have to clone the remote repository to directory of a current level. I used some of these commands

```sh
git clone ssh://bandit27-git@localhost/home/bandit27-git/repo 
```

>If you obtain the repo successfully , You're going to learn what you supposed to do in this task .
>I used 
```sh
git log 
```
>to find any previous commits.

```sh
git tag 
```
>to find any tags in repo

```sh
git add
```
>to adding the file I created.

```sh
git commit 
```
>to committing my changes.

```sh
git push 
```
>to uploading local repo to remote repo and validate(I gave you a hint this is related to 31-32 ;) ).



### FINAL

![Screenshot_5](https://github.com/boranakova/wargames/assets/56170942/458eee0b-aee1-4cd7-820f-10e2b64322d5)


## Author

👤 **Boran AKOVA**

- LinkedIn: [@BoranAkova](https://www.linkedin.com/in/boran-akova-328477171/)
- Github: [@boranakova](https://github.com/boranakova)


Copyright © 2023 [Boran Akova](https://github.com/boranakova).<br />
This project is [MIT] licensed.

