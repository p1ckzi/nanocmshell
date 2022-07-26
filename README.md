# nanocmshell ⭐
a simple script that exploits an authenticated file upload/remote code execution vulnerability in NanoCMS v0.4.  

## the exploit ❗
https://github.com/kalyan02/NanoCMS has not been maintained in a long time and suffers from a a number of vulnerabilities including authenticated file upload/remote code execution which this script exploits.  
More information here: https://github.com/ishell/Exploits-Archives/blob/master/2009-exploits/0904-exploits/nanocms-multi.txt  
NanoCMS saves pages both new and edited, as .php files by default, allowing an authenticated attacker to upload executable code.  
this script uploads a webshell.

## prerequisites ✔
* python3
* python3 requests module
* python3 beautifulsoup4 module
```
sudo apt install python3
sudo apt install python3-pip
pip3 install beautifulsoup4
pip3 install requests
```

## usage ℹ
use `./nanocmshell` or `python3 nanocmshell` with `-h` or `--help` for help menu:
```
usage: nanocmshell [-h] [-u USER] [-p PASSWD] [-e] [-a] [-n] address file

../nanocmshellv2.py exploits authenticated file upload
and remote code execution in NanoCMS.

positional arguments:
  address               schema/ip/hostname, port, sub-directories to the vulnerable NanoCMS
                        server
  file                  php file to upload

options:
  -h, --help            show this help message and exit
  -u USER, --user USER  username
  -p PASSWD, --passwd PASSWD
                        password
  -e, --execute         attempts to make a request to the uploadedfile (more useful if
                        uploading a reverse shell)
  -a, --accessible      turns off features which may negatively affect screen readers
  -n, --no-colour       removes colour output

examples:
        python3 nanocmshellv2.py http://10.10.10.10/ rev.php
        python3 nanocmshellv2.py http://hostname:8080 rev-shell.php -a
        ./nanocmshellv2.py https://10.10.10.10 rev-shell -n -e -u 'user'
```
