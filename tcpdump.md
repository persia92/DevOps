# All About tcpdump
### 1. Draw the IP Header with detailed bits.
### 2. What is tcpdump?
tcpdump is a packet-analizing tool for capturing network traffic in command line. It captures TCP, UDP and ICMP based traffic.
### 3. How to get the HTTPS traffic? Share the command!
```sh
tcpdump port 443 
tcpdump -nN port 443 # for -n and -N Will not show Doamin name
tcpdump -nNX port 443 # for -X, show header and data in hex & ASCII
```
### 4. For everything on an interface, what is the command?
```sh
tcpdump -i any # shows packets from all interfaces 
tcpdump -i eth0 # eth0 = interface-name
```
### 5. Write the command to find Traffic by IP.
```sh
tcpdump host 10.0.2.15 # Everything going in and out
```
### 6. Share the filtering by Source and/or Destination?
```sh
tcpdump dst 10.0.2.15 # Packets coming to this IP
tcpdump src 10.0.2.15 # Packets going from this IP
```
### 7. How to find Packets by Network, write the line.
```sh
sudo tcpdump net 10.0.2.0/24  # Packets from this network only
```
### 8. Using packet contents with Hex Output, write the command.
```sh
tcpdump -X net 10.0.2.0/24 
tcpdump host -X 10.0.2.15
```
### 9. To find a specific port traffic, write the command.
```sh
sudo tcpdump port 22
sudo tcpdump dst port 22
```
### 10.Show Traffic of One Protocol command.
```sh
sudo tcpdump tcp
sudo tcpdump tcp port 80 # get tcp packets from specific port
sudo tcpdump icmp
sudo tcpdump -X udp
```
### 11. Write the command showing only IP6 Traffic.
```sh
sudo tcpdump ip6
```
### 12. Write the command for finding Traffic Using Port Ranges.
```sh
sudo tcpdump portrange 8088-8090
```
### 13.What are PCAP (PEE-cap) files?
### 14.How are PCAP files processed and why is it so?
### 15.Which switch is used to write the PCAP file called capture_file?
### 16.What is the command for reading / writing to capture a File?
### 17.Which switch is needed to read the PCAP files?
### 18.What is the tcpdump command while reading in a file?
### 19.Which switch is used for the ethernet header?
### 20.What is Line-readable output? How is it notified?
### 21.What does -q implify?
### 22.What does this tweak: -t work?
### 23.What does -tttt show?
### 24.To listen on the eth0 interface, which one is used?
### 25.Purpose for -vv ?
### 26.Purpose for -c?
### 27.Why -s is used?
### 28.What does -S, -e, -q, -E implify?
### 29.How to show the raw output view?
### 30.If a specific IP and destined course are given then which tweak is used for?
### 31.To pass from From One Network to Another, the command?
### 32.If a Non ICMP Traffic Goes to a Specific IP, what should be the query?
### 33.If a host isn't on a specific port, what will be tweaked and commanded?
### 34.Why single quotes used?
### 35.How to isolate TCP RST flags?
### 36.To Isolate TCP SYN flags, which query is used?
### 37.To Isolate packets that have both the SYN and ACK flags set, what should be the command?
### 38.How to Isolate TCP URG flags?
### 39.How to Isolate TCP ACK flags?
### 40.Isolate TCP PSH flags?
### 41.Isolate TCP FIN flags.
### 42.How is grep used?
### 43.Command for Both SYN and RST?
### 44.What to do for Cleartext GET Requests?
### 45.What to do to Find HTTP Host Headers?
### 46.How to Find HTTP Cookies?
### 47.The command line for Find SSH Connections?
### 48.How to Find DNS Traffic?
### 49.Command for Find FTP Traffic.
### 50.Find NTP Traffic, what is the command?
### 51.Command to Find Cleartext Passwords?
### 52.Command to Find Cleartext Passwords?
### 53.Describe Evil bit.5
### 54.Write the fun filter to find packets where it’s been toggled.
