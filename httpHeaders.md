## HTTP Headers

- HTTP Headers play a curcial role in API design as they provide essential information between client and server regarding the data to be exchanged.

- Headers a part of request / response message, with type including Common, Uncommon, standard, Non-standard headers.

- They can define parameters such as content-type, authentication, response status, cookies and more.

- Headers are case-insensitive but the value are case sensetive.

### How HTTP Headers work

- HTTP headers communicate throughout the request / response cycle.

- The request and response flow:
  1. Client prepares the request:
     - The browser or application assembles an HTTP request with relevant headers that describe What it wants and What formats it can accept.

  2. Headers travel with request:
     - The headers accompany the request as it traverse the network to the server.

  3. Server process the headers:
     - The server examine the request headers to understand authentication, preferred formats, and other metadata.

  4. Server generates the response:
     - Based on the request headers and it's own logic, server creates a response with appropriate response headers.

  5. Client receives and process the response:
     - The client interpretes the response headers to determine how to handler the returned data, including cache, security policies, and content rendering.

### Types of HTTP headers

- HTTP headers fall into several categories based on their purpose and where they appear in the communication cycle:
  1. Request Headers:
     - Sent from the client to the server, containing information about the request, the client’s capabilities, and what the client expects in return.

  2. Response Headers:
     - Sent from the server to the client, providing metadata about the response, including how the client should handle the returned data.

  3. Representation Headers:
     - Describe the encoding, format, and other characteristics of the message body in both requests and responses.

  4. Payload Headers:
     - Contain information about the payload data, including content length, encoding, and range information for partial content delivery.

### Common HTTP request headers

1. Accept:
   - Defines which formats it prefers.

   Eg:
   `Accept: application/json , Accept: text/html`

2. User-Agent:
   - Identifies the web browser or client application making the request, which enables the server to tailor its response to the client's capablities.

   Eg:
   `User-Agent: postman / curl / browser`

3. Authorization:
   - This headers supports various authentication scheme including Bearer tokens, Basic auth, api-key

   Eg:
   `Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9...
Authorization: Basic dXNlcm5hbWU6cGFzc3dvcmQ=
Authorization: ApiKey sk_live_abc123xyz789`

4. Content-type:
   - Identifies the media type of the content in the request body.

   Eg: `Content-type: application/json`
   - Indicates the request body contains json data.

5. Cookie:
   - Cookie header to send previously stored cookies back to the server. The server uses these cookies to associate the request with a specific user or session.

   Eg:

   `Cookie: sessionId=abc123; userId=456; theme=dark`

6. Accept-Language:
   - Client preferred language for the response content

   Eg:

   `Accept-Language: en-US,en;q=0.9,es;q=0.8`

7. Referring:
   - The Referer header (note the historical misspelling) indicates the URL of the page that linked to the currently requested resource. This helps servers understand where traffic is coming from

   Eg:

   `Referer: https://www.example.com/previous-page`

8. If-Modified-Since:
   - The If-Modified-Since header enables conditional requests by asking the server to return the resource only if it has been modified after a specific date.

   Eg:

   `If-Modified-Since: Wed, 21 Oct 2023 07:28:00 GMT `

### Common HTTP response headers

1. Content-type:
   - Indicates the media type of the returned content

   - Eg: Content-Type: application/json; charset=utf-8,Content-Type: text/html; charset=UTF-8, Content-Type: image/png

2. Cache-Control:
   - Controls caching behaviour in the client's browser or intermediate caches.

   - It defines how the response can be cached, when it expires, how it will revalidated.

   Eg:

   ````
   Cache-Control: max-age=3600, public
   Cache-Control: no-cache, no-store, must-revalidate
   Cache-Control: private, max-age=0```
   ````

3. Server:
   - The Server header includes the name and version of the server software that generated the response.

   Eg:

   ```
   Server: Apache/2.4.10 (Unix)
   Server: nginx/1.21.0
   Server: Cloudflare
   ```

4. Set-Cookie:
   - The Set-Cookie header instructs the client to store a cookie with the specified name, value, and attributes, such as expiration, domain, path, and security flags.

   Eg:

   ```
   Set-Cookie: sessionId=abc123; Expires=Wed, 09 Jun 2024 10:18:14 GMT
   Set-Cookie: userId=456; HttpOnly; Secure; SameSite=Strict
   ```

5. Content-Length:
   - Header specifies the size of the response body in bytes.

   Eg: `Content-Length: 348`

6. Location:
   - Location Header is used in redirect responses (3xx status code) and indicates where the client should navigate next.

   Eg:

   ```
   Location: https://api.example.com/users/12345
   Location: /dashboard
   ```

7. ETag:
   - The ETag (Entity Tag) header provides a unique identifier for a specific version of a resource.

   Eg: `ETag: "33a64df551425fcc55e4d42a148795d9f25f89d4"`

8. Access-Control-Allow-Origin:
   - The Access-Control-Allow-Origin header specifies which origins can access the resource from a browser context.

   Eg:

   ```
   Access-Control-Allow-Origin: *
   Access-Control-Allow-Origin: https://www.example.com

   ```

9. Strict-Transport-Security:
   - The Strict-Transport-Security (HSTS) header tells browsers to only access the site using HTTPS, enhancing security by preventing downgrade attacks.

   Eg: `Strict-Transport-Security: max-age=31536000; includeSubDomains`

### Best practices for using HTTP headers

1. Keep headers concise:
   - Avoid unnecessary or redundant headers to reduce the size of both request / responses.

2. Leverage caching headers:
   - Use caching headers to reduce load on the server and imporve response time.

3. Prioritize Security:
   - Never include sensitive data such as passwords or API keys in plain-text headers. Always use HTTPS to encrypt header data in transit.

4. Safely handle Cross-Origin Resource Sharing (CORS):
   - Configure CORS carefully to prevent unauthorized access. Avoid using Access-Control-Allow-Origin: \* for authenticated endpoints.

5. Use appropriate compression:
   - Enable compression through the Accept-Encoding and Content-Encoding headers to reduce bandwidth usage.

6. Document your headers:
   - Document all expected request and response headers in your API documentation, and include example values and descriptions.
