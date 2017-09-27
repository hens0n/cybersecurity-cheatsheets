iptables
========

-   Allow input on port: iptables -A INPUT -p tcp --dport [port] -j ACCEPT
-   iptables -A INPUT -p tcp --dport 22 -j ACCEPT
-   iptables -A INPUT -p udp--dport 22 -j ACCEPT
-   Traffic analysis
    -   iptables -I INPUT 1 -s [your_ip_address]-j ACCEPT
    -   iptables -I OUTPUT 1 -s [your_ip_address]-j ACCEPT
    -   iptables –Z
    -   iptables –vn -L

-   Clean up rules: iptables -F INPUT