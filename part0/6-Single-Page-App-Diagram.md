Here is a simple flow chart:

```mermaid
sequenceDiagram;
    participant browser;
    participant server;

    

    

    activate browser;
    Note right of browser: JS script runs once button is clicked; Data is taken from form input and added to internal notes array as a key, value pair; JS script causes document to update with updated list
    deactivate browser;



    
    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa;
    activate server;
    browser-->>server: Key Value pair of the new input, {"message":"note created"}
    deactivate server; 
    


    
```