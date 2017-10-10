Nmap
======


Ping Sweep Example:

.. code-block:: shell

	nmap –v –sn a.b.c.d-z –oG sweep.txt
	grep Up sweep.txt | cut –d " " -f 2

Web Sweep

.. code-block:: shell

	nmap –p 80 a.b.c.0/24 -oG web.txt
	grep Up sweep.txt | cut –d " " -f 2


-   Top 20 TCP ports: nmap –sT –A –top-ports=20 a.b.c.d-z –oG top20.txt
-   OS: nmap –O <IP Address>
-   Banners: nmap –sV –sT <IP Address>
-   NSE Script: nmap --script somescript.nse
-   SMB: nmap –v –p 139, 445 smb.txt a.b.c.d-z