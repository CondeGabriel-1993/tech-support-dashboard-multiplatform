# Estrutura dos Dados de Suporte Técnico

Este documento descreve a estrutura do arquivo CSV utilizado como fonte de dados para o projeto.

## Colunas do Dataset

| Nome da Coluna | Tipo | Descrição | Exemplo |
|----------------|------|-----------|---------|
| ticket_id | Inteiro | Identificador único do chamado | 1001 |
| data_abertura | Data | Data e hora da abertura do chamado | 2023-06-15 09:32:45 |
| cliente_id | Inteiro | Identificador único do cliente | 505 |
| cliente_nome | Texto | Nome do cliente | Empresa XYZ |
| tipo_problema | Texto | Categoria do problema | Hardware, Software, Rede, Acesso |
| prioridade | Texto | Nível de prioridade | Alta, Média, Baixa |
| status | Texto | Status atual do chamado | Aberto, Em Atendimento, Aguardando Cliente, Resolvido, Fechado |
| responsavel_id | Inteiro | ID do técnico responsável | 42 |
| responsavel_nome | Texto | Nome do técnico responsável | João Silva |
| descricao | Texto | Descrição do problema | "Computador não liga após queda de energia" |
| solucao | Texto | Descrição da solução (quando resolvido) | "Substituída a fonte de alimentação" |
| data_resolucao | Data | Data e hora da resolução (se resolvido) | 2023-06-16 14:20:18 |
| tempo_resolucao | Decimal | Tempo em horas para resolução | 28.8 |
| satisfacao_cliente | Inteiro | Avaliação do cliente (1-5) | 4 |
| departamento | Texto | Departamento do cliente | Financeiro, RH, Operações, Marketing |
| equipamento | Texto | Tipo de equipamento (se aplicável) | Desktop, Notebook, Impressora, Servidor |
| sistema_operacional | Texto | SO do equipamento (se aplicável) | Windows 10, macOS, Linux |
| versao_software | Texto | Versão do software (se aplicável) | v2.3.1 |
| recorrente | Booleano | Se é um problema recorrente | True, False |
| canal_abertura | Texto | Canal pelo qual o chamado foi aberto | Email, Telefone, Portal, App |

## Exemplo de Dados

ticket_id,data_abertura,cliente_id,cliente_nome,tipo_problema,prioridade,status,responsavel_id,responsavel_nome,descricao,solucao,data_resolucao,tempo_resolucao,satisfacao_cliente,departamento,equipamento,sistema_operacional,versao_software,recorrente,canal_abertura
1001,2023-06-15 09:32:45,505,Empresa XYZ,Hardware,Alta,Resolvido,42,João Silva,"Computador não liga após queda de energia","Substituída a fonte de alimentação",2023-06-16 14:20:18,28.8,4,Financeiro,Desktop,Windows 10,,False,Telefone
1002,2023-06-15 11:45:22,612,Empresa ABC,Software,Média,Resolvido,37,Maria Oliveira,"Erro ao abrir arquivos PDF","Reinstalado o software Adobe Reader",2023-06-15 15:20:00,3.6,5,RH,Notebook,Windows 11,v2.3.1,False,Email

## Geração de Dados Fictícios

Os dados utilizados neste projeto são completamente fictícios e foram gerados para fins de demonstração. Nenhuma informação real de clientes ou empresas foi utilizada.

## Considerações sobre os Dados

- O dataset contém aproximadamente Xmb de dados
- Abrange chamados de suporte técnico fictícios em um período de X meses
- Inclui diversos tipos de problemas e resoluções para permitir análises variadas
