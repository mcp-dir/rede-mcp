# Ferramentas

Rede expõe 4 ferramentas (todas somente leitura).

### 1. `rede_vendas_listar`
**Input**: `start_date` (opcional), `end_date` (opcional), `status` (opcional), `page` (opcional), `size` (opcional)

Lista as vendas/transações da conta Rede por período (crédito, débito e Pix; com status, tipo e valor), via a API interna do Portal Rede.

### 2. `rede_recebiveis_agenda`
**Input**: `start_date` (opcional), `end_date` (opcional), `visao` (opcional)

Agenda de recebíveis da Rede no período (quando cada venda cai na conta; visão resumo, calendário ou diário).

### 3. `rede_extrato`
**Input**: `start_date` (opcional), `end_date` (opcional)

Extrato financeiro da conta Rede no período (movimentações, pagamentos, ajustes, débitos e chargebacks).

### 4. `rede_conta`
**Input**: nenhum input

Dados da conta no Portal Rede (perfil e ponto(s) de venda / PV).

## Prompts de exemplo

```
Minhas vendas na Rede dos últimos 7 dias
Qual é minha agenda de recebíveis na Rede?
Mostra o extrato da minha conta Rede neste mês
```
