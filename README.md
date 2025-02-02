# UniFi_with_S2S_and_DNS_on_remote_Site
How to use DNS in remote network when connecting Site-2-Site VPN on UDM or UDR.


![S2S VPN](https://github.com/user-attachments/assets/fceccda7-b664-4fe7-b3e2-983937aac456)

So, we have a configured site-2-site VPN according to the diagram in the figure, ping works between networks, we can open shared resources by accessing hosts by IP address, but we do not understand why, having specified the DNS server 10.0.10.15 in the DHCP UDR setting, clients in "office 2" cannot resolve the host name in "office 1" without receiving a response from it?
What settings need to be made on the UniFi router for everything to work?

And you only need to make two entries in the "Routing" settings section:
1. on the "DNS" tab, specify where to send all requests for your domain

![Screenshot_4](https://github.com/user-attachments/assets/5989a732-b7de-41ec-ac0b-480f1c6e12f6)

![Screenshot_3](https://github.com/user-attachments/assets/c602eb7a-899b-4cc9-b47c-5366781817dd)

2. on the "Static Routes" tab, specify where to return responses

![Screenshot_1](https://github.com/user-attachments/assets/67a0cb0b-2405-46df-9cac-e268fdb4ca3a)

![Screenshot_2](https://github.com/user-attachments/assets/240769e3-fc82-4e05-bf2c-7639503917cb)

After that, after a couple of minutes, try to resolve some host in the remote network with the nslookup command, you should see a response from your DNS server!
