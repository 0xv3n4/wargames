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
> NOTE : First of all I used Burp to find any changes in website of the current level. Everything seemed normal at first. But then I noticed the Cookie section has a value named <b>loggedin=0</b>. So as a curious fellow i wanted to change it from 0 to 1.
![4-5 1](https://github.com/boranakova/wargames/assets/56170942/cc4f97f6-d63c-438d-9395-ae657fa25c95)
> NOTE : Well... c: 
![4-5 2](https://github.com/boranakova/wargames/assets/56170942/832c0c0d-c261-4c78-a4e7-dfee52709c70)

#### What are Cookies ? 
Cookies are simply wants to know you or your device. That are used to identify your computer as you use a computer network.
Specific cookies known as HTTP cookies are used to identify specific users and improve your web browsing experience. They are built like tracking and saving information about each user's session. 

### 5-6
![5-6 1](https://github.com/boranakova/wargames/assets/56170942/f3373458-dfab-40c0-902c-114a9540fbee)

This level contains a <b>source code</b> written in <b>PHP</b> !

> NOTE : To acquiring a password for the next level you have to analyse source code given by the website. When I examine <b>index-source.html</b> 
> I found an embedded PHP code in html file. When I understand the source code. I tried to access the "includes/secret.inc" file via URL.
>  But I got  <b>Autharization has failed error </b> from website. So I decide to connect with web server via FTP. Because I had the credentials of current level So why not? 
>  
```sh
ftp http://natas6.natas.labs.overthewire.org/includes/secret.inc 
cat secret.inc
```
![5-6 2](https://github.com/boranakova/wargames/assets/56170942/2e248202-ab79-418f-a063-92b429c033f7)
> NOTE : Then I put the secret key in textfield and submitting the query. 

![5-6 3](https://github.com/boranakova/wargames/assets/56170942/77d1ed75-6629-4561-aab6-a86f1c5804bc)
<br></br>
![5-6 4](https://github.com/boranakova/wargames/assets/56170942/b488d714-f49e-42bd-90c7-b4f5a1b7fc40)

### 6-7
This level gives hint about the directory stored password for the next level.
<br></br>
![6-7 1](https://github.com/boranakova/wargames/assets/56170942/dd6220c7-af7c-4ed5-8557-f697f238d891)

>NOTE : The website has <b>Home</b> and <b>About</b> page and index url of a website directs these requests with <b>page</b> parameter.
>So I formatting the URL like below and I got the password for the next level. 

![6-7 2](https://github.com/boranakova/wargames/assets/56170942/7e027b5e-5e7e-4ad0-b33a-fdabf6d14bd6)

### 7-8 
This level contains a <b>source code</b> written in <b>PHP</b> !
>NOTE : When I examine the source code I saw the function called encodeSecret(). It is simply used base64 encoding. Then the output is reversed. and finally the output is converted binary to hexadecimal. We already have the encoded secret key. All we have to do is resolve all the steps in reverse. This means, we have to converting hexadecimal to binary then output will be reversed and finally decoding base64 will give us the secret key.  


![7-8 1](https://github.com/boranakova/wargames/assets/56170942/d8f2d45c-0286-4eea-a99f-ee35ea601a04)

Normally the specific websites like [CyberChef](https://gchq.github.io/CyberChef/) already solve this methods automatically. But I wanted to do this level manually for hands-on experience with commands of Linux.

```sh
touch myencoded.txt
nano myencoded.txt
cat myencoded.txt
```
![7-8 2](https://github.com/boranakova/wargames/assets/56170942/2e6c4c6e-aa18-40e0-969f-10556c1e4d43)

```sh
xxd -r -p myencoded.txt myencoded.bin 
```
>NOTE : <b>-r</b> flag is reverting hexdump into binary. <b>-p</b> flag is an output with plain style.

![7-8 3](https://github.com/boranakova/wargames/assets/56170942/7bfafde5-befb-4de7-9691-0d3293fe6889)

>NOTE : I reversed my output with <b>rev</b> command.
```sh
cat myencoded.bin | rev
```
>NOTE : I decoded via base64 with my output.
```sh
echo b3ViV1lmMmtCcQ== | base64 --decode
```
![7-8 4](https://github.com/boranakova/wargames/assets/56170942/e9bced2a-0398-4ee4-94de-6d86c33992da)

>NOTE : I put the key on the input.

![7-8 5](https://github.com/boranakova/wargames/assets/56170942/a66ef34e-4948-4c28-85ca-aa9c10e14a9e)


### 8-9
This level contains a <b>source code</b> written in <b>PHP</b> !
<br></br>
![8-9 1](https://github.com/boranakova/wargames/assets/56170942/61ba50b2-d82b-4a57-9188-773a2bf921b3)

> NOTE : <b>passthru</b> executes a command so If I inject the method with <b>|</b> , <b>&</b> or <b>;</b>. It will give results of any requests.

![8-9 2](https://github.com/boranakova/wargames/assets/56170942/9e780dc3-9a4f-48e6-bcce-5ecd7910ab5e)
> Like that ! Let me try something different... What if I....
<br></br>
![8-9 3](https://github.com/boranakova/wargames/assets/56170942/4da41322-0e24-413c-a1af-6dd7e06db6b5)

### 9-10

This level contains a <b>source code</b> written in <b>PHP</b> !
Similar to 8-9 but updated with some security measures. So <b>|</b> , <b>&</b> or <b>;</b> are not gonna work !

![9-10 1](https://github.com/boranakova/wargames/assets/56170942/cdd352fe-2941-4110-b347-c1b4884e2614)

> NOTE : I did some research and found a command name <b>curl</b>. It enables data exchange between a device and server. <b>passthru</b> still be able to execute a command. So I'm going to inject the command again.

![9-10 2](https://github.com/boranakova/wargames/assets/56170942/ee090398-6587-4fb9-ae1e-e74cb50a4414)



### 10-11

This level contains a <b>massive</b> <b>source code</b> written in <b>PHP</b> !

![10-11 1](https://github.com/boranakova/wargames/assets/56170942/557ef647-ab32-47cf-ad4f-36e6baaaabc4)


> NOTE : I did lot of research for understanding XOR encryption. I tried to understand the code below.

```sh
<?
$defaultdata = array( "showpassword"=>"no", "bgcolor"=>"#ffffff");

function xor_encrypt($in) {
    $key = '<censored>';
    $text = $in;
    $outText = '';

    // Iterate through each character
    for($i=0;$i<strlen($text);$i++) {
    $outText .= $text[$i] ^ $key[$i % strlen($key)];
    }
    return $outText;
}

function loadData($def) {
    global $_COOKIE;
    $mydata = $def;
    if(array_key_exists("data", $_COOKIE)) {
    $tempdata = json_decode(xor_encrypt(base64_decode($_COOKIE["data"])), true);
    if(is_array($tempdata) && array_key_exists("showpassword", $tempdata) && array_key_exists("bgcolor", $tempdata)) {
        if (preg_match('/^#(?:[a-f\d]{6})$/i', $tempdata['bgcolor'])) {
        $mydata['showpassword'] = $tempdata['showpassword'];
        $mydata['bgcolor'] = $tempdata['bgcolor'];
        }
    }
    }
    return $mydata;
}
function saveData($d) {
    setcookie("data", base64_encode(xor_encrypt(json_encode($d))));
}
$data = loadData($defaultdata);
if(array_key_exists("bgcolor",$_REQUEST)) {
    if (preg_match('/^#(?:[a-f\d]{6})$/i', $_REQUEST['bgcolor'])) {
        $data['bgcolor'] = $_REQUEST['bgcolor'];
    }
}
saveData($data);
?>
```
> NOTE : When the parameter is sent to the website , Website creates cookie named <b>data</b> This cookie was loading with Base64Decode > XOR  order and saving with XOR > Base64Encode. So we need to do reversely for finding the key. Firstly I executed a code in online PHP editor for formatting to JSON. 

![10-11 2](https://github.com/boranakova/wargames/assets/56170942/090775ef-198b-4e0c-9b97-28e063434005)

> NOTE : Then I obtained the cookie named data from Burp. I Copied and pasted to [CyberChef](https://gchq.github.io/CyberChef/) as an input. Executing the steps generated the key. 

![10-11 3](https://github.com/boranakova/wargames/assets/56170942/134b2d5b-2d6f-40bf-9bb9-e0cedd256303)


> NOTE : The key can be inputted in XOR. Afterwards Base64Encode process will start.


![10-11 4](https://github.com/boranakova/wargames/assets/56170942/0fe2ef9a-1d54-443e-a191-c80bb90ba1f7)

> NOTE : If we change <b>showpassword</b> variable from no to yes with XOR encryption. Then it will encode to Base64 and give it cookie data stored the password. Like <b>3-4</b> or <b>4-5</b> , We need to change the cookie variable named data to new one. 

If these steps done right. You will see the website has been updated with password for the next level.
![10-11 5](https://github.com/boranakova/wargames/assets/56170942/8c721fc1-7905-40da-a0e6-3407bb302aca)







### FINAL



## Author

👤 **Boran AKOVA**

- LinkedIn: [@BoranAkova](https://www.linkedin.com/in/boran-akova-328477171/)
- Github: [@boranakova](https://github.com/boranakova)


Copyright © 2023 [Boran Akova](https://github.com/boranakova).<br />
This project is [MIT] licensed.
