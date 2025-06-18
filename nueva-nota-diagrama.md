# fullstackopen-diagrams

```

sequenceDiagram
    participant browser
    participant server

    Note right of browser: The user types a note into the text field and clicks the "Save" button.

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note
    activate server
    Note left of server: The server processes the new note (e.g., saves it to a database).
    server-->>browser: 302 Found (Redirect to /exampleapp/notes)
    deactivate server

    Note right of browser: The browser follows the redirect, reloading the notes page.

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/notes
    activate server
    server-->>browser: HTML document (updated with the new note)
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.css
    activate server
    server-->>browser: the css file
    deactivate server

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/main.js
    activate server
    server-->>browser: the JavaScript file
    deactivate server

    Note right of browser: The browser starts executing the JavaScript code that fetches the JSON from the server.

    browser->>server: GET https://studies.cs.helsinki.fi/exampleapp/data.json
    activate server
    Note left of server: The server retrieves all notes, including the newly added one.
    server-->>browser: [{ "content": "HTML is easy", "date": "2023-1-1" }, ..., { "content": "Nueva nota del usuario", "date": "2024-06-18" }]
    deactivate server

    Note right of browser: The browser executes the callback function that renders all notes, including the new one.


```
