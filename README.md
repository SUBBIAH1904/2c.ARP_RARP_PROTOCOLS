### 2c.SIMULATING ARP /RARP PROTOCOLS

### AIM:
To write a python program for simulating ARP protocols using TCP.
### ALGORITHM:
### Client:
1. Start the program
2. Using socket connection is established between client and server.
3. Get the IP address to be converted into MAC address.
4. Send this IP address to server.
5. Server returns the MAC address to client.
### Server:
1. Start the program
2. Accept the socket which is created by the client.
3. Server maintains the table in which IP and corresponding MAC addresses are
stored.
4. Read the IP address which is send by the client.
5. Map the IP address with its MAC address and return the MAC address to client.
P
### PROGRAM - ARP:
### Client:
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
### Server:
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
### OUPUT - ARP:
## Client:
![WhatsApp Image 2024-03-05 at 8 05 43 PM](https://github.com/SUBBIAH1904/2c.ARP_RARP_PROTOCOLS/assets/147473604/53e3a0aa-1b41-4680-820f-ca049ba9c5b7)
## Server:
![WhatsApp Image 2024-03-05 at 8 05 43 PM (1)](https://github.com/SUBBIAH1904/2c.ARP_RARP_PROTOCOLS/assets/147473604/752214d1-4b07-4849-986e-15ff493396da)

### PROGRAM - RARP:
### Client:
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
### Server:
```
import socket
s=socket.socket()
s.connect(('localhost',9000))
while True:
 ip=input("Enter MAC Address : ")
 s.send(ip.encode())
 print("Logical Address",s.recv(1024).decode())
```
### OUPUT -RARP
### Client:
![WhatsApp Image 2024-03-05 at 8 05 43 PM](https://github.com/SUBBIAH1904/2c.ARP_RARP_PROTOCOLS/assets/147473604/302fb360-8d1f-4f09-9415-75337d5a611a)
### Server:
![WhatsApp Image 2024-03-05 at 8 05 43 PM (1)](https://github.com/SUBBIAH1904/2c.ARP_RARP_PROTOCOLS/assets/147473604/e5ee7870-ff98-4006-94e3-d49f87c9a786)
### RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
