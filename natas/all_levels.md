<h1 align="center"> NATAS </h1>

![Angron](https://github.com/boranakova/wargames/assets/56170942/9a702436-9e7b-4a19-897a-fd0be0740081)


> This file contains the commands mentioned in the solutions. Main purpose of this game is gathering information about the level and performing requested ways for ensuring password of the next level. 
## ✨ What is Wargames 
<p align="center">
  The wargames are great way to begin security journey with gamified concepts offered by OverTheWire community mentioned down below.
  <br></br>
  You can find more https://overthewire.org/wargames/
  

> NOTE :
While you're challenging with those levels you should save your passwords already achieved by you in .txt file in your main device. You may need those passwords of previous levels . 

## 🚀 What is NATAS 
![natasss](https://github.com/boranakova/wargames/assets/56170942/80899ced-84cc-4a69-994d-e446831d3f79)

<br></br>

The community of OverTheWire.org aimed to teach basics of serverside web-security. 
<br></br>
Each level of natas consists of its own website located at http://natasX.natas.labs.overthewire.org, where X is the level number. 
There is no SSH login. To access a level, enter the username for that level (e.g. natas0 for level 0) and its password.

### 0 
In this level you should just view page source and find the comment. 
                 
![0](https://github.com/boranakova/wargames/assets/56170942/8a585dc5-a146-4e52-be60-f267937b928d)
                 
### 0-1 
In this level you should find a way to open page source and find the comment.
                 
![0-1](https://github.com/boranakova/wargames/assets/56170942/49df9753-95fb-4dfd-b00e-9b346ea1df50)
             
                 
### 1-2            
![1-2 1](https://github.com/boranakova/wargames/assets/56170942/cf6b05ba-5668-4145-9e88-09259897c07a)
> NOTE :
                 When you inspect the page of NATAS2 , you will find a directory in <b>'img'</b> tag.
                 I simply deleted the file path. Afterwards I kept the directory named <b>files</b>
                 <br></br>
![1-2 2](https://github.com/boranakova/wargames/assets/56170942/5e652de7-2600-4bd7-8f96-19118da5ebd9)
> NOTE : 
> Clicking the file icon will direct to the screen shown below.

![1-2 3](https://github.com/boranakova/wargames/assets/56170942/51245804-e4e6-47f3-8f77-d7ae9d49e03f)
> NOTE : 
> Then you will find a hidden file named <b>users.txt</b>. That will give the password for the next level.


![1-2 4](https://github.com/boranakova/wargames/assets/56170942/780f262e-2b5e-4cb8-840b-d764da0293c4)
                 
             
                 
                 

### 2-3
In this level, you need to have knowledge for understanding the hint given by website.
<br></br>
![2-3 1](https://github.com/boranakova/wargames/assets/56170942/fb56bb09-1845-4a91-b7be-b1c50d836800)
> NOTE : If you said "What the heck this ?!" like me. Well I googled it and found a file named robots.txt. 

#### WHAT IS robots.txt 
Search engine bots examine this file before visiting our website. Then the commands of this file starts to scan our web pages.
When the hint tells us <b> " Not even Google will find it this time " </b> it means not even the bots of Google can track you or examine you.

> NOTE : So i simply put the <b>/robots.txt</b> in my URL like below. Then i found hidden path named <b>s3cr3t</b>
 
![2-3 2](https://github.com/boranakova/wargames/assets/56170942/e45c6792-7482-4e52-b692-c6cebf18c9b0)

> NOTE : I put the hidden path to the URL like below. I found a .txt file named <b>users.txt </b> When I opened the file on my browser , the password for 
> the next level has appeared. 

![2-3 3](https://github.com/boranakova/wargames/assets/56170942/926cd26a-f8f0-4f22-9baf-5dab36b6940f)
<br></br>
![2-3 4](https://github.com/boranakova/wargames/assets/56170942/4d8c1624-cd58-4617-a17d-a0be497ecbb7)

### 3-4
![3-4 1](https://github.com/boranakova/wargames/assets/56170942/9da13ecc-1382-4149-be70-a546a5f8d55d)

In this level , you have to use a tool for examine parameters.Any 
web application analysis tool can help but the most used tool is <b>Burp Suite</b>. So I researched to install and setup the tool in Kali.

> NOTE : You need an also have specify Proxy setting of Firefox for using Burp with the website simultaneously. 
> You should go Settings>Network-Settings>Connection-Settings. 
> Open Manual proxy configuration and type <b> 127.0.0.1 Port : 8080 </b>. Press <b>OK</b> <br></br> You ready to go. 

![3-4 2](https://github.com/boranakova/wargames/assets/56170942/87c7f43a-838b-43d5-a88b-5a31a7e18b15)

> NOTE : I did some research and i learned website visitation called <b>Referring</b>. The NATAS4 wants us to visit here from NATAS5.
> I haven't got password of NATAS5 yet. So I have to pretend to be NATAS5 credentials and arrive from there.
> By that I used Burp to manipulating my referer-header value. I simply changed the number <b>4</b> to <b>5</b> of referer value.                           

![3-4 3](https://github.com/boranakova/wargames/assets/56170942/4466d047-8835-44d0-bc14-cf1dae0b525e)

> NOTE : I forwarded my request in Burp. When the browser triggered i got the password for the next level has shown like below.

![3-4 4](https://github.com/boranakova/wargames/assets/56170942/d5f71a10-3432-4dd7-907c-7dabf62c50ef)

### 4-5




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
