# Scalability 


1) what is Scalability ? 
    * The ability to handle more requests by buying more machines or buying more machines 
    * Buy more machines -> Horizontal Scaling
    * Buy bigger machines -> Vertical Scaling

2) Comparison 

    * Horizontal Scaling 
        * Load balancing is required 
        * Resilient (If one server crashes some other will handle requests)
        * network calls
        * Data consistency is issue
        * Scales well as User Increases

    * Vertical Scaling
        * Not LB Required
        * Single point of failure
        * Inter process communication   
        * Consistent Data
        * Hardware Limit 