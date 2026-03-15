# streampay-backend

**StreamPay** API backend — stream management, usage metering, and settlement services.

## Overview

Node.js + Express (TypeScript) service that will power the StreamPay API gateway: health checks, stream listing, and (later) metering and Stellar settlement integration.

## Prerequisites

- Node.js 18+
- npm (or yarn/pnpm)

## Setup for contributors

1. **Clone and enter the repo**
   ```bash
   git clone <repo-url>
   cd streampay-backend
   ```

2. **Install dependencies**
   ```bash
   npm install
   ```

3. **Verify setup**
   ```bash
   npm run build
   npm test
   ```

4. **Run locally**
   ```bash
   npm run dev    # dev with hot reload
   # or
   npm run build && npm start
   ```

API will be at `http://localhost:3001` (or `PORT` env). Try `GET /health` and `GET /api/streams`.

## Scripts

| Command        | Description              |
|----------------|--------------------------|
| `npm run build`| Compile TypeScript       |
| `npm start`    | Run production build     |
| `npm run dev`  | Run with ts-node-dev     |
| `npm test`     | Run Jest tests           |
| `npm run lint` | Run ESLint               |

## CI/CD

On every push/PR to `main`, GitHub Actions runs:

- Install: `npm ci`
- Build: `npm run build`
- Tests: `npm test`

Keep the default branch green before merging.

## Project structure

```
streampay-backend/
├── src/
│   ├── index.ts        # Express app and routes
│   └── health.test.ts  # API tests
├── package.json
├── tsconfig.json
├── jest.config.js
├── .github/workflows/ci.yml
└── README.md
```

## License

MIT
