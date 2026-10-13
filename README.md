# From The Other Side 👻

A lightweight, full-stack web application for logging, reading, and streaming paranormal sightings. Built entirely with vanilla Node.js to demonstrate core backend principles—including custom routing, static asset serving, asynchronous file I/O, input sanitization, and Server-Sent Events (SSE)—without third-party backend frameworks like Express.

---

## Features

- **Vanilla Node.js HTTP Server**: Custom request routing using the native `http` module.
- **Static File Serving**: Delivers HTML, CSS, JavaScript, and image assets across cross-platform environments using native `fs/promises` and `path` modules.
- **RESTful API**: Supports `GET` and `POST` methods under `/api` for reading and submitting sightings.
- **Data Persistence**: Stores and retrieves sighting records dynamically in a flat JSON file (`data.json`).
- **Input Sanitization**: Cleans and validates incoming user-submitted content to protect against Cross-Site Scripting (XSS) vulnerabilities.
- **Server-Sent Events (SSE)**: Streams real-time story notifications and news updates to connected clients using the standard event-stream protocol.

---

## Project Structure

```text
├── data/
│   └── data.json              # Persistent JSON storage for sightings
├── handlers/
│   └── routeHandlers.js       # Core route handlers (GET, POST, SSE)
├── public/
│   ├── images/                # Static assets (logos, background images)
│   ├── 404.html               # Fallback error page
│   ├── index.css              # Main application styling
│   ├── index.html             # Homepage
│   ├── index.js               # Frontend script for index
│   ├── sightings.html         # Sighting feed view
│   ├── upload-sighting.html   # Report submission form
│   └── upload-sighting.js     # Form handler & API post logic
├── utils/
│   ├── addNewSighting.js      # Appends new entries to data.json
│   ├── getContentType.js      # Resolves MIME types for static assets
│   ├── getData.js             # Reads and parses data.json
│   ├── parseJSONBody.js       # Collects and parses incoming request streams
│   ├── sanitizeInput.js       # Sanitizes user input to prevent XSS
│   ├── sendResponse.js        # Helper for sending HTTP status & headers
│   └── serveStatic.js         # Static file reader and dispatcher
├── package.json
└── server.js                  # Application entry point & request router
