# Rede

### Rede for Claude, ChatGPT and AI agents

Sales, receivables and statements for your Rede (card machine) account via session capture, with your authorization. You provide your Rede portal email and password and the platform logs into your account to read your own data, on the same area you use in the portal. Read-only: sales and transactions by period, receivables schedule and financial statement. Pairs with the Banco MCP to reconcile card machine and bank.

- 📊 **4 tools**
- 🔒 **Read-only**
- 💬 **Works with any MCP client**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Magic-link login (no password)**

[Portuguese version](README.md) · [Full docs (PT-BR)](docs/)

---

## One-click install

### Claude (Web and Desktop)

[➕ Open in Claude and connect](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

Manual: [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Add custom connector** → name `Rede`, URL `https://api.mcp.ai/p_rede`.

### Cursor

[➕ Install in Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=rede&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9yZWRlIn0=)

### VS Code (Copilot Chat)

[➕ Install in VS Code](vscode:mcp/install?name=rede&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_rede%22%7D)

### Any other MCP-over-HTTP client

```
https://api.mcp.ai/p_rede
```

---

## 4 tools

| Tool | Description |
|---|---|
| `rede_vendas_listar` | Lista as vendas/transações da conta Rede por período (crédito, débito e Pix; com status, tipo e valor), via a API interna do Portal Rede. |
| `rede_recebiveis_agenda` | Agenda de recebíveis da Rede no período (quando cada venda cai na conta; visão resumo, calendário ou diário). |
| `rede_extrato` | Extrato financeiro da conta Rede no período (movimentações, pagamentos, ajustes, débitos e chargebacks). |
| `rede_conta` | Dados da conta no Portal Rede (perfil e ponto(s) de venda / PV). |

---

## Pricing

See [docs/precos.md](docs/precos.md) (PT-BR).

---

## License

MIT — see [LICENSE](LICENSE). The MCP server at `api.mcp.ai/p_rede` is proprietary (hosted); this repo (manifests, docs, skills) is MIT.
