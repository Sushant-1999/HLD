# CAP Theorem

1. It is desirable property of Distributed System with replicated data. C - Consistency, A - Availability, P - Partition Tolerance
2. In Distributed System, all 3 properties commonly can't used either use CP, CA, AP

3. What is Consistency ? 
    * Consistency should give proper data should be in sync across all the Nodes. 
    * This is meant by consistency. Data is consistent across all the Nodes after successful write in One node.
     
4. What is Availability ? 
    * Suppose we have two DB Nodes B or C . All nodes at least respond. All nodes should respond. Either Success or Failure but it should respond. Means all nodes are available.

5. What is Partition Tolerance ? 
    *  If there is breakage between Node B and C . IF we consider 3 Nodes A, B, C over here.  Still A is able to query B and C. He is doing Request and getting response means system is UP after partition in two nodes. 
    * Partition tolerance is if there is partition breakage still system is UP then it is. 

6. Now, let's see why we can't use CAP three principles altogether (eksath) ?

    *  Possibilites : CA, CP, AP 
    *  Not Possible : CAP

    * Consider three Nodes : A, B, C connected each other. B and C are DB Nodes.
    *  Now, Lets see C : C means at any point of time, data should be in sync with B and C as they are DB nodes, data should be consistent after writes, reads. Both nodes should give consistent data. Hence 'C' is possible. 
    * Now, let's see 'A'. A means availability both nodes should be available at any point of time and should respond . Hence it is possible. 
    * Now, let's see 'P'. P means after partition breakage system should be UP and give data. 
    * There is breakage. Now some writes happened in A but there is partition breakage hence write in B but B should not send update to C due to breakage hence there happened inconsistency as C couldn't sync. Hence 'C' dropped. 
    * Hence 'AP' satisfied over here. Consistency gets comprimized. 
    * Now consider 'CP' . If partition happened for 5 to 10 min. Then we have achieved C by downing C node. Here 'CP' is possible but not 'A' because we have made one Node C down to achieve CP
    *  Now lets consider 'CA' here we should not consider P partion tolerance but we achieved C and A as well but we can't do P. As partition is not here all nodes are available and consistency is there at all nodes. Hence 'CA' achieved. 
    * Hence, 'CAP' altogether is not possible at all. 
    * As in real life 'P' happens we can't tolerate this but we have option which one we should trade off ON C or A. P can't never trade off. We need to choose between C or A which one to choose. 
    * Partition Tolerance means after breakage in any node communication do our system is UP or NOT. 
