# 2a_Stop_and_Wait_Protocol
## Name : GEETHU R
## Register No. :212224040089
## AIM 
To write a python program to perform stop and wait protocol
## ALGORITHM
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
### Client:
~~~
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
~~~
### Server:
~~~
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("Acknowledgement Received".encode())
~~~
## OUTPUT
![Client](https://github.com/user-attachments/assets/ff0b8d50-a16c-4f32-a241-873b6345f1b0)
![Server](https://github.com/user-attachments/assets/b1143e42-ba43-405a-bbca-25d0fb8b6229)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed.
