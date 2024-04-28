# High Availability 


1) Single Nodes 

    * Single Nodes may get down so system will also become down as node get crashed somehow.


2) Multi Nodes 

    * Multi Nodes has two types
        * Active - Passive 
        * Active - Active  

3) Active - Passive Architecture

    * Now request is coming. We have load balancer and load balancer moved it to the data centre 1 and it is write request. 
    * We have 2nd data center which is replication of first primary data center. 
    * In active-passive model only one is primary node and other one is replicated node which is used for disaster recovery hence replication. 
    * And whenever request comes to disaster recovery data center then application layer connects to primary DB to store data.
    * And hence any request coming to disaster recovery node due to load balancer its application layer moves the traffic to the Primary or Live DB.
    * And there will be sync up will happen from primary DB to replica DB.
    * So when any request read comes we can read it from replica NODE. Hence replica DB is known as REPLICA DB.
    * But when any write request comes in it goes to LIVE DB or PRIMARY DB. 
    * So when any write request comes in we can move it to LIVE DB and all READ we can move to REPLICA DB.


4) Data Resilience (How to avoid Single Point of Failure)

    * For this we can make Disaster Recovery Node as Primary Node means Read - Write Access so even one node fails other one is there to handle. 
    * Here one disadvantage is that latency will increase as request is served by other location node.
    *  Other disadvantage is when any DB failure happens then app has to route to Replica Node and make it Primary. So till to make him Primary the request for some time failure will happen till other becomes Primary Node.


5) Active - Active Architecture

    * Oracle, Sql, Postgresql does not support multimaster writes. 
    * In Active - Active there is client and LB and data center 1 - Mumbai, data center 2 - Pune. 
    * Now both nodes are Primary means Live having its own DB which is also Primary and live. 
    * In active-active - Bidirectional Sync Up will happen but in active - passive : one directional sync up will be there.
    * There are issues here, when request comes to DC1 for write and simultaneously Read request comes to DC2 then before sync up it will read incorrect (inconsistent) data.
    * Hence there are some conflicts due to multimaster for sync up to happen. 
    * But in this we are utilizing our resource very will in this case and traffic is very well handle due to both are READ WRITE operations are taken care rather than only one master node. 
    
    