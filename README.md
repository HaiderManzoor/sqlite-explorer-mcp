# sqlite-explorer-mcp

A Model Context Protocol (MCP) server that lets AI agents browse, query, and explore SQLite databases.

![npm version](https://img.shields.io/npm/v/sqlite-explorer-mcp)
![license](https://img.shields.io/npm/l/sqlite-explorer-mcp)

## Features

- **List databases** — Automatically discover `.db`, `.sqlite`, and `.sqlite3` files in your project
- **Run queries** — Execute read-only SQL queries with formatted results
- **Browse schemas** — View table structures, column types, and indexes
- **Preview data** — Quickly inspect table contents with formatted output

## Installation

```bash
npm install -g sqlite-explorer-mcp
```

Or clone and install locally:

```bash
git clone https://github.com/user/sqlite-explorer-mcp.git
cd sqlite-explorer-mcp
npm install
```

## MCP Configuration

### Claude Code

Add to your `.mcp.json`:

```json
{
  "mcpServers": {
    "sqlite-explorer": {
      "type": "stdio",
      "command": "node",
      "args": ["/path/to/sqlite-explorer-mcp/index.js"]
    }
  }
}
```

### Cursor

Add to your MCP settings:

```json
{
  "sqlite-explorer": {
    "command": "node",
    "args": ["/path/to/sqlite-explorer-mcp/index.js"]
  }
}
```

## Available Tools

### `list_databases`

Discover SQLite databases in a directory.

```
list_databases({ "directory": "/path/to/project" })
```

### `query_database`

Execute a read-only SQL query.

```
query_database({ "db_path": "./data/app.db", "query": "SELECT * FROM users LIMIT 10" })
```

### `schema`

View the schema of a database.

```
schema({ "db_path": "./data/app.db" })
```

### `table_data`

Preview rows from a table.

```
table_data({ "db_path": "./data/app.db", "table_name": "users" })
```

## Requirements

- Node.js 18+
- `better-sqlite3` (installed automatically)

## License

MIT
