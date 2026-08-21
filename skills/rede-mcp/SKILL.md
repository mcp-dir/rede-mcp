---
name: rede-mcp
description: Skill da REST API do Rede na MCP.AI: 4 endpoints em /api/rede. Vendas, recebíveis e extrato da sua conta na Rede (maquininha) por captura de sessão, com a sua autorização. Você informa o e-mail e a senha do Portal Rede e a plataforma entra na sua conta para ler os seus próprios dados, na mesma área que você usa no portal. Somente leitura: vendas e transações por período, agenda de recebíveis e extrato financeiro. Combina com o Banco MCP para conciliar maquininha e banco. Autentique com workspace API key (sk_live) gerada em app.mcp.ai/settings/api-keys. Use quando o usuário pedir algo coberto pelos endpoints.
---

# Rede — REST API skill

Você tem acesso à **Rede** REST API na MCP.AI.

> Vendas, recebíveis e extrato da sua conta na Rede (maquininha) por captura de sessão, com a sua autorização. Você informa o e-mail e a senha do Portal Rede e a plataforma entra na sua conta para ler os seus próprios dados, na mesma área que você usa no portal. Somente leitura: vendas e transações por período, agenda de recebíveis e extrato financeiro. Combina com o Banco MCP para conciliar maquininha e banco.

## Base URL

```
https://api.mcp.ai/api/rede
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
curl -X POST https://api.mcp.ai/api/rede/conta \
  -H "Authorization: Bearer sk_live_..." \
  -H "Content-Type: application/json" \
  -d '{}'
```

## Reportar problemas

Se um endpoint retornar erro, vazio ou dado inesperado, reporte (não desista calado): **POST /api/rede/report** com `{ "message": "...", "context"?: "...", "conversation"?: [...] }`. Isso notifica o time da MCP.AI.

## Endpoints (4)

#### `rede_conta`

Dados da conta no Portal Rede (perfil e ponto(s) de venda / PV). _(POST /api/rede/conta)_

#### `rede_extrato`

Extrato financeiro da conta Rede no período (movimentações, pagamentos, ajustes, débitos e chargebacks). _(POST /api/rede/extrato)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `start_date` | string | Não | Data inicial YYYY-MM-DD (padrão: 30 dias atrás). |
| `end_date` | string | Não | Data final YYYY-MM-DD (padrão: hoje). |

#### `rede_recebiveis_agenda`

Agenda de recebíveis da Rede no período (quando cada venda cai na conta; visão resumo, calendário ou diário). _(POST /api/rede/recebiveis/agenda)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `start_date` | string | Não | Data inicial YYYY-MM-DD (padrão: 30 dias atrás). |
| `end_date` | string | Não | Data final YYYY-MM-DD (padrão: hoje). |
| `visao` | string | Não | Visão da agenda (padrão: resumo). (resumo, calendario, diario) |

#### `rede_vendas_listar`

Lista as vendas/transações da conta Rede por período (crédito, débito e Pix; com status, tipo e valor), via a API interna do Portal Rede. _(POST /api/rede/vendas/listar)_

| Parâmetro | Tipo | Obrigatório | Descrição |
|---|---|---|---|
| `start_date` | string | Não | Data inicial YYYY-MM-DD (padrão: 30 dias atrás). |
| `end_date` | string | Não | Data final YYYY-MM-DD (padrão: hoje). |
| `status` | string | Não | Filtra por status da transação. |
| `page` | integer | Não |  |
| `size` | integer | Não |  |

---

Este MCP também funciona via **conexão MCP** (Claude / Cursor) em `https://api.mcp.ai/p_rede` — veja o [README](../../README.md). A skill acima é pra consumir a **REST API** direto (agente próprio / código).
