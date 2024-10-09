# 2b IMPLEMENTATION OF SLIDING WINDOW PROTOCOL


## AIM

To implement the sliding window protocol using Python.


## ALGORITHM:

1. Start the program.
2. Get the frame size from the user
3. To create the frame based on the user request.
4. To send frames to server from the client side.
5. If your frames reach the server it will send ACK signal to client
6. Stop the Program
   
## PROGRAM
DEVELOPED BY:JWALAMUKHI S
REGISTER:212223040079

CLIENT
```
import socket
s=socket.socket()
s.bind(('localhost',8003))
s.listen(5)
c,addr=s.accept()
size=int(input("enter number of frames to send:"))
l=list(range(size))
s=int(input("enter window size:"))
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

SERVER
```
import socket 
s=socket.socket()
s.connect(('localhost',8003))
while True:
    print(s.recv(1024).decode())
    s.send("acknowledgement received from server".encode())
```

## OUTPUT
CLIENT

![image](https://github.com/user-attachments/assets/e76c047f-cd53-4c2a-b49a-b9d812703119)





SERVER

![image](https://github.com/user-attachments/assets/719cd7b8-f7dc-4578-a5a7-3ae25344a66b)



## RESULT
Thus, python program to  implement the sliding window protocol using Python  was successfully executed.
