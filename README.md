# Sephora-IOS-Application-Jmeter-Test-Script
Sephora IOS Application JMeter Test Script

JMX File name - Sephora_TestAssessment.jmx

Apache JMeter Version - 5.6.3

Tool: Jmeter
Application: Sephora
https://apps.apple.com/us/app/sephora-buy-makeup-skincare/id393328150?icid2=ios_app_hotspot_bopis_lp or
https://play.google.com/store/apps/details?id=com.sephora&icid2=android_app_hotspot_bopis_lp 

# LISTS OF TASKS TO BE PERFORMED - 

1. 	Open App,	100%

2. 	Item Selection,	100%
 	
         Search-> Open item,	30%
   
      	 Select random recommendation,	20%
        
      	 Select random just dropped,	10%	
        
      	 Select random selling fast,	10%	
        
      	 Shop->Random Category->Random Product,	30%

    Search Criteria
   	
   	    Set of keywords for search with Probability%
   	
        Fragrance,30
   	
        Lipstick,20
   	
        Color,20
   	
        Shampoo,10
   	
        Skin,10
   	
        Eye,5
   	
        Face,5

   
4. 	Add to cart,	60%

5. 	Think time 5...10 seconds.

6. 	New user at each iteration.

7. 	A product should be available before adding to Cart.

8. 	Average shopping cart size – 4 items.

9. 	Average user session duration – 4 minutes.


# TASKS THAT WERE NOT ACHIEVED - 
  
 1. A product should be available before adding to Cart.
  
        EXPLANATION - As per my JSON extractor logic, I was not able to find the business relevance with any propery Key that could help me identify if the product is available.i.e, Either isAvailable or isInStock key. I would reach out to the product team to understand which property refers to product availability and apply the same logic to my Json as applied for randomization in other transactions.

  2. On Running with multiple user/thread, The generate token api is giving me 403 forbidden error. Thus, able to run it successfully with Single thread only.


# TYPES OF JMETER ELEMENTS USED IN MY SCRIPT - 

Thread Group - To group all my Transactions in the test plan.
Disabled "Same User on each Iteration" in my test plan.

HTTP(S) Test Script Recorder - To Record all the transactions from the ios mobile app.

HTTP Cookie Manager - To manage all the cookies and sessions.

Random Variables - To create random values for product Indexes and Think times.

User Defined Variables - To pass my Login creds to the application.

bzm - Weighted Switch Controller - To handle the weighted scenario of transactions for the percentage distribution of threads/user sessions.

Flow Control Action - To add think times between all transactions.

Boundary Extractor - To extract the token value from the API.

JSON Extractor - To extract the respective values from the APIs to correlate the dynamic values from the user.

Debug Sampler - To debug my application script during development.

Duration Assertion - To check that user session takes <4 mins for execution.

View Results Tree and Summary Report - Listeners to check on the report of my transactions.
