```mermaid

sequenceDiagram
    participant Browser
    participant Server

    Note right of Browser: User writes text and submits the form

    Browser->>Server: POST /new_note with form data
    activate Server
    Note left of Server: Server saves the note and sends a redirect
    Server-->>Browser: 302 Redirect to /notes
    deactivate Server

    Note right of Browser: Browser reloads the page after redirect

    Browser->>Server: GET /notes
    Server-->>Browser: HTML document
    Browser->>Server: GET /main.css
    Server-->>Browser: CSS file
    Browser->>Server: GET /main.js
    Server-->>Browser: JavaScript file

    Note right of Browser: Browser executes JS and requests JSON data
    Browser->>Server: GET /data.json
    Server-->>Browser: Updated JSON with new note
    Note right of Browser: Browser renders the list again
