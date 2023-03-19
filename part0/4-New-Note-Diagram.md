Here is a simple flow chart:

```mermaid
sequenceDiagram;
    participant browser;
    participant server;

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_notes;
    browser-->>server: html document containing form data;
    activate server;
    server-->>browser: status code 302(URL redirect)
    deactivate server;
    Note right of browser: The browser sends html document with the form data to the server. 
    Note right of browser: Server responds with status code 302, asks the browser to do a new HTTP GET request to the address defined in the header's Location (/notes).

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes;
    activate server;
    server-->>browser: html document;
    deactivate server; 

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css;
    activate server;
    server-->>browser: the css file;
    deactivate server;

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js;
    activate server;
    server-->>browser: the JavaScript file;
    deactivate server; 
    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{"content":"salve","date":"2023-03-19T00:43:25.542Z"}, ... ]
    deactivate server

    Note right of browser: The browser executes the callback function that renders the notes

    
```