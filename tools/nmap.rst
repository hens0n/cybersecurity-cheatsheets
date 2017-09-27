Nmap
======

Shell
-----
-   Ping sweep: nmap –v –sn a.b.c.d-z –oG sweep.txt
    -   Grep Up sweep.txt | cut –d " " -f 2
-   Web sweep: nmap –p 80 a.b.c.0/24 -oG web.txt
-   Top 20 TCP ports: nmap –sT –A –top-ports=20 a.b.c.d-z –oG top20.txt
-   OS: nmap –O <IP Address>
-   Banners: nmap –sV –sT <IP Address>
-   NSE Script: nmap --script somescript.nse
-   SMB: nmap –v –p 139, 445 smb.txt a.b.c.d-z