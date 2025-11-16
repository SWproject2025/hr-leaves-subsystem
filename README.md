# HR Leaves Subsystem

Lightweight README for local development.

## Prerequisites
- Node.js (v14+ recommended)
- npm

## Setup
1. Install dependencies:
    ```
    npm install
    ```

2. Create a `.env` in the project root (example):
    ```
    PORT=3000
    SWAGGER_PATH=/api-docs
    ```

    The app defaults to port 3000 when `PORT` is not set.

## Running (development)
Start the dev server:
```
npm run start:dev
```
This command should run the application in watch/development mode. Swagger UI is exposed on port 3000 — by default visit:
```
http://localhost:3000/api-docs
```
(Confirm the exact Swagger path in your app; adjust `SWAGGER_PATH` if needed.)

## Running (production)
Build and run (example):
```
npm run build
npm run start
```

## Useful scripts (example entries for package.json)
Add or verify these scripts in `package.json`:
```json
{
  "scripts": {
     "start:dev": "NODE_ENV=development node ./dist/index.js --watch",
     "build": "tsc -p tsconfig.json",
     "start": "node ./dist/index.js"
  }
}
```
Adjust the script commands to match your project setup (Nest/Express/etc.).

## Troubleshooting
- If Swagger does not appear, confirm:
  - Server is running and listening on port 3000.
  - The Swagger route (`/api-docs`) matches your app configuration.
  - Any required environment variables or DB connections are provided.

## Notes
- Keep `PORT=3000` in root `.env` or set it in your shell to ensure the app and Swagger run on port 3000.
- Update the README with any framework-specific run/build instructions if needed.