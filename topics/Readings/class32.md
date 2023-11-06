# Class 32:AWS Amplify ,Intro to Serverless and GraphQL.

# RESTful APIs vs. GraphQL

## RESTful APIs

- **Representational State Transfer (REST)** is an architectural style for designing networked applications.
- RESTful APIs use HTTP methods like GET, POST, PUT, and DELETE for data manipulation.
- Key characteristics:
  - Stateless: Each request must contain all necessary information, and the server should not store client state.
  - Client-Server: Clear separation between client (UI) and server (processing).
  - Uniform Interface: Consistent interface using standard HTTP methods and URIs.
  - Layered System: Supports intermediaries between clients and servers.
  - Stateless Communication: No client state is maintained.

## GraphQL

- **GraphQL** is a query language for APIs, allowing clients to request precisely the data they need.
- Developed by Facebook, GraphQL offers flexibility and efficiency in fetching data.
- Benefits of GraphQL:
  - Precise Data Retrieval: Clients specify needed data, avoiding over-fetching or under-fetching.
  - Reduced Requests: Multiple data types retrieved in one request.
  - Client-Driven Queries: Clients determine data needs, promoting responsive front-end applications.
  - Schema-Based: GraphQL schemas define data types and relationships.
  
- Downsides of GraphQL:
  - Learning Curve: Steeper learning curve compared to REST.
  - Large Queries: Potential for server overload due to large queries.
  - Caching Complexity: Caching can be complex as data retrieval is not tied to specific endpoints.
  - Security: Poorly designed APIs can lead to security issues if queries are unrestricted.

The choice between RESTful APIs and GraphQL depends on project-specific requirements. GraphQL excels in precise data retrieval, but it requires careful planning to avoid potential issues.



# Understanding "Serverless" Computing

Imagine you're running a restaurant. In the traditional way, you'd need to own a big kitchen with lots of equipment, hire chefs, and manage everything yourself. This is like having your own servers in the tech world. You need to worry about maintaining them, keeping them running 24/7, and paying for all the equipment, even if it's not always in use.

Now, think about a different approach - a food delivery service. You don't own a kitchen, you don't hire chefs, and you don't deal with all the kitchen stuff. You just focus on taking orders and delivering food. When someone orders, you prepare the food and deliver it. You pay only for what you use. This is similar to the idea of "serverless" in technology.

In a serverless system, you don't need to own or manage servers. You focus on writing your code (making food) and let a cloud provider (like AWS, Google Cloud, or Azure) take care of running it (cooking and serving). You're charged only for the time your code is actually running, not for having a server sit idle.

So, "serverless" is like running a restaurant without owning the kitchen – you write your code and run it when needed without dealing with server maintenance. It's a way to make things simpler and more cost-effective in the world of technology.
