```mermaid
  participant browser
  participant server

  Note right of browser: User visits Single-page application
  browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/spa
  server-->>browser: HTTP status code 304 not modified
  Note right of browser: Browser receives html code and requests main.css and spa.js files
  browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/main.css
  server-->>browser: main.css
  browser->>server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/spa.js
  server-->>browser: spa.js
  Note right of browser: The browser executes the JavaScript code and because of this it sends a GET request to get the notes which the server returns in a data.json file
  browser->server: HTTP GET https://studies.cs.helsinki.fi/exampleapp/data.json
  server-->>browser: data.json

```
