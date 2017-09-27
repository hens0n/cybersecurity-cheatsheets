Services
========

Starting Services
-----------------

Windows
+++++++

.. code-block:: shell

	systemctl start ssh
	systemctl start apache2
	service apache2 start

Linux
+++++

.. code-block:: shell

	systemctl start ssh
	systemctl start apache2
	service apache2 start


Enable/Disable service to start on boot
---------------------------------------

Linux
+++++

.. code-block:: shell

	systemctl enable apache2
	systemctl disable apache2