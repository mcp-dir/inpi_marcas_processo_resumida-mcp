---
name: inpi_marcas_processo_resumida-mcp
description: Skill da REST API do INPI: Processo de Registro de Marca (Resumida) na MCP.AI: 1 endpoint em /api/inpi_marcas_processo_resumida. INPI: Processo de Registro de Marca (Resumida), consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# INPI: Processo de Registro de Marca (Resumida) — REST API skill

Você tem acesso à **INPI: Processo de Registro de Marca (Resumida)** REST API na MCP.AI.

> INPI: Processo de Registro de Marca (Resumida), consulta em fonte oficial. Hospedado pela plataforma, sem credenciais da plataforma, pague por consulta com crédito pré-pago.

## Base URL

```
https://api.mcp.ai/api/inpi_marcas_processo_resumida
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
curl -X POST https://api.mcp.ai/api/inpi_marcas_processo_resumida/consultar \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{"numero_processo":"..."}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/inpi_marcas_processo_resumida/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (1)

#### `inpi_marcas_processo_resumida_consultar`

INPI: Processo de Registro de Marca (Resumida), consulta em fonte oficial. _(POST /api/inpi_marcas_processo_resumida/consultar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `numero_processo` | string | Sim | Parâmetro de consulta "numero_processo". |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_inpi_marcas_processo_resumida` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
