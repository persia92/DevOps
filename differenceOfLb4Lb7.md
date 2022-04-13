## Difference between Layer 4 and Layer 7 Load Balancer

| Layer 4 LB  | Layer 7 LB |
| ------------- | ------------- |
| Operates at Transport Layer  | Operates at Application Layer  |
| Offers simple packet-level load balancing. (Take limited route decisions based on examining TCP/UDP packets)  | Offers smart routing based on the path and host  |
| Doesn't inspect/decrypt data inside packet. | Inspect data, perform decryption and other mechanism for routing |
| Fast and efficient as it doesn’t consider the data. | More Expensive in both scenario  |
| Doesn't have cache mechanism. | Have caching mechanism (sticky session)  |
| More secure as it doesn’t consider the data. | User's certificate must be shared with the load balancers.  |




##### Reference:
https://medium.com/@harishramkumar/difference-between-layer-4-vs-layer-7-load-balancing-57464e29ed9f
https://docs.aws.amazon.com/elasticloadbalancing/latest/classic/elb-sticky-sessions.html
