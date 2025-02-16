
## Setup

To setup the stockbroker, install dependencies from the root of the monorepo:

```bash
yarn install
```

This will install all dependencies required by both the frontend and backend projects. You can also run shared commands from the root of the project:

```bash
yarn format

yarn build
```

## Environment variables

### Backend

The backend requires Financial Datasets AI, Tavily and OpenAI API keys to run. Sign up here:

- Financial Datasets AI: https://financialdatasets.ai/
- Tavily: https://tavily.com/
- OpenAI: https://platform.openai.com/signup

Once you have your API keys, create a `.env` file in the [`./backend`](`./backend`) directory and add the following:

```bash
FINANCIAL_DATASETS_API_KEY=YOUR_API_KEY
TAVILY_API_KEY=YOUR_API_KEY
OPENAI_API_KEY=YOUR_API_KEY
```

### Frontend

The frontend requires the production, or local deployment of your agent, along with a LangSmith API key (if calling the production endpoint), and finally the name of the agent to interact with (in this case `stockbroker`).

For local development, you can find the API endpoint in the bottom left of LangGraph Studio, which defaults to `http://localhost:51497`. You can find the production URL in the deployment page of your LangGraph cloud deployment.

Then, set the variables in a `.env` file inside [`./frontend`](./frontend):

```bash
# Only required for production deployments
# LANGCHAIN_API_KEY=YOUR_API_KEY
LANGGRAPH_API_URL=http://localhost:51497
NEXT_PUBLIC_API_URL=http://localhost:3000/api # Or your production URL + /api
NEXT_PUBLIC_LANGGRAPH_GRAPH_ID=stockbroker
```

## LangGraph Config

The LangGraph configuration file for the stockbroker project is located inside [`./backend/langgraph.json`](./backend/langgraph.json). This file defines the stockbroker graph implemented in the project: `stockbroker`.
