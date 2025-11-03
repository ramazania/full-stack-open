```mermaid
sequenceDiagram
    participant Browser
    participant Server

    Browser->>Server: GET /spa
    activate Server
    Server-->>Browser: HTML file
    deactivate Server

    Browser->>Server: GET /main.css
    activate Server
    Server-->>Browser: CSS stylesheet
    deactivate Server

    Browser->>Server: GET /spa.js
    activate Server
    Server-->>Browser: JavaScript file
    deactivate Server

    Note right of Browser: Browser runs the JavaScript code that builds the page content dynamically

    Browser->>Server: GET /data.json
    activate Server
    Server-->>Browser: JSON array containing existing notes
    deactivate Server

    Note right of Browser: JavaScript processes the JSON and displays the notes without reloading the page
