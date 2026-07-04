# Controle Financeiro Oficina Mecânica

**Versão:** v1.0 | **Data:** 2026-07-04T13:49:59.285Z

## Descrição
Planilha para controle das finanças, estoque e vendas da oficina mecânica.

## Prompt Original
```
REGRA 1: Todas as colunas DEVEM ter 'example' preenchido com dado fictício e realista. REGRA 2: Colunas de cálculo (Saldo, Total, Montante) DEVEM ser tipo 'formula' com 'formula' em inglês Excel (=SUM, =FV, =IF). REGRA 3: Colunas categóricas DEVEM ser tipo 'dropdown' com 'dropdownValues' de ao menos 3 opções. CRITICAL SPATIAL AWARENESS RULE: Before writing any Excel 'formula', you MUST mentally map the columns you are creating to Excel letters (Column 1=A, Column 2=B, Column 3=C, etc.). (1) When generating a mathematical formula or VLOOKUP, ensure you are referencing the correct cell letter based on your mental map — do not multiply text columns. (2) NEVER reference a column inside its own formula (e.g. if Total is Column G, do not put G inside the SUM — this creates a fatal Circular Reference). (3) CRITICAL: If a column's type is NOT 'formula', DO NOT include a 'formula' property in the JSON at all — never send null, 'null', empty string or undefined for 'formula'. Only formula-type columns may have the 'formula' key. Baseado nas especificações estritas do JSON a seguir, construa a arquitetura de banco de dados e planilhas: {"empresa":"Oficina mecânica","objetivo":"Controlar finanças","funcionarios":"2-5","modulos":["Estoque","Fluxo de Caixa","Faturamento","Vendas","Despesas"],"configuracoes":{"dashboard":true,"graficos":true,"financeiro":true,"estoque":true},"observacoes":null}
```

## Abas

### Estoque
Gerenciar o estoque de peças e produtos da oficina.

| Coluna | Tipo | Fórmula |
|--------|------|--------|
| ID da Peça | number | - |
| Nome da Peça | string | - |
| Quantidade | number | - |
| Preço Unitário | currency | - |
| Total em Estoque | formula | =C2*D2 |

### Fluxo de Caixa
Controle de entradas e saídas de caixa da oficina.

| Coluna | Tipo | Fórmula |
|--------|------|--------|
| Data | date | - |
| Descrição | string | - |
| Entrada | currency | - |
| Saída | currency | - |
| Saldo | formula | =C2-D2 |

### Faturamento
Registra todas as vendas realizadas pela oficina.

| Coluna | Tipo | Fórmula |
|--------|------|--------|
| Data da Venda | date | - |
| Cliente | string | - |
| Valor da Venda | currency | - |
| Forma de Pagamento | dropdown | - |

### Despesas
Controle de despesas da oficina.

| Coluna | Tipo | Fórmula |
|--------|------|--------|
| Data da Despesa | date | - |
| Descrição da Despesa | string | - |
| Valor da Despesa | currency | - |

### Painel de Indicadores
Análise de KPIs essenciais da oficina.

| Coluna | Tipo | Fórmula |
|--------|------|--------|
| Indicador | string | - |
| Valor Consolidado | formula | =SUM('Faturamento'!C:C) |
| Meta | currency | - |
| Variação | formula | =B2-C2 |
| Status | dropdown | - |
