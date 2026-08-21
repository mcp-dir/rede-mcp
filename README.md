# Rede

### Rede para Claude, ChatGPT e agentes de IA

Vendas, recebíveis e extrato da sua conta na Rede (maquininha) por captura de sessão, com a sua autorização. Você informa o e-mail e a senha do Portal Rede e a plataforma entra na sua conta para ler os seus próprios dados, na mesma área que você usa no portal. Somente leitura: vendas e transações por período, agenda de recebíveis e extrato financeiro. Combina com o Banco MCP para conciliar maquininha e banco.

- 📊 **4 ferramentas**
- 🔒 **Somente leitura**
- 💬 **Funciona com qualquer cliente MCP**: Claude Desktop, Cursor, VS Code, Cline, Continue
- 🔑 **Login via magic-link (sem senha)**

[English version](README.en.md) · [Documentação completa](docs/) · [Skill pra agentes](skills/)

---

## Instalar em 1 clique

### Claude (Web e Desktop)

A Anthropic unificou a instalação de MCPs em `claude.ai/customize/connectors`. **O mesmo link serve pra Claude Web e Claude Desktop** (basta estar logado):

[➕ Abrir no Claude e conectar](https://claude.ai/new?modal=add-custom-connector#settings/customize-connectors)

**Manual** (se o deeplink não abrir): [claude.ai/customize/connectors](https://claude.ai/customize/connectors?surface=cowork) → **+** → **Adicionar conector personalizado** → cole **Nome** `Rede` e **URL** `https://api.mcp.ai/p_rede`.

### Cursor

[➕ Instalar Rede no Cursor](cursor://anysphere.cursor-deeplink/mcp/install?name=rede&config=eyJ1cmwiOiJodHRwczovL2FwaS5tY3AuYWkvcF9yZWRlIn0=)

### VS Code (Copilot Chat)

[➕ Instalar Rede no VS Code](vscode:mcp/install?name=rede&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Fapi.mcp.ai%2Fp_rede%22%7D)

### ChatGPT, Manus, OpenClaw e mais 40+ clientes

Funciona em qualquer cliente MCP que suporte **MCP over HTTP**. A URL do servidor é sempre:

```
https://api.mcp.ai/p_rede
```

Detalhes por cliente: [INSTALL.md](INSTALL.md).

---

## Exemplos de uso

```
Minhas vendas na Rede dos últimos 7 dias
Qual é minha agenda de recebíveis na Rede?
Mostra o extrato da minha conta Rede neste mês
```

---

## 4 ferramentas disponíveis

| Tool | Descrição |
|---|---|
| `rede_vendas_listar` | Lista as vendas/transações da conta Rede por período (crédito, débito e Pix; com status, tipo e valor), via a API interna do Portal Rede. |
| `rede_recebiveis_agenda` | Agenda de recebíveis da Rede no período (quando cada venda cai na conta; visão resumo, calendário ou diário). |
| `rede_extrato` | Extrato financeiro da conta Rede no período (movimentações, pagamentos, ajustes, débitos e chargebacks). |
| `rede_conta` | Dados da conta no Portal Rede (perfil e ponto(s) de venda / PV). |

Detalhe de cada tool: [docs/ferramentas.md](docs/ferramentas.md)

---

## Preços

Veja [docs/precos.md](docs/precos.md).

---

## Privacidade & LGPD

- **Somente leitura**, nenhuma ferramenta altera dados na origem.
- **Sub-processadores**: Rede, o LLM host que você escolher (Claude, ChatGPT, Cursor, agente próprio). Lista completa em [docs/privacidade-lgpd.md](docs/privacidade-lgpd.md).
- Os dados retornados pelas tools são enviados ao **LLM host que você escolher**, sub-processador fora do nosso controle. Recomendamos planos com opt-out de treinamento.

---

## Perguntas frequentes

**O servidor é open source?**
O servidor é proprietário (hosted). Este repositório é o wrapper público com manifestos, docs e skills — tudo MIT.

**Posso usar com agente próprio (não Claude/Cursor)?**
Sim — qualquer cliente que suporte MCP over HTTP. URL: `https://api.mcp.ai/p_rede`.


---

## Suporte

- 📧 [rede@mcp.ai](mailto:rede@mcp.ai)
- 🐛 [GitHub Issues](https://github.com/mcp-dir/rede-mcp/issues)
- 📄 [docs/](docs/)

---

## Licença

MIT — veja [LICENSE](LICENSE). O servidor MCP em `api.mcp.ai/p_rede` é proprietário (hosted); este repositório (manifestos, docs, skills) é MIT.
