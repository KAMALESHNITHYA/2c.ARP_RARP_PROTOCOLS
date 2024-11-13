# 2c.SIMULATING ARP /RARP PROTOCOLS

## NAME : KAMALESH R
## REGISTER NUMBER : 212223230094

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


## client
```
socket 
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

## server
```
import socket 
s=socket.socket() 
s.connect(('localhost',8000)) 
while True: 
     ip=input("Enter logical Address : ") 
     s.send(ip.encode()) 
     print("MAC Address",s.recv(1024).decode())
```
## OUPUT - ARP

### CLIENT 
![image](https://github.com/user-attachments/assets/6ab7989c-11b1-4f02-b0c4-f5d4fec14179)
### SERVER
![image](https://github.com/user-attachments/assets/eebba58e-5536-4077-bfee-0baa6b4518b5)

## PROGRAM - RARP

## client
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

## server
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

### CLIENT 
![image](https://github.com/user-attachments/assets/e891444b-94ad-4fc4-bb25-a18fd59565e0)
### SERVER
![image](https://github.com/user-attachments/assets/867d1120-3039-4e86-b26e-71f1f47ee8b5)

## RESULT
Thus, the python program for simulating ARP protocols using TCP was successfully 
executed.
