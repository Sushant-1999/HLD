# Microservices and Its Patterns 


1) Disadvantages of Monolithic 
    * Overloades IDE
    * Difficult to Scale and Costlier
    * Tightly Coupled 
    * Debugging, Deployment, Bug fixing is very hard due to major codebase


2) Advantages of Microservice
    * Managing the components becomes very easy as components are independent
    * Scale is very easy
    * Monolithic service is break down into multiple independent services


3) Disadvantages of Microservice

    * Latency issue can go up if services are not divided properly or we don't decompose monolithic service properly. They will not be loosely coupled. 
    * Monitoring is difficult if some service fails down
    * Transaction Management is difficult


4) Decomposition Patterns

    * Decomposed by Subdomains
    * Decomposed by Business Functionality / Capability
    