# EXP 2A. : STOP AND WAIT PROTOCOL :

## NAME : RUSHMITHA  R
## REGISTRATION NUMBER : 212224040281

## AIM :
To write a python program to perform stop and wait protocol


## ALGORITHM :
1. Start the program.

2. Get the frame size from the user

3. To create the frame based on the user request.

4. To send frames to server from the client side.

5. If your frames reach the server it will send ACK signal to client

6. Stop the Program


## PROGRAM
### Server Side :
```
#server
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement received".encode())
```
### Client Side :

```
#client
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
while True:
    i=input("Enter a data: ")
    c.send(i.encode())
    ack=c.recv(1024).decode()
    if ack:
        print(ack)
        continue
    else:
        c.close()
        break
```

## OUTPUT

### Server side:
<img width="1695" height="1081" alt="EXP 2 A CLIENT" src="https://github.com/user-attachments/assets/aab3fc06-dcaf-4958-9c2a-88b4e7a57495" />


### Client Side:
<img width="1695" height="1081" alt="EXP 2 A CLIENT" src="https://github.com/user-attachments/assets/1c6697d2-76cd-4ae7-aba0-25a4c5f6cd00" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
