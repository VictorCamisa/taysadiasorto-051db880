# Remix of Esthetic Flow

Desenvolva um sistema completo de Gestão Financeira + Estoque para uma clínica estética.
Não existe integração com CRM nesta fase.
O sistema deve ser 100% funcional, completo e sem omissões.
O objetivo é substituir uma planilha complexa de fluxo de caixa e criar um painel profissional.
1. OBJETIVO DO SISTEMA
Criar um sistema financeiro robusto e completo, integrado ao controle de estoque e ficha técnica de tratamentos.
O sistema deve permitir registrar entradas e saídas, controlar custos, calcular margem real, gerir contas a pagar, acompanhar estoque e gerar relatórios gerenciais como DRE, margem por tratamento, previsão de retorno de insumos e visão financeira consolidada.
2. MÓDULOS DO SISTEMA
O sistema deve conter obrigatoriamente:
Cadastros Base
Diário de Caixa (Lançamentos)
Contas a Pagar
Estoque & Compras
Ficha Técnica de Tratamentos
Contas Financeiras
Relatórios Financeiros
DRE Automatizada
Alertas internos de inconsistência
Dashboard geral
3. CADASTROS BASE
Criar páginas/telas para cadastro de:
3.1. Categorias de Despesa
Categoria Sintética (macro)
Categoria Analítica (subcategoria)
Tipo: Fixa / Variável / Impostos / Estruturais / Comissões / Marketing / Serviços
Status: ativa/inativa
3.2. Formas de Pagamento
Dinheiro
PIX
Débito
Crédito
Transferência
Parcelado (registrar nº de parcelas)
Cheque
Permuta (opcional)
3.3. Origem / Procedência de Receita
Lead – Consultório
Indicação – X
Recorrente
Outras origens editáveis
3.4. Contas Financeiras
Nome da conta
Tipo (Caixa físico, conta bancária, cartão, conta sócio)
Saldo inicial
Status
3.5. Fornecedores
Nome
CNPJ/CPF
Telefone
Observações
4. TRATAMENTOS & FICHA TÉCNICA
Criar cadastro completo com:
Nome do tratamento
Grupo (Ex.: Injetável, Limpeza, Bioestimulador etc.)
Preço de venda padrão
Itens da ficha técnica (lista dinâmica):
Produto de estoque
Quantidade usada por procedimento
Custo unitário (puxar do estoque)
Custo total automático
Margem bruta automática
Margem de contribuição (%)
Status: ativo/inativo
Regra:
Toda vez que um tratamento for lançado no financeiro, o sistema deve baixar automaticamente os insumos do estoque.
5. ESTOQUE & COMPRAS
5.1 Cadastro de produtos
Campos obrigatórios:
Nome do produto
Categoria (Ácido, Toxina, Bioestimulador, Consumível etc.)
Unidade de medida
Fornecedor padrão
Custo médio (calculado via compras)
Estoque atual
Estoque mínimo
Status
Lote / validade (opcional mas incluir suporte)
5.2 Compras (Entrada de Estoque)
Fornecedor
Nº da NF
Data da compra
Itens (produto, quantidade, valor unitário, valor total)
Forma de pagamento
Vincular automaticamente a um título em Contas a Pagar
Regras:
Atualizar custo médio dos produtos
Atualizar saldo do estoque
Registrar automaticamente o impacto no contas a pagar
6. CONTAS A PAGAR
Campos:
Fornecedor
Tipo (estoque, serviço, imposto, estrutural etc.)
Valor
Vencimento
Forma de pagamento
Status: Aberto / Pago / Atrasado / Cancelado
Data de pagamento
Conta financeira usada
Observações
Regra essencial:
Quando um título for marcado como pago, criar automaticamente um lançamento no diário de caixa como despesa.
7. DIÁRIO DE CAIXA (LANÇAMENTOS)
Uma única tabela unificada.
Nada de “aba por mês”.
Campos:
Data
Tipo: Receita / Despesa / Transferência / Ajuste
Cliente (texto simples)
Fornecedor (se despesa)
Procedência (se receita)
Tratamento (se receita)
Quantidade
Valor de entrada
Valor de saída
Forma de pagamento
Conta financeira
Categoria Sintética
Categoria Analítica
Observações
Custo do tratamento (puxar ficha técnica automaticamente)
Margem automática por lançamento
Regra:
Se usuário lançar um tratamento, sistema baixa estoque + calcula custo + calcula margem.
Se lançar despesa manual, vincular categoria e conta.
Transferências devem mover saldo entre contas sem afetar o DRE.
8. RELATÓRIOS FINANCEIROS
Criar telas completas para:
8.1 Relatório de Receitas
Por tratamento
Por origem/procedência
Por forma de pagamento
Por conta financeira
Por período
Ticket médio mensal
8.2 Relatório de Despesas
Por categoria sintética
Por subcategoria analítica
Por fornecedor
Por conta
Por período
8.3 Margem por Tratamento
Total faturado
Custo real (estoque consumido)
Margem bruta
Margem líquida
% de contribuição
8.4 Relatório de Estoque
Produtos no limite
Lotes próximos à validade
Previsão de reposição (com base no consumo médio)
9. DRE COMPLETO (GERADO AUTOMATICAMENTE)
Criar o relatório DRE com:
Receita total
Receita por tratamento
CMV (Custo dos materiais usados)
Custos variáveis (taxas, comissões, parcelamentos)
Margem de contribuição
Despesas fixas
Despesas variáveis
Resultado operacional
Lucro líquido
Regra:
Tudo deve ser calculado a partir dos lançamentos e fichas técnicas.
10. DASHBOARD PRINCIPAL
Incluir KPIs:
Receita do mês
Despesas do mês
Lucro líquido
Top 5 tratamentos por faturamento
Top 5 tratamentos por margem
% de pagamentos por forma
Saldo por conta financeira
Gastos por categoria
Produtos abaixo do mínimo
Alertas importantes
11. LÓGICAS INTERNAS E REGRAS DO SISTEMA
Baixa automática de estoque ao lançar tratamento.
Cálculo de custo real via ficha técnica.
Lançamento automático no caixa ao pagar título.
Atualização automática de custo médio quando entra novo estoque.
Prevenção de saldo negativo (alerta).
Aviso de estoque baixo.
Aviso de contas vencendo.
Controle integral por data e período.
Proibição de edição do saldo manual — tudo calculado.
Tudo auditável: histórico de alterações.
12. INTERFACE E USABILIDADE
Interfaces limpas, com filtros avançados
Gráficos e cards em todos os relatórios
Possibilidade de exportar tudo (CSV/Excel)
Trabalhar com listas, modais e tabelas editáveis
Painéis separados por módulo

Foque em uma identidade visual limpa, moderna. Desenvolva o UX e UI de maneira extremamente competente. Não falhe.

This project was built with [Lovable](https://lovable.dev).

**Live app**: https://taysadiasorto.lovable.app

## Build with Lovable

Continue developing this project in the [Lovable editor](https://lovable.dev/projects/994d72ea-f1e9-46dd-af21-3be1bea2fd35).

- **Ship faster**: describe what you want to build and Lovable handles the code.
- **Stay in sync**: every change made in Lovable is committed straight to this repository.
- **Full ownership**: this code is yours. Push to `main` on GitHub and your changes sync back into Lovable, ready for your next prompt.

## Development

Prefer working locally? You need Node.js and npm — [install with nvm](https://github.com/nvm-sh/nvm#installing-and-updating).

```sh
git clone <this-repository-url>
cd <repository-name>
npm i
npm run dev
```
