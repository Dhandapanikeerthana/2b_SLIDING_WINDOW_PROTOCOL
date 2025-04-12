# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM:
  To write a python program to perform sliding window protocol
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
## PROGRAM
## CLIENT:
import socket<br> 
s=socket.socket() <br>
s.bind(('localhost',8000)) <br>
s.listen(5) <br>
c,addr=s.accept() <br>
size=int(input("Enter number of frames to send : ")) <br>
l=list(range(size)) <br>
s=int(input("Enter Window Size : ")) <br>
st=0 <br>
i=0 <br>
while True:
while(i<len(l)):
st+=s <br>
c.send(str(l[i:st]).encode()) <br>
ack=c.recv(1024).decode() <br>
if ack: 
   print(ack) <br>
    i+=s <br>
 
## SERVER: 
import socket <br>
s=socket.socket() <br>
s.connect(('localhost',8000))<br>
while True:    
    print(s.recv(1024).decode()) <br>
    s.send("acknowledgement recived from the server".encode()) <br>
## OUPUT
![Screenshot (33)](https://github.com/user-attachments/assets/bac6a6fc-6f53-4276-af38-5c72687b1bd5)

## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
