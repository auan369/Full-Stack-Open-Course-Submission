Here is a simple flow chart:

```mermaid
sequenceDiagram;
    participant browser;
    participant server;

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa;
    activate server;
    server-->>browser: HTML Document
    deactivate server; 
    

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css;
    activate server;
    server-->>browser: css file;
    deactivate server; 

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/spa.js;
    activate server;
    server-->>browser: the JS file;
    deactivate server;
    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js;
    activate server;
    server-->>browser: the JavaScript file;
    deactivate server; 
    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server


    Note left of browser: After the form is filled up and save button clicked...
    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    server-->>browser: [{"content":"salve","date":"2023-03-19T00:43:25.542Z"}, ... ]
    deactivate server

    Note right of browser: The browser executes the callback function that renders the notes

    
```