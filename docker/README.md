# Packet Flow from Docker container


[![N|Solid](https://lh3.googleusercontent.com/pw/AM-JKLUScO7REc9e-wufc-v3wU7d9VJlkLD-BWk4kBhDW7roPGrEF3wn9YhuaXJJWWxHqOoUOGHTbmEdQzSbQkRnCldCZsqtebzPT0FNDYvzc8DvnV6Oj3lOqGAukBQgEQmbtuyapO2a66cQ7GepgimzGJr1kg=w1018-h782-no)](https://lh3.googleusercontent.com/pw/AM-JKLUScO7REc9e-wufc-v3wU7d9VJlkLD-BWk4kBhDW7roPGrEF3wn9YhuaXJJWWxHqOoUOGHTbmEdQzSbQkRnCldCZsqtebzPT0FNDYvzc8DvnV6Oj3lOqGAukBQgEQmbtuyapO2a66cQ7GepgimzGJr1kg=w1018-h782-no)

###### My Environment:  
- virtual mechine(ubuntu)
- Installed docker and pull ngnix image (or any other)
- installed net-tools, tcpdump, tracerote in Both container and host mechine (vm)

To check the packet flow from container to outside, run traceroute from inside the container 
```sh
docker exec -it <container-id> sh # Getting inside the container
cd traceroute 8.8.8.8
```
Result:
[![N|Solid](https://lh3.googleusercontent.com/kenRycznYIBo70xy03e8lHPv-2fSMcSTD-azzcF-RcgMZ6-5udCUOQ_XwEErJvo4PX_pORsVxmdJj2uxNIlo94HrBfEWO_iSFUgvg5XSoa38N6Caw6NWynvDlqnv5tGNzSXiSb1DZ8MGD8hawJhOBYhai6GZfX6e-JFVSBT-ZdNiS6DaYYfBmOh7uCj8h0PTAhk56Y4QqqNQrRg33PJsrXnpuaKwTXKx8el0zA9MPk_O-8tlzvYceMo9SegonK07Flzc2QJW3RWJCXhE8tQsQEtr7EVBapXTHDxc7gGV5UVRMfoOHfvZi4mcHrJXet4SSBre7O74gmzPz6K_lfl_DiskISKjMKhNMw_NljD5eoGwoNAmVWASL6gjgjSYEM0D7CWB33KV8FnuBF-iwg3031XCV0co8A7xw-2Kk8_ZtNgfD1P3DKwewsARCqDsn4V7YM97HOMzaqxHqlkScNYNHvx26fPUtuInMLO4wcW-6NKXJAv8N04LwDojAkxxhfagNAot1Qwxe0QPUr_NJn92o3QezBFszr05YrPXsHDGtdiUskIEoRVLeAd9YRIgmgToi-V6wsqiS2yje0yqtY6bL9Fms_1kvFzmYZRELVa_NHNvU2-2HDVs85dq42A5pE3v8Qdw0h1_2ChFRxFWJ3iBaxXco7pMq5buAQCmh92a5N8i9TU9G5diYrTLsRsNMi6gB6oC8POiMWr89oMGbtRDBLiVrA=w839-h285-no?authuser=0)](https://lh3.googleusercontent.com/kenRycznYIBo70xy03e8lHPv-2fSMcSTD-azzcF-RcgMZ6-5udCUOQ_XwEErJvo4PX_pORsVxmdJj2uxNIlo94HrBfEWO_iSFUgvg5XSoa38N6Caw6NWynvDlqnv5tGNzSXiSb1DZ8MGD8hawJhOBYhai6GZfX6e-JFVSBT-ZdNiS6DaYYfBmOh7uCj8h0PTAhk56Y4QqqNQrRg33PJsrXnpuaKwTXKx8el0zA9MPk_O-8tlzvYceMo9SegonK07Flzc2QJW3RWJCXhE8tQsQEtr7EVBapXTHDxc7gGV5UVRMfoOHfvZi4mcHrJXet4SSBre7O74gmzPz6K_lfl_DiskISKjMKhNMw_NljD5eoGwoNAmVWASL6gjgjSYEM0D7CWB33KV8FnuBF-iwg3031XCV0co8A7xw-2Kk8_ZtNgfD1P3DKwewsARCqDsn4V7YM97HOMzaqxHqlkScNYNHvx26fPUtuInMLO4wcW-6NKXJAv8N04LwDojAkxxhfagNAot1Qwxe0QPUr_NJn92o3QezBFszr05YrPXsHDGtdiUskIEoRVLeAd9YRIgmgToi-V6wsqiS2yje0yqtY6bL9Fms_1kvFzmYZRELVa_NHNvU2-2HDVs85dq42A5pE3v8Qdw0h1_2ChFRxFWJ3iBaxXco7pMq5buAQCmh92a5N8i9TU9G5diYrTLsRsNMi6gB6oC8POiMWr89oMGbtRDBLiVrA=w839-h285-no?authuser=0)
 
 In seperate terminal, we can see these packets from dockerO and vm nic (enp0s3)
 ```sh
sudo tcpdump -i docker0
sudo tcpdump -i enp0s3
```
