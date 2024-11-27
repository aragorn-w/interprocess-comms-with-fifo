# Inter Process Communication Using FIFOs

In this project, I extend the restricted shell, rsh, by adding a new built-in command to send messages to other users. The 13th command, **sendmsg**, can be uses as in the following example:

```
rsh>sendmsg user2 hello there!
```

The command above should send the message "hello there!" to user **user2**. Note that the message is not enclosed within quotes.

### Compiling, Running, and Testing the Code

You can compile the server by typing **make server** and compile the client by typing **make rsh**. In order to test the code, you should first create 3 FIFOs like below:

```
mkfifo serverFIFO
mkfifo user1
mkfifo user2
```

These are the server and the client FIFOs. You can then run the server by typing "./server &" to run it in the background. Don't forget to kill the process after your finished with your testing. You can also run it in the foreground and run the client processes on different terminals.

In order to run a client, you execute rsh with the user name command line argument like below:

```
./rsh user1
```

You can then run a different client on a different terminal with username user2. Make sure your user names match the FIFOs you have created. If you have completed the implementation correctly, you should be able to send messages and see the messages arrive at the other user's rsh prompt.

This project will have only one test case, which is publicly available in the "test" directory. You can inspect the inputs and the expected outputs for each of the 3 processes in a session with a server and two clients.
