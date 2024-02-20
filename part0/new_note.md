sequenceDiagram
    participant browser
    participant server
    
    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa
    Payload: {”content":"Mureke on mureke","date":"2024-02-15T16:45:03.567Z"}
    activate server
    server-->>browser: HTTP OK 200, response body:  {"message": "note created"}
    deactivate server

   Note right of browser: The browser executes the callback function that renders the notes 
