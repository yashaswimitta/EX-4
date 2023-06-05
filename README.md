# EX-4 IMPLEMENTATION OF ADDRESS RESOLUTION PROTOCOL (ARP)


## DATE :29-03-2023

## AIM :
To write a python program for simulating ARP protocols using TCP
## ALGORITHM :
### client
```
1.Start the program
2.Using socket connection is established between client and server.
3.Get the IP address to be converted into MAC address.
4.Send this IP address to server.
5.Server returns the MAC address to client.
```
### server
```
1.Start the program
2.Accept the socket which is created by the client.
3.Server maintains the table in which IP and corresponding MAC addresses are stored.
4.Read the IP address which is send by the client.
5.Map the IP address with its MAC address and return the MAC address to client.
```
## PROGRAM :
```
Developed By: Yashaswi Mitta
Reg No: 212221230062
```
### client:
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
### server:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))#
while True:
    ip=input("Enter logical Address : ")
    s.send(ip.encode())
    print("MAC Address",s.recv(1024).decode())
```
## OUTPUT:
![cn 4-1](https://github.com/yashaswimitta/EX-4/assets/94619247/0f84ebf9-cfa6-4899-8f7b-ac3971f11d60)



## RESULT:
Thus, the python program for simulating ARP protocols using TCP was successfully executed.
