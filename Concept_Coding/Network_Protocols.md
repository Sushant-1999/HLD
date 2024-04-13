# Network Protocols

1. There are total 7 layers in the Network. These are as follows.
    * Application Layer
    * Presentation Layer
    * Session Layer
    * Transport Layer
    * Network Layer
    * Data link Layer
     
2. Lets learn more about Application Layer and Transport Layer in deep.
3. Application Layer
    *  Divided into two types : Client server Protocols , Peer to Peer protocols
    * Client Server Protocols divided into : 
        * HTTP
        * SMTP 
        * FTP 
        * Web Sockets 
    * Peer to Peer Protocols : 
        * WebRTC

    * Client Server Protocols 
        * Communication between web browser (client) with web server (server) it makes request and server gives response via HTTP, FTp , etc
        * But in websocket we have client and server, but websocket is bidirectional communication, Client and server talks with each other. 
        * It is not a peer to peer
        * HTTP have one connection 
        * FTP maintains two connections : control and data connection. Data connection can connect, disconnect but data connection never closes.
        * SMTP used with IMAP and POP. 
        * SMTP used for sending Emails and IMAP used for accessing / reading the mails. SMTP with IMAP is widely used. 
        * WebSocket is used in Messaging Apps like Whatsapp,.. 

    * Peer to Peer Protocols : 
        * We have server, client1, client2. They all can talk with each other and not just client server talking. Everyone talks with each other. 
        * WebRTC is peer to peer. It is a fast.


4. Transport / Network Layer
    * Here we have TCP/IP and UDP/IP .
    * We have data packets through connection and packets divided into sequence . Ordering is maintained and hence if some data packet not came then there is ack.
    * If ack not got then again that packets is sent. 
    * Ordering is there, ack is there and connections is maintained.
    * In UDP, no any connection is maintained. There are various connections data is divided into datagrams and these sent via multiple connections parallely.
    * Ordering is not maintained. 
    * But UDP is fast rather TCP as we are not maintaining connection, not ordering, not ack. Hence fast to send the data. 
    * UDP is helpful for video calling, fast live streaming of data. Here UDP comes in picture and hence WebRTC used UDP protocol to transfer the data.
    * FTP is not secured as it is not encrypted.
    * HTTPS is secured transfer protocol. 
    

     
    