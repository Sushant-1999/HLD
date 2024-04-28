# Messaging Queues

1) What is Messaging Queue and Why it is Needed and Its Advantages ? 

    *  So basically we have Produer , Consumer and Queue.
    * Message first goes from Producer to the Queue gets appended and then Consumer accordingly consumes it. 
    
    * Asynchronous Nature
    * Ecommerce Application Notification System. Its stored in the queue.
    * Queue also bring ReTry Capability. If suppose message sending got failed because of server issues. So we can retry by putting it back in the queue.
    
    * The Pace Matching
    * Now we have ECommerce APP and Inventory App, etc they all want to send notification like Mail. Now they all will call Notification Send. Now different Producer App are generating notifications at different pace faster than the consumer can consume.  So here again Message Queue tackles this problem  by putting all messages in messaging queue and consumer will consume it by its own Pace. So, this is Pace Matching provided by Queue.


2) What is Point to Point and Pub Sub Messaging Types.

    * In point to point when message comes in this message only consumed vai one consumer if we have multiple consumers. 
    * Whenever particular message puts in Queue it will be consumed only once. 

    * But in Pub-Sub we have publisher , Q1, Q2 and C1, C2 whenever message comes it will broadcasted to all the Queues. So here same message can be consumed by multiple Consumers 
    * But in Point to Point single message should consumed by single consumer. 


3) How Kafka Messaging Queue Works ? 

    * Producer talks with Broker (Kafka Server).
    * Now Broker has Topics. Broker can have many such topics.
    * Now Inside Topic there are Partitions. Any partitions it can have. Partitions can be many. 
    * Inside Partitions there is Offset .
    
    * Consumer Reads from the Partition. 
    * Each consumer is part of One Consumer Group. 
    * There can be multiple Consumer Groups having multiple consumers inside it. 
    * There can be many Brokers means Kafka servers multiple present. 
    * And the group of these is called as - Cluster
    * DIfferent brokers they will interact with each other vai ZooKeeper. 
    
    * Now message is composed of these things : Key, Value, Partition, Topic.
    * Key means unique ID, topic in which we want to publish message, partition and message is actual data.


    * Now Topic A has 3 partitions now now message has key it computes hash of it. Now it will see based on key hashing put the data in particular partition. 
    * If any consumer goes down then kafka server will choose another consumer and its check from zookeeper its commited offset - 3 means till 3 it has successfully read the message. 
    * Now from that offset of a particular partition start consuming the message. And that's why consumer groups are used and committed offsets are used. 

    * 
