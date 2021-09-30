# RHS
### AKA Right Hoe's Shit
The Retarded HTTP Server - the most retarded implementation of HTTP server in C language ever seen.

## Implementation Steps, roughly
1. basic TCP sockets layer running (listen on port/ports, accept client connections and send/receive data)
2. implement a buffered reader for reading requests one line at a time (delimited by CRLF)
3. begining parser: parse out the method, the request version and the path
4. header parsing for the "Header: value" syntax (Don't forget unfolding folded headers.)
5. check the request method, content type and content size to determine how/if the body will be read (maybe limit only to GET request, maybe allow query string params at most)
6. implement decoding of content based on content type
7. Optional: if support of HTTP 1.1, implement things like "100 Continue", keep-alive, chunked transfer
8. Optional: add robustness/security measures like detecting incomplete requests, limiting max number of clients etc
