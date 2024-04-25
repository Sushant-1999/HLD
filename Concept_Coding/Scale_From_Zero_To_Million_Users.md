# Scale 0 to Million Users

1) Single Server, Application Server and DB Server Separation, Load Balancer

    * Client - WEbapp, Mobile App
    * Application Server with DB in server itself
    * But if we want to scale it further, We need to remove Server and bring mid tier having application layer only
    * Then comes DB Layer. So we removed dependency by giving different server to each.
    * Now if we need to handle more traffic then first of all replace mid tier with multiple application servers rather than keeping only one. 
    * Then before that bring one layer known as LOAD BALANCER. Client will talk to load balancer and then load balancer will decide whom to pass the request in amidst of Multiple Application server privately IP Address.
    * It brings one layer of Security. It will equally divides the traffic across server to handle traffic 

2) Database Replication 

    * Now here we are improving DB Layer. 
    * It is nothing but Master - Slave concept. I have one Master DB as well as Slave DB which can be more than one.
    * Now all write requests will go to Master DB (Create, Update). And all Read will be done by Slave.
    * Now even one DB is failed we have Replicas and that will handle the request and from slaves one of them will become Master DB. 
    * Now we encountered the failure with respect to DB down / failures. 
    

3) Use of Cache

    * When our Application Server talks with DB it is like Network Call takes time. It is an expensive operation, whenever an application calls DB for read/write/update operation. 
    * DBs Operations are very very very expensive.
    * Now before going to call DB server if we checked if we have data in Cache. Then our application will call cache first.
    * If Cache has data - Cache HIT else no data then server goes to DB Server - Cache MISS.
    * If App. server gets the Data from Cache then he didn't require to approach DB but if not he will call DB server and save the data into Cache. 
    * Here cache helps to improve Performance by avoiding DB Calls.
    * TTL for Cache depending on Application Requirement. When TTL Expires data will purge. 


4) CDN 

    * CDN means Content Delivery Network.
    * CDN Does caching but all those who does Caching are not CDN.
    * CDN having Caching capability but CDN has some other functionality.
    * Suppose we have Data Centre in India and our application has users from all over the world from different Countries,  Now when requests come from all outside world, before that the users in India response will be very fast  but for users outside India response time will increase.
    * As user's location which is near to data center will get fast response But those who are farther to data centre will face Latency Issues. 
    * This problem is solved by CDN. 
    * Now we will insert CDN Nodes for other counties now what CDN does it does Caching of Static Data like HTML pages, Videos, CSS files which doesn't change. 
    * Now when request comes it will go to nearest CDN Node for that country user, Now if data is there in CDN response will given from that CDN but if data is not there in CDN then CDN will ask its nearest CDN if not present then it will go the nearest DB.
    * Now, this gave performance also Security is provided by CDN as we avoided direct Server access
    * Also load is decreased from the Server.
    * Also cost cutting as we don't require multiple DB servers. 
    * Now before going to Load Balancer, client will go to the CDN 


5) Data Centers

    * Client request Load Balancer, Now we have different Data Centers after LB.
    * LB will send request to different Data centers.
    * Data center will have Application Servers, DB Servers. Data centers can present anywhere in the world. But LB sends request to nearest Data Center depending upon Geo Location. 
    *  But if data center one goes down then LB will redirect to another data center. 
     

6) Messaging Queue

    * What is need of Messaging Queue ? 
    * Different types of Messaging Queues are there like Kafka, RabbitMQ. 
    * In messaging Queue we get producer 
