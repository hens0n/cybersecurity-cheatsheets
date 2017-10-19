Users and Groups
================

Add user
--------

Windows2
++++++++

.. code-block:: shell

	net user bob bob123 /ADD
	net localgroup "Remote Desktop Users" bob /ADD
	net localgroup "Users" bob /ADD

Linux2
+++++++

.. code-block:: shell

	adduser bob
	usermod -aG sudo bob