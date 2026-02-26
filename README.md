# starkbot-harness

Claude Code plugin for commanding a Starkbot agent via the External Channel Gateway API.

## Setup

### 1. Set environment variables

```bash
export STARK_URL="http://localhost:3000"   # Your Starkbot instance URL
export STARK_TOKEN="your-bearer-token"     # API authentication token
export STARK_SESSION=""                     # Optional: session ID for persistence
```

### 2. Install the plugin

**Local development:**
```bash
claude --plugin-dir ~/ai/starkbot-harness
```

## Usage

### Slash command

```
/starkbot-harness:stark hello, what can you do?
```

### Auto-invocation

Claude will automatically use the Starkbot Gateway skill when interaction with a Starkbot agent is contextually relevant.

## API Endpoints

| Method | Endpoint | Purpose |
|--------|----------|---------|
| POST | `/api/gateway/chat` | Send message, get full response |
| POST | `/api/gateway/chat/stream` | Send message, stream SSE |
| POST | `/api/gateway/sessions/new` | Create new session |
| GET | `/api/gateway/sessions` | List sessions |
| GET | `/api/gateway/sessions/{id}/messages` | Get message history |
