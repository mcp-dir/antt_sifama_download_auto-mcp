# Autenticação

ANTT SIFAMA: Download de Auto de Infração usa um único endpoint público (`https://api.mcp.ai/p_antt_sifama_download_auto`).

Dois fluxos, escolhidos automaticamente pelo cliente:

- **OAuth 2.1** (recomendado, cliente moderno) — browser abre na 1ª chamada, login via magic-link, token rotaciona sozinho, nunca passa pelo chat.
- **agent-auth** (cliente sem OAuth) — o agente expõe a tool `authenticate(token)`. Você abre `https://app.mcp.ai/agent-auth`, faz login, copia o JWT e cola no chat. ⚠️ o JWT passa pelo provedor LLM — rotacione periodicamente.

Config do cliente nos dois casos:
```json
{ "mcpServers": { "antt_sifama_download_auto": { "url": "https://api.mcp.ai/p_antt_sifama_download_auto" } } }
```
