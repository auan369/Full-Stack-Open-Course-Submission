Here is a simple flow chart:

```mermaid
sequenceDiagram;
    participant browser;
    participant server;

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_notes;
    activate server;
    browser-->>server: html document containing form information;

    browser->>server; GET https://studies.cs.helsinki.fi/exampleapp/notes;
    browser-->server: html document;
    deactivate server; 

    browser->>server; GET https://studies.cs.helsinki.fi/exampleapp/main.css;
    browser-->server: the css file;
    deactivate server; 
```