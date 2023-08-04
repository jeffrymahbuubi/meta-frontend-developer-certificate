## HTTP examples

This reading explores the contents of HTTP requests and responses in more depth.

### Request Line

Every HTTP request begins with the request line. This consists of the HTTP method, the requested resource and the HTTP protocol version. For instance:
<code>GET /home.html HTTP/1.1</code>
In this example, GET is the HTTP method, /home.html is the resource requested and HTTP 1.1 is the protocol used.

### HTTP Methods

HTTP methods indicate the action that the client wishes to perform on the web server resource. Common HTTP methods are:

<li><strong>GET</strong>: The client requests a resource on the web server.
</li><li><strong>POST</strong>: The client submits data to a resource on the web server.
</li><li><strong>PUT</strong>: The client replaces a resource on the web server.
</li><li><strong>DELETE</strong>: The client deletes a resource on the web server.</li>

### HTTP Request Headers

After the request line, the HTTP headers are followed by a line break. There are various possibilities when including an HTTP header in the HTTP request. A header is a case-insensitive name followed by a colon (:) and then followed by a value. Common headers are:

```makefile
Host: example.com
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.9; rv:50.0) Gecko/20100101 Firefox/50.0
Accept: */*
Accept-Language: en
Content-type: text/json
```

The <strong>Host</strong> header specifies the host of the server and indicates where the resource is requested from. The <strong>User-Agent</strong> header informs the web server of the application that is making the request. It often includes the operating system (Windows, Mac, Linux), version and application vendor. The <strong>Accept</strong> header informs the web server what type of content the client will accept as the response. The <strong>Accept-Language</strong> header indicates the language and optionally the locale that the client prefers. The <strong>Content-type</strong> header indicates the type of content being transmitted in the request body.

### HTTP Request Body

HTTP requests can optionally include a request body. A request body is often included when using the HTTP POST and PUT methods to transmit data.

```bash
POST /users HTTP/1.1
Host: example.com

{
"key1":"value1",
"key2":"value2",
"array1":["value3","value4"]
}
```

```bash
PUT /users/1 HTTP/1.1
Host: example.com
Content-type: text/json

{"key1":"value1"}
```

### HTTP Responses

When the web server is finished processing the HTTP request, it will send back an HTTP response. The first line of the response is the status line. This line shows the client if the request was successful or if an error occurred. For example:

<code>HTTP/1.1 200 OK</code>

The line begins with the HTTP protocol version, followed by the status code and a reason phrase. The reason phrase is a textual representation of the status code.

### HTTP Status Codes

The first digit of an HTTP status code indicates the category of the response: Information, Successful, Redirection, Client Error or Server Error. The common status codes you'll encounter for each category are:

<li><strong>1XX Informational</strong><ul><li>100: Continue</li>
<li>101: Switching Protocols</li></ul></li><li><strong>2XX Successful</strong><ul><li>200: OK</li><li>201: Created</li><li>202: Accepted</li><li>204: No Content</li></ul></li><li><strong>3XX Redirection</strong><ul><li>301: Moved Permanently</li><li>302: Found</li></ul></li><li><strong>4XX Client Error</strong><ul><li>400: Bad Request</li><li>401: Unauthorized</li><li>403: Forbidden</li><li>404: Not Found</li><li>405: Method Not Allowed</li></ul></li><li><strong>5XX Server Error</strong><ul><li>500: Internal Server Error</li><li>502: Bad Gateway</li><li>503: Service Unavailable</li></ul></li>

### HTTP Response Headers

Following the status line, there are optional HTTP response headers followed by a line break. Similar to the request headers, there are many possible HTTP headers that can be included in the HTTP response. Common response headers are:

```yaml
Date: Fri, 11 Feb 2022 15:00:00 GMT+2
Server: Apache/2.2.14 (Linux)
Content-Length: 84
Content-Type: text/html
```

The <strong>Date</strong> header specifies the date and time the HTTP response was generated. The <strong>Server</strong> header describes the web server software used to generate the response. The <strong>Content-Length</strong> header describes the length of the response. The <strong>Content-Type</strong> header describes the media type of the resource returned (e.g. HTML document, image, video).

### HTTP Response Body

Following the HTTP response headers is the HTTP response body. This is the main content of the HTTP response and it can contain images, video, HTML documents and other media types.

```html
HTTP/1.1 200 OK Date: Fri, 11 Feb 2022 15:00:00 GMT+2 Server: Apache/2.2.14
(Linux) Content-Length: 84 Content-Type: text/html

<html>
  <head>
    <title>Test</title>
  </head>
  <body>
    Test HTML page.
  </body>
</html>
```
