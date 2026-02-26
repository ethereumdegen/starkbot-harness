# starkbot-harness

Claude Code plugin for commanding a Starkbot agent via the External Channel Gateway API.

## Quick Start

### 1. Add the marketplace

```
/plugin marketplace add ethereumdegen/starkbot-harness
```

### 2. Install the plugin

```
/plugin install starkbot-harness@starkbot-harness
```

### 3. Set environment variables

```bash
export STARK_URL="https://your-starkbot-instance.com"
export STARK_TOKEN="your-bearer-token"
```

### 4. Use it

```
/starkbot-harness:stark hello, what can you do?
```

Claude will also auto-invoke the Starkbot Gateway skill when interaction with your agent is contextually relevant.

## API Endpoints

| Method | Endpoint | Purpose |
|--------|----------|---------|
| POST | `/api/gateway/chat` | Send message, get full response |
| POST | `/api/gateway/chat/stream` | Send message, stream SSE |
| POST | `/api/gateway/sessions/new` | Create new session |
| GET | `/api/gateway/sessions` | List sessions |
| GET | `/api/gateway/sessions/{id}/messages` | Get message history |

## Environment Variables

| Variable | Required | Description |
|----------|----------|-------------|
| `STARK_URL` | Yes | Base URL of your Starkbot instance |
| `STARK_TOKEN` | Yes | Bearer token for API authentication |
| `STARK_SESSION` | No | Session ID for conversation persistence |

## Local Development

```bash
claude --plugin-dir ~/ai/starkbot-harness
```
