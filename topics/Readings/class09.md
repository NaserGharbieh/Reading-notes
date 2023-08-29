# Class 09 reading: 
# HTTP Request Lifecycle and HTTP Request Basics.
## Five Steps in the HTTP Request Lifecycle:

1. **Local Processing:** The browser extracts necessary information from the URL, such as protocol, host, port, resource path, and query strings. It resolves the hostname to an IP address using various caches.

2. **Resolve an IP:** The browser sends a DNS request to resolve the IP address associated with the hostname. This involves querying DNS servers and potentially iterating through multiple servers to obtain the IP.

3. **Establish a TCP Connection:** The client establishes a TCP connection with the server using a three-way handshake (SYN, SYN-ACK, and ACK messages). This ensures reliable and ordered data transmission.

4. **Send an HTTP Request:** With the TCP connection in place, the client sends an HTTP request to the server. The request includes a request line, headers, and an optional body.

5. **Tearing Down and Cleaning Up:** After receiving the HTTP response, the client sends a FIN packet to initiate the termination of the TCP connection. A four-way handshake takes place to confirm the termination, involving FIN and ACK messages exchanged between both parties.

## Two Things the Client Needs Before Making an HTTP Request:

1. **IP Address:** The client needs the IP address of the server it wants to communicate with. This is obtained through the DNS resolution process, which converts the hostname to an IP address.

2. **TCP Connection:** Before sending the actual HTTP request, the client establishes a TCP connection with the server using a three-way handshake. This connection provides a reliable communication channel for the request and response exchange.

## Four-Way Handshake and Its Purpose:

The four-way handshake is a process used to gracefully terminate a TCP connection between a client and a server. It ensures that both parties agree to close the connection and that all remaining data has been transmitted. The steps involved in the four-way handshake are as follows:

1. **Client Sends FIN:** The client sends a FIN (Finish) packet to the server to indicate that it has finished sending data.

2. **Server Sends ACK:** The server acknowledges the FIN packet with an ACK (Acknowledgment) packet. This acknowledges that the server received the client's request to terminate the connection.

3. **Server Sends FIN:** Once the server has completed sending its data, it sends its own FIN packet to the client.

4. **Client Sends ACK:** The client responds with an ACK packet to acknowledge the server's FIN packet. This confirms that both parties agree to close the connection.

The four-way handshake ensures that both the client and server have transmitted all data and are ready to terminate the connection. It helps prevent data loss and ensures a reliable closure of the connection.

## HTTP Request Basics

### Redirects in HTTP Requests

- **True or False: When making an HTTP request, you MUST follow any redirect returned by the request.**
  - **Answer:** False.
  - **Explanation:** Following redirects is not mandatory in an HTTP request. Redirects are indicated by HTTP status codes 301 (Moved Permanently) and 302 (Found). Whether you follow redirects or not depends on your application's requirements and behavior. You can control whether to follow redirects using the `setInstanceFollowRedirects()` method or globally using `HttpUrlConnection.setFollowRedirects()`.

### Java Class for HTTP Requests

- **Which built-in Java class can be used to perform an HTTP request?**
  - **Answer:** The `HttpUrlConnection` class.
  - **Explanation:** The `HttpUrlConnection` class is a built-in Java class that allows you to perform basic HTTP requests without the need for additional libraries. It's part of the `java.net` package and provides methods to create, configure, and send HTTP requests.

### HTTP Status Codes

- **What HTTP status codes represent a successful response? A redirect? A client error?**

    - Successful Response: HTTP status codes in the range of 200 to 299 represent successful responses. For example, status code 200 (OK) indicates a successful request.
    - Redirect: HTTP status codes 301 (Moved Permanently) and 302 (Found) typically represent redirects. These codes indicate that the requested resource has been moved to a different location.
    - Client Error: HTTP status codes in the range of 400 to 499 represent client errors. For example, status code 404 (Not Found) indicates that the requested resource could not be found on the server.
