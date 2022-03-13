
### Load Balancer (LB): 
Exactly what the name suggests. Balancing traffics among apps/networks. :P
LB usually grouped into two categories: 
- Layer 4
- Layer 7

Requests are distributed to a particular server based on a configured algorithm. some common algorithms -
- Round robin
- Weighted round-robin
- Least connections
- Least response time, etc

## Layer 4 LB
- Works at the transport layer, using the TCP and UDP protocols.
- Simple Packet-level load balancing
- Messages are neither inspected/decrypted
- Forwarded quickly & securely.
- Creates a stateful connection and maintains it. 1 TCP connection


![Layer 4 LB](https://miro.medium.com/max/1400/1*ttz8Pjhn2noTHu5DQzgWXg.png)

## Layer 7 LB
- Works as Proxy. Getting a request from the Client and creating a new one to a server based on requesting host/path. 
- Stateless
- Operates at the application level, using protocols such as HTTP and SMTP to make decisions.
- Two types: host-based and path-based routing. 
- Inspects messages, performs decryption & makes content-based routing decisions.
- 
![Layer 4 LB](https://miro.medium.com/max/1154/1*ce0nAN9RL88VUPl8bu9NBA.png)


## Reference: 
- Image Link -https://levelup.gitconnected.com/l4-vs-l7-load-balancing-d2012e271f56

