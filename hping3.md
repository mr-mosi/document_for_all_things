## How to hping3

**hping3** is very good tool to scan network with costumized packets with hping3 we can:

- Test firewall rules
- Advanced port scanning
- Testing net performance
- Path MTU discovery
- Transferring files between even fascist firewall rules
- Traceroute-like under different protocols
- Remote OS fingerprinting & others


Useful commands:

To create an ack packet:

`root@kali:~# hping3 –A 192.168.0.1`

To create SYN scan against different ports:

`root@kali:~# hping3 -8 1-600 –S 10.10.50.202`


