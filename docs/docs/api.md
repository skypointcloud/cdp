# Getting Started With the SkyPoint API

The SkyPoint CDP API is a restful JSON API using Java Web Tokens (JWT). SkyPoint uses Microsoft Azue B2C services for authentication. 

# Prerequisites

Before you can start using the API, you need to do the following:

Sign up for SkyPoint CDP account.
Make sure you have Postman installed on your machine.

# Access APIs using Swagger UI

APIs are categorized into Internal and External.All APIs including parameters and responses, can be found on the [SkyPoint CDP Swagger Page](https://api.skypointcloud.com/swagger/index.html).

If you aren't familiar with Swagger, here's a step-by-step tutorial: [Swagger Tutorial](https://idratherbewriting.com/learnapidoc/pubapis_swagger.html).

1. Go to the [SkyPoint CDP Swagger Page](https://api.skypointcloud.com/swagger/index.html)

2. Click on **Authorize** and use your SkyPoint CDP credentials.

3. Open the **Instances** > **GET /api/instances** endpoint. Select **Try it out** and **Execute** the call.

# Throttling & Rate Limits
Throttling is the process responsible for regulating the rate at which the application processing is conducted. Throttling is a way to practically implement rate-limiting. It lets API developers control how their API is used by setting up a temporary state, allowing the API to assess each request. Rate Limits refers to controlling the amount of incoming and outgoing traffic to or from a network. In this case, the rate limit for our API is set to be 2000 requests/sec. If the number of requests get above the threshold, then the requests after the threshold will get an error message responding that the request limit has reached.

# References & Tips

Here is a quick video on how to use JWT with Postman - https://www.youtube.com/watch?v=LKveAwao9HA

How to generate JWT token using b2clogin - https://docs.microsoft.com/en-us/azure/active-directory-b2c/access-tokens

https://docs.microsoft.com/en-us/azure/active-directory-b2c/overview

https://docs.microsoft.com/en-us/azure/active-directory-b2c/tokens-overview

https://www.youtube.com/watch?v=N7PQGJErXqs
