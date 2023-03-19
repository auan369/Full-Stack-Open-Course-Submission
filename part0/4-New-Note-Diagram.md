Here is a simple flow chart:

```mermaid
sequenceDiagram;
    participant browser;
    participant server;

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_notes;
    activate server;
    browser-->>server: html document containing form information;
    deactivate server;

    browser->>server; GET https://studies.cs.helsinki.fi/exampleapp/notes;
    activate server;
    browser-->server: html document;
    deactivate server; 

    browser->>server; GET https://studies.cs.helsinki.fi/exampleapp/main.css;
    activate server;
    browser-->server: the css file;
    deactivate server; 
```