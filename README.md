![WhatsApp Image 2024-03-05 at 20 08 42_ac2f5f59](https://github.com/Pradeepkumar-2005/2c.ARP_RARP_PROTOCOLS/assets/147474038/e09db481-608c-4d62-99b7-d3f468d9ace5)# 2c.SIMULATING ARP /RARP PROTOCOLS
## AIM
To write a python program for simulating ARP protocols using TCP.
## ALGORITHM:
## Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
## Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
P
## PROGRAM - ARP
# Cilent
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
address={"165.165.80.80":"6A:08:AA:C2","165.165.79.1":"8A:BC:E3:FA"};
while True:
 ip=c.recv(1024).decode()
 try:
 c.send(address[ip].encode())
 except KeyError:
 c.send("Not Found".encode())
```
# Server
```
 import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
REG NO:
 ip=input("Enter logical Address : ")
 s.send(ip.encode())
 print("MAC Address",s.recv(1024).decode()
```

## OUPUT - ARP
# Cilent
![WhatsApp Image 2024-03-05 at 20 05 44_c3a6377d](https://github.com/Pradeepkumar-2005/2c.ARP_RARP_PROTOCOLS/assets/147474038/9133ba15-68ad-414b-9dd3-ce5275f1debb)


# Server
![WhatsApp Image 2024-03-05 at 20 05 44_4305be37](https://github.com/Pradeepkumar-2005/2c.ARP_RARP_PROTOCOLS/assets/147474038/d42fdbca-315a-4150-933d-0f9da5e31eae)


## PROGRAM - RARP
# Cilent
```
import socket
s=socket.socket()
s.bind(('localhost',9000))
s.listen(5)
c,addr=s.accept()
address={"6A:08:AA:C2":"192.168.1.100","8A:BC:E3:FA":"192.168.1.99"};
while True:
 ip=c.recv(1024).decode()
 try:
   c.send(address[ip].encode())
 except KeyError:
   c.send("Not Found".encode())
```
# Server
```
import socket
s=socket.socket()
s.connect(('localhost',9000))
while True:
 ip=input("Enter MAC Address : ")
 s.send(ip.encode())
 print("Logical Address",s.recv(1024).decode())
```


## OUPUT -RARP
# Cilent
![WhatsApp Image 2024-03-05 at 20 08 42_7cfb5dfc](https://github.com/Pradeepkumar-2005/2c.ARP_RARP_PROTOCOLS/assets/147474038/532b7396-bfaa-47ba-8564-9ed4ad11c40a)


# Server
![WhatsApp Image 2024-03-05 at 20 08 42_a3f460ea](https://github.com/Pradeepkumar-2005/2c.ARP_RARP_PROTOCOLS/assets/147474038/f715f737-ebc2-4a53-8958-91bbcecd1f90)



## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
