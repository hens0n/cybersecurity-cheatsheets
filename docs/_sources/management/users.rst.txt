Users and Groups
================

Add user
--------

Windows
+++++++

.. code-block:: shell

	net user bob bob123 /ADD
	net localgroup "Remote Desktop Users" bob /ADD
	net localgroup "Users" bob /ADD

Linux
+++++++

.. code-block:: shell

	adduser bob
	usermod -aG sudo bob