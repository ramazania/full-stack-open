```mermaid

sequenceDiagram
    participant Browser
    participant Server

    Note right of Browser: User types a note and clicks the Save button

    Note right of Browser: The JavaScript code instantly adds the note to the visible list<br>without refreshing the page

    Browser->>Server: POST /new_note_spa with JSON data
    activate Server
    Note left of Server: Server stores the note and responds with confirmation
    Server-->>Browser: {"status": "ok", "saved": true}
    deactivate Server

    Note right of Browser: Browser receives the response and keeps showing the updated note list
