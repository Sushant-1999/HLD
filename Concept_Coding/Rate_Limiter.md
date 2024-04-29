# Design Rate Limiter

1) What is Need of Rate Limiter and Why it is Made ? 

    * DDOS Attacks, in these attacks attackers send unwanted requests to the server. ANd each server has limited resources like RAM, DISK Space.
    * Attackers send lots of request like in thousands and lakhs of requests per second and all of the resources consumed and server becomes DOWN.
    * And when genuine use makes request he will not be fulfilled.
    * Hence we should make rate limiter for our APIs.


2) Algorithms for our Rate Limiter 

    * Token Bucket
    * Leaking Bucket
    * Fixed Window
    * Sliding Window Log
    * Sliding Window Counter


3) Token Bucket Algorithm

    * There is bucket : Capacity of Bucket : No of tokens hold by bucket.
    * There is Refiller : In 1 min or 2 min or 3 min how many token he add in the bucket and all this is driven by configuration file.
    * Whenever request are coming,  first it will check is there token present ? If yes then it will consume the request and count is decreased.
    * But if there is no token then request is denied.
    * This is how Token Bucket Algorithm is works.

    * Refiller runs after some time and fills the counter and when counter > 0 then only request will be processed but when counter == 0 then request will be denied. 


4) Leaking Bucket 

    *  There is some tap from where requests are coming randomly but bucket has some fixed capacity but out of requests coming there is some leak which is constant at a fixed rate, these requests are processed via leak.
    * So when incoming request are more than processing rate then there will be overflow and requests will be denied.
    * And this is implemented vai Queue.

    * If queue is not full then request will be added in the queue. But if the queue is Full then request will be denied.
    * Disadvantage of this algo is that, as there is constant rate of fulfilling the algorithm when major requests coming then due to constant speed many of the request will be denied like Amazon Prime, night time more request will come.
    * Hence it will not be efficient for such Applications. 

5) Fixed Window Counter Algorithm

    * There is counter set for fixed window.
    * Disadvantage like 

6) Sliding Window Log Algorithm
    
    * There is no fixed window here.
    * It will log the request but not fulfill when request count crosses for a window like limit crossed for 3 Req / min.
    * Even the request is denied we are logging the request.

7) Sliding Window Counter Algorithm

    * It adds two functionality : fixed window counter + Sliding window log.
    * IT takes advantages of both
    * In 1 min : 5 Req.
    * Goal is to find the no of requests present in this window.



8) HLD Diagram of Rate Limiter (Components)

    * We need Counter, in memory : Redis we can use to maintain the counter
    * Also Config File to store the configurations 
    * We have Client and We have Server.
    * Now we need to put Rate Limiter in between both

    * Now client send request to rate limiter and rate limiter sends it to the server.
    * Now Rate Limiter should have Redis to maintain the counter, its updation and all.
    * Also there will be some Config Files.
    * So to Read them we will need cache for COnfig File for real time updation, fetching and all.
    * We can bring Atomicity to Redis already present solution we dont need to develop by own but latency will increase we need to bear that.
    
