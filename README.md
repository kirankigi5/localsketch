# LocalSketch

A peer-to-peer collaborative whiteboard, with its React/TypeScript frontend and WebRTC signaling setup in one repository.

Maintained by [Kiran Reddy Bhumireddy](https://github.com/kirankigi5).

## Components

| Directory | Purpose |
| --- | --- |
| frontend/ | React, TypeScript and Vite app with Yjs CRDTs, WebRTC synchronization and IndexedDB persistence |
| signaling-server/ | Package configuration that starts the y-webrtc signaling server |

## Run locally

Install dependencies and start signaling in one terminal:

```bash
cd signaling-server
npm ci
npm start
```

The signaling start command uses port 10000. In a second terminal, start the frontend from this repository's root:

```bash
cd frontend
npm ci
VITE_SIGNALING_URL=ws://localhost:10000 npm run dev
```

Open the address printed by Vite. Peers use the same room name to collaborate.

Build the frontend:

```bash
cd frontend
npm run build
```

For deployment, configure the frontend's VITE_SIGNALING_URL to the deployed signaling service and retain any required TURN configuration.
