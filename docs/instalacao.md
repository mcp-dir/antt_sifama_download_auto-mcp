# Instalação detalhada

ANTT SIFAMA: Download de Auto de Infração é um servidor MCP remoto. Aponte seu cliente pra `https://api.mcp.ai/p_antt_sifama_download_auto`. Snippets rápidos: [INSTALL.md](../INSTALL.md).

| Cliente | URL | Auth |
|---|---|---|
| Claude Desktop | `https://api.mcp.ai/p_antt_sifama_download_auto` | OAuth 2.1 ou agent-auth |
| Cursor | `https://api.mcp.ai/p_antt_sifama_download_auto` | OAuth 2.1 ou agent-auth |
| VS Code (Copilot) | `https://api.mcp.ai/p_antt_sifama_download_auto` | OAuth 2.1 ou agent-auth |

A config JSON é a mesma em todos: só a URL, sem headers.

## Desinstalar

Remova o bloco `mcpServers.antt_sifama_download_auto` (ou `servers.antt_sifama_download_auto` no VS Code) do config do cliente e reinicie.
