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

## References
* http://blog.g0tmi1k.com/2011/08/basic-linux-privilege-escalation/?redirect
* http://www.computersecurity.org/computer-cyber-security-certifications-education-college-courses/cheat-sheet-how-to-pass-the-oscp-offensive-security-certified-professional-exam-step-by-step-guide-enumerating-services-part-2/
* http://www.computersecurity.org/computer-cyber-security-certifications-education-college-courses/cheat-sheet-how-to-pass-the-oscp-offensive-security-certified-professional-exam-step-by-step-guide-sqli-xss-web-app-attacks-part-5/
* http://www.computersecurity.org/computer-cyber-security-certifications-education-college-courses/cheat-sheet-how-to-pass-the-oscp-offensive-security-certified-professional-exam-step-by-step-guide-network-pivoting-part-7/
* https://jordanpotti.com/oscp/
* https://hackingandsecurity.blogspot.com/2016/04/oscp-related-notes.html?m=1
