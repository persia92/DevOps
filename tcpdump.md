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
.pcap files are used for saving captured packet. 
PCAP API captures Live network traffic and save it in .pcap file.
### 14.How are PCAP files processed and why is it so?
PCAP files can be process by many network analyzer including tcpdump.
### 15.Which switch is used to write the PCAP file called capture_file?
Write -w switch
### 16.What is the command for reading / writing to capture a File?
```sh
sudo tcpdump -c 4 -X host 10.0.2.15 -w capture_file.pcap
```
### 17.Which switch is needed to read the PCAP files?
Read -r switch
### 18.What is the tcpdump command while reading in a file?
```sh
sudo tcpdump -r capture_file.pcap
```
you can apply other command of tcpdump in the file content
```sh
sudo tcpdump -nN -r capture_file.pcap
```
### 19.Which switch is used for the ethernet header?
-e switch
```sh
sudo tcpdump -e
```
### 20.What is Line-readable output? How is it notified?
### 21.What does -q implify?
Less Verbose/ quiet / less words
### 22.What does this tweak: -t work?
### 23.What does -tttt show?
### 24.To listen on the eth0 interface, which one is used?
```sh
sudo tcpdump -i eth0
```
### 25.Purpose for -vv ?
verbose / more details of the result
### 26.Purpose for -c?
-c number
For limiting the count of the packets.
### 27.Why -s is used?
-s number
Captured packet size in bytes. s0 = everything
### 28.What does -S, -e, -q, -E implify?
-S = Sequence of the next TCP packet is increased by the size of current packet. -S shows the absolute number of each packets.
-e = Get Ethernet header details. Physical Address and Protocol information.
-q = quiet/ less verbose/ show less details
### 29.How to show the raw output view?
```sh
sudo tcpdump -ttnNvvS
```
### 30.If a specific IP and destined course are given then which tweak is used for?
packets coming from this 10.0.2.2 and destined to 22 port
```sh
sudo tcpdump -vv src 10.0.2.2 and dst port 22
```
### 31.To pass from From One Network to Another, the command?
```sh
sudo tcpdump src net 10.0.2.0/24 and dst net 172.17.0.0/16
```
### 32.If a Non ICMP Traffic Goes to a Specific IP, what should be the query?
```sh
sudo tcpdump -v dst 10.0.2.2 and not icmp
sudo tcpdump -v dst 10.0.2.2 and not tcp 
sudo tcpdump -v dst 10.0.2.2 and not udp
```
### 33.If a host isn't on a specific port, what will be tweaked and commanded?
```sh
sudo tcpdump -v not port 22
sudo tcpdump -v not src port 22
```
### 34.Why single quotes used?
To ignore certain special char/ To group togather
### 35.How to isolate TCP RST flags?
Tcp flag is at offset 13 in the TCP header. So we can use tcp[13] to filter TCP flags.
URG ACK PSH **RST** SYN FIN
32 16 8 **4** 2 1 
```sh
sudo tcpdump 'tcp[13] & 4!=0'
sudo tcpdump 'tcp[tcpflags] == tcp-rst'
```
### 36.To Isolate TCP SYN flags, which query is used?
URG ACK PSH RST **SYN** FIN
32 16 8 4 **2** 1 
```sh
sudo tcpdump 'tcp[13] & 2!=0'
sudo tcpdump 'tcp[tcpflags] == tcp-syn'
```
### 37.To Isolate packets that have both the SYN and ACK flags set, what should be the command?
URG **ACK** PSH RST **SYN** FIN
0 1 0 0 1 0
```sh
sudo tcpdump 'tcp[13] & 18!=0'
```
### 38.How to Isolate TCP URG flags?
**URG** ACK PSH RST SYN FIN
**32** 16 8 4 2 1 
```sh
sudo tcpdump 'tcp[13] & 32!=0'
sudo tcpdump 'tcp[tcpflags] == tcp-urg'
```
### 39.How to Isolate TCP ACK flags?
URG **ACK** PSH RST SYN FIN
32 **16** 8 4 2 1 
```sh
sudo tcpdump 'tcp[13] & 16!=0'
sudo tcpdump 'tcp[tcpflags] == tcp-ack'
```
### 40.Isolate TCP PSH flags?
URG ACK **PSH** RST SYN FIN
32 16 **8** 4 2 1 
```sh
sudo tcpdump 'tcp[13] & 8!=0'
sudo tcpdump 'tcp[tcpflags] == tcp-psh'
```
### 41.Isolate TCP FIN flags.
URG ACK PSH RST SYN FIN
32 16 8 4 2 1 
```sh
sudo tcpdump 'tcp[13] & 1!=0'
sudo tcpdump 'tcp[tcpflags] == tcp-fin'
```
### 42.How is grep used?
captures specific text from the command result 
command -vvl | grep 'Text'
### 43.Command for Both SYN and RST?
URG ACK PSH **RST** **SYN** FIN
0 0 0 1 1 0
```sh
sudo tcpdump 'tcp[13] & 6!=0'
```
### 44.What to do for Cleartext GET Requests?
```sh
sudo tcpdump -vvl | grep 'GET:'
```
### 45.What to do to Find HTTP Host Headers?
```sh
sudo tcpdump -vvAls0 | grep 'HOST:'
```
### 46.How to Find HTTP Cookies?
```sh
sudo tcpdump -vvls0 | grep 'cookie:'
```
### 47.The command line for Find SSH Connections?
### 48.How to Find DNS Traffic?
### 49.Command for Find FTP Traffic.
### 50.Find NTP Traffic, what is the command?
### 51.Command to Find Cleartext Passwords?
### 52.Command to Find Cleartext Passwords?
### 53.Describe Evil bit.5
### 54.Write the fun filter to find packets where it’s been toggled.
