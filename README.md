# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL
## AIM
## ALGORITHM:
1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
# PROGRAM
Developed By: PRAVEEN K
Register No: 212223230153
## CLIENT:
```
import socket
s=socket.socket()
s.bind(('localhost',8000))
s.listen(5)
c,addr=s.accept()
size=int(input("Enter number of frames to send: "))
l=list(range(size))
s=int(input("Enter Window Size: "))
st=0
i=0
while True:
    while(i<len(l)):
        st+=s
        c.send(str(l[i:st]).encode())
        ack=c.recv(1024).decode()
        if ack:
            print(ack)
            i+=s
```
## SERVER:
```
import socket
s=socket.socket()
s.connect(('localhost',8000))
while True:
    print(s.recv(1024).decode())
    s.send("acknowledgement recieved from the server".encode())
```
## OUPUT
## CLIENT
![image](https://github.com/K-PRAVEEN-2005/2b_SLIDING_WINDOW_PROTOCOL/assets/145742724/d409139c-aacb-4bca-8992-6933f53a06d6)
## SERVER
![image](https://github.com/K-PRAVEEN-2005/2b_SLIDING_WINDOW_PROTOCOL/assets/145742724/de732dca-1b4b-4b34-a8b2-8bfc44fe1e5a)


## RESULT
Thus, python program to perform stop and wait protocol was successfully executed
