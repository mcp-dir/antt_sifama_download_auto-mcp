---
name: antt_sifama_download_auto-mcp
description: Skill da REST API do ANTT SIFAMA: Download de Auto de Infração na MCP.AI: 1 endpoint em /api/antt_sifama_download_auto. ANTT SIFAMA: Download de Auto de Infração, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# ANTT SIFAMA: Download de Auto de Infração — REST API skill

Você tem acesso à **ANTT SIFAMA: Download de Auto de Infração** REST API na MCP.AI.

> ANTT SIFAMA: Download de Auto de Infração, consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/antt_sifama_download_auto
```

Todo endpoint é um **POST** na Base URL + o path abaixo. Os parâmetros vão no corpo JSON.

## Autenticação

Inclua em toda request:

```
Authorization: Bearer sk_live_...
Content-Type: application/json
```

> Gere sua chave em **https://app.mcp.ai/settings/api-keys** (workspace API key `sk_live_…`, não expira, revogável). Uma única chave serve pra todos os seus MCPs.

## Formato de resposta

```json
{ "ok": true, "tool": "<tool_id>", "result": <payload> }
```

## Exemplo cURL

```bash
curl -X POST https://api.mcp.ai/api/antt_sifama_download_auto/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"login_senha":"...","cnpj_representado":"...","auto_infracao":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/antt_sifama_download_auto/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `antt_sifama_download_auto_consultar`

ANTT SIFAMA: Download de Auto de Infração, consulta em fonte oficial. _(POST /api/antt_sifama_download_auto/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `login_cpf` | string | Não | Parâmetro de consulta "login_cpf". |
| `login_cnpj` | string | Não | Parâmetro de consulta "login_cnpj". |
| `login_senha` | string | Sim | Parâmetro de consulta "login_senha". |
| `cnpj_representado` | string | Sim | Parâmetro de consulta "cnpj_representado". |
| `auto_infracao` | string | Sim | Parâmetro de consulta "auto_infracao". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_antt_sifama_download_auto` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
