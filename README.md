# ETL Pipeline — Marketing Cloud Customer Journeys

## O que é esse projeto

Pipeline ETL (Extract, Transform, Load) para consolidação de múltiplas fontes de dados, aplicação de regras de negócio e preparação de bases para campanhas no Salesforce Marketing Cloud.

Projeto desenvolvido como **case study corporativo** durante estágio em dados, demonstrando habilidades de modelagem, tratamento e segmentação de dados em ambiente de produção.

## Contexto do Negócio

Uma campanha de renovação de contratos exigia consolidação de informações distribuídas em diferentes sistemas:
- Contratos ativos
- Dados de contato
- Responsáveis comerciais
- Gestoras
- Segmentação atacadista/varejista

O desafio: transformar essas informações em bases consistentes e prontas para uso no Salesforce Marketing Cloud.

## Arquitetura do Processo

EXTRACT → TRANSFORM → LOAD → Salesforce Marketing Cloud
↓          ↓          ↓
5 bases   Cruzamentos  2 bases
fonte    + Regras    finais

## Principais Etapas

### 1. Consolidação
Integração de 5 bases de dados em uma única fonte de verdade contendo: cliente, contrato, e-mail, CNPJ, responsável comercial.

### 2. Identificação de Analistas
Cruzamento (PROCX/XLOOKUP) com base de responsáveis comerciais para atribuição automática de consultores.

### 3. Auditoria e Validação
Aplicação de regras de negócio para:
- Identificação de gestoras
- Exclusão de clientes varejistas
- Confirmação de elegibilidade

### 4. Normalização de Contatos
Transformação de múltiplos e-mails em registros individuais para compatibilidade com Marketing Cloud.

## Regras de Negócio Implementadas

**Jornada dos Analistas:**
- Cliente possui responsável comercial identificado → Disparo_Analistas

**Jornada das Gestoras:**
- Cliente sem analista + Classificação atacadista + Vinculado a gestora → Disparo_Gestoras

## Desafios Resolvidos

- **Múltiplos destinatários:** Transformação de listas de e-mails em registros individuais
- **Duplicidade de registros:** Validação e identificação de comportamentos legítimos do sistema
- **Chave de relacionamento:** Análise comparativa (CNPJ vs. Razão Social) para determinar melhor método de cruzamento

## Tecnologias Utilizadas

- Microsoft Excel (PROCX, XLOOKUP, Validação de Dados)
- Salesforce Marketing Cloud
- AMPscript e HTML (templates)
- SharePoint e Microsoft Teams (documentação)

## Arquivos do Projeto

- `ETL_Pipeline_for_Marketing_Cloud_Customer_Journeys.pdf` — Documentação completa do case study
- `marketing_cloud_data_prep_case_ficticio_final.xlsx` — Arquivo com todas as abas do pipeline (dados fictícios)

## Dados

Todos os dados utilizados neste projeto são **fictícios** e foram criados exclusivamente para demonstração técnica.

Nenhuma informação confidencial ou pertencente a clientes reais foi incluída.

## Próximos Passos

Automação completa do pipeline utilizando:
- Python (Pandas)
- SQL
- Power Query
- Power Automate

## Competências Demonstradas

✅ Modelagem e arquitetura de dados  
✅ Tratamento e validação de dados  
✅ Implementação de regras de negócio  
✅ Segmentação de clientes  
✅ Integração com plataformas de marketing  
✅ Documentação técnica  
✅ Trabalho em ambiente corporativo real

