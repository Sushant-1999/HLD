# Load Balancers and Its Different Algorithms 


1) What is Load Balancer ? 

    * We have many clients and we have many servers as well. When request comes from a client so one server should not get overloaded so we need to put the Load Balancer.
    * Load Balancer should distribute the traffic appropriately to all the servers so that no single server should get overburden.

2) Types of Load Balancer 

    * Network Load Balancer Type (L4 Balancer) (Transport Layer of OSI Model - 4)
    * Application Load Balancer Type (L7 Balancer)(Application Layer of OSI Model - 7)

    * Major difference between these two is L7 can read your header, session, data as well response. It can take decisions to distribute traffic based on these information. It can also do caching because it can read the response. It is much more advanced.

    * L4 can have TCP port, IP address of Source and Destination, UDP Port.
    * Based on these info it routes the traffic. But it is much more fast.

3) Algorithms of L4 Load Balancer

    * Static Algorithms 
        * Round Robin Algorithm
            * Multiple client sending request to LB.
            * Round Robin then distribute first to 1, second to 2 then 3 to first then 4 to second like this fashion.
             
            * Advantages of Round Robin Algorithm 
                * Very easy to implement.
                * Equal distribution of load to all servers

            * Disadvantages 
                * One server with high capability and other with low capability will be treated as same.
                * So chance of low capacity server will go down to overload of requests 

        * Weighted Round Robin Algorithm
            * It gives the weight to server which solves the issues of Round Robin.
            * Now when request coming, weight represents capacity of the server. 
            * Serve 1 is 3 times more than server 2.
            * So first 3 requests will go to server 1 due to more capacity determined by weight.
            * 4th request will go server 2. 5,6,7 will go to server 1.

                * Advantages 
                    * Low capacity server will be saved from getting large no of requests
                    * Easy to implement as weights are static no any dynamic computation as weight is fixed.

                * Disadvantages
                    * The requests which comes, If requests having different processing time, then its possible that low capacity server gets high processing requests and will get overburdened.


        * IP Hash Algorithm

            * WE compute the Hash of IP Address and with this hash we get to know which server to redirect that request. 
            * Same client should go to this server only then this algorithms is useful enough. 
            * Easy to implement.

                * Disadvantages
                    * If clients request is coming through the PROXY then all the clients will be having same IP address and that will overburden the same server only. 
                    * Can't ensure the equal load distribution.

    
    * Dynamic Algorithms 

        * Least Connection

            * now request are coming from clients.
            * Here LB will check which server has less active connections so he will transfer that request to least active connection server so LB will calculate the load dynamically and redirect to less load server.
            * This will guarantee that no single server will get overburden.

                * Disadvantages
                    * No difference between LOW Capacity and High Capacity server. Chances  that low capacity will get overburden.


        * Weighted Least Connection
            * So, here we have assigned the weight also to determine which one having high and low capacity of the server. 
            * When any new request comes it will calculate the ratio of no of Active connections to its weight. And it will forward to min ratio

        * LEAST Response Time

            * TTFB : Time interval between Sending a Request and receiving the response from the server.
            * Now each server is having TTFB Calculated along with no of active connections. This response time is calculated by LB Dynamically .
            * It will pick the server with less TTFB and multiply with active connections.


        

