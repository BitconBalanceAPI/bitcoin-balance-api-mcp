# Bitcoin Balance API — Open Plugins (MCP)

This folder follows the [Open Plugins](https://open-plugins.com/) layout: a plugin bundles metadata and MCP configuration in one place.

## Files

| File | Purpose |
|------|--------|
| [`.plugin/plugin.json`](.plugin/plugin.json) | Plugin manifest: name, version, links |
| [`.mcp.json`](.mcp.json) | Streamable HTTP MCP servers (mainnet) |

## Tools (remote MCP)

After you copy [`.mcp.json`](.mcp.json) into **`.cursor/mcp.json`** (or merge the `mcpServers` block) and set your API key, the agent can use:

- `get_address_balance` — confirmed balance (satoshis) for one address  
- `get_batch_balances` — multiple addresses (same limits as REST batch)  
- `get_utxo` — UTXO list for an address  

Authenticate with the **`X-API-Key`** header (same key as REST `?apikey=`).

## Quick setup (Cursor)

1. Get a key: [Get API key](https://api.bitcoin-balance-api.com/keys) (mainnet) or your testnet deployment.  
2. Copy or merge [`.mcp.json`](.mcp.json) into **`.cursor/mcp.json`**.  
3. Replace **`YOUR_API_KEY`** and remove the server you do not use if you only need one network.  
4. Reload Cursor.

## Docs

- MCP: [docs.bitcoin-balance-api.com — MCP](https://docs.bitcoin-balance-api.com/endpoints/mcp)  
- Swagger: [api.bitcoin-balance-api.com/docs](https://api.bitcoin-balance-api.com/docs)

## Self-host (Docker)

See the project [`README.md`](../README.md) for the `mcp` Compose service.
