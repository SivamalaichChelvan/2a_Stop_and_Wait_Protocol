# 2a_Stop_and_Wait_Protocol
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## SERVER SIDE
```
(1)Start
(2)Import the socket library.
(3)Create a socket using socket() function.
(4)Bind the socket to the local host and port number 8001.
(5)Put the socket into listening mode using listen().
(6)Accept a connection request from the client using accept().
(7)Repeat the following steps until communication ends:
(a)Read data from the user (frame).
(b)Send the data to the client using send().
(c)Wait for acknowledgement from the client using recv().
(d)If acknowledgement is received:
•Display the acknowledgement.
•Continue sending the next data.
(e)Else:
•Close the connection.
•Stop execution
(8)Stop
```
## CLIENT SIDE
```
(1)Start
(2)Import the socket library.
(3)Create a socket using socket() function.
(4)Connect the socket to the server using host name and port number 8001.
(5)Repeat the following steps:
•Receive data (frame) from the server using recv().
•Display the received data.
•end acknowledgement to the server using send().
(6)Continue until the server closes the connection.
(7)Stop
```

## PROGRAM
```
import socket
s=socket.socket()
s.connect(('localhost', 8001))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Recived from the server".encode())
```

```
import socket
s=socket.socket()
s.bind(('localhost', 8001))
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
<img width="474" height="186" alt="image" src="https://github.com/user-attachments/assets/790712b4-d81e-48f8-9c64-9ac24b917ef3" />
<img width="511" height="186" alt="image" src="https://github.com/user-attachments/assets/89a84ab1-628b-4ffb-8c26-552891631162" />


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
