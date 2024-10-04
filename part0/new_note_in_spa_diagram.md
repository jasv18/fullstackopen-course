# Single page app diagram

```mermaid
sequenceDiagram
    participant browser
    participant server

    browser->>server: POST https://studies.cs.helsinki.fi/exampleapp/new_note_spa

    Note right of browser: The browser executes the onSubmit event callback function that renders and also sends the note

    activate server
    server-->>browser: HTTP status code 201 (Created)
    deactivate server

    Note right of browser: The server does not ask for redirect and the browser stays on the same page. The server response with json: {"message":"note created"}