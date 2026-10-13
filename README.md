# ORCA

ORCA is an omnichannel customer-retention demo for Nigerian telecom operators.
It combines a FastAPI service for mentions, classification, queues, and
intelligence with a Next.js dashboard. The default MTN case study starts with
seeded demonstration data; external integrations are optional.

## Run locally

Start the API with Python 3 and the dependencies in `backend/requirements.txt`:

```sh
cd backend
cp .env.example .env
./run.sh
```

Open `http://localhost:8000/docs` for the API schema or call
`http://localhost:8000/api/health`. The default SQLite database is generated
locally at `backend/orca.db` and populated with demo records on startup.

In another terminal, start the dashboard with Node.js and npm:

```sh
cd frontend
npm ci
npm run dev
```

Open `http://localhost:3000`. Set `NEXT_PUBLIC_API_BASE` if the API is not on
`http://localhost:8000`.

## Configuration and scope

`backend/.env.example` lists the API settings. With no `APIFY_TOKEN`, the API
uses seeded demo mentions. With no `ANTHROPIC_API_KEY`, classification uses a
deterministic mock. The sample database and generated files are kept out of
version control; no real customer data is required to explore the UI.

This is a case study and development demo. Review privacy, authentication,
rate limits, and provider permissions before connecting live customer data.
