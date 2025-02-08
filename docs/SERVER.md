## Server

- use express
- use cors
- use helmet

- install npm packages in project root `./package.json`
- should be implemented typescript in `./server/index.ts`
- add changes to typescript config `./tsconfig.node.json`

- add GET `/*` as the last endpoint which sends the file `./dist/index.html`

- add a router at `/api` with an endpoint for each of the following:
  - GET /api/index - returns a welcome message in html

- start server using `tsx`
- in `npm run server` script add `npm run build` before

- add server test, that the server is running, use `vitest` and `supertest`