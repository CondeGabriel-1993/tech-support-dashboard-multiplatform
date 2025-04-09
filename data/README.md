# Dados do Projeto de Helpdesk

Esta pasta armazena o conjunto de dados brutos utilizado como base para o projeto de demonstração do sistema de helpdesk.

## Origem e Fluxo dos Dados

1.  **Geração:** Os dados são **inteiramente fictícios** e foram gerados utilizando o **ChatGPT (modelo GPT-3.5/4)**, com um prompt para criar aproximadamente 1000 registros de chamados de suporte em formato CSV.
2.  **Armazenamento Inicial:** O arquivo CSV bruto resultante dessa geração está localizado na subpasta `/raw` deste diretório.
3.  **Base de Dados Central:** Este arquivo CSV serviu como fonte inicial para popular uma planilha **Google Sheets**. Esta planilha funcionou como a **base de dados central e única**, acessada diretamente pelas três aplicações desenvolvidas:
    *   Google AppSheet (para leitura e escrita)
    *   Google Looker Studio (para leitura e análise)
    *   Microsoft Power BI (para leitura e análise)
4.  **Não há dados processados ou transformados armazenados neste repositório.** Todas as transformações ou cálculos específicos foram feitos dentro das próprias ferramentas de BI ou na lógica do AppSheet.

## Estrutura da Pasta

*   `/raw`: Contém o arquivo CSV original (`chamados_helpdesk.csv`) com os dados fictícios gerados.

## Estrutura dos Dados (Colunas no CSV / Google Sheets)

A tabela abaixo descreve as colunas presentes no conjunto de dados:

| Coluna             | Tipo de Dados (Esperado) | Descrição                                        | Exemplo Fictício     |
| :----------------- | :----------------------- | :----------------------------------------------- | :------------------- |
| `IDChamado`        | Número                   | Identificador único numérico do chamado.          | `1001`               |
| `DataAbertura`     | Data/Hora                | Data e hora em que o chamado foi aberto.          | `07/04/2025 19:14`   |
| `Solicitante`      | Texto                    | Nome fictício do usuário que abriu o chamado.   | `Maria da Penha`     |
| `Departamento`     | Texto                    | Departamento fictício do solicitante.            | `TI`                 |
| `Categoria`        | Texto                    | Tipo de problema relatado.                       | `Falha em equipamento`|
| `DescricaoCurta`   | Texto                    | Breve descrição do problema.                     | `Impressora não funciona`|
| `Urgencia`         | Texto (Enum)             | Nível de urgência do chamado (`Baixa`, `Média`, `Alta`, `Crítica`). | `Média`              |
| `Status`           | Texto (Enum)             | Situação atual do chamado (`Aberto`, `Em Andamento`, `Resolvido`, etc.). | `Em Andamento`       |
| `TecnicoResponsavel`| Texto (Enum)            | Técnico (fictício) responsável pelo atendimento. | `Gabriel`            |
| `DataFechamento`   | Data/Hora (Opcional)     | Data e hora em que o chamado foi resolvido/fechado (preenchido apenas para status finais). | `07/04/2025 19:07`   |

## 🤖 Prompt Utilizado para Geração de Dados via ChatGPT

Para garantir transparência e demonstrar o processo de criação dos dados fictícios, segue abaixo o prompt utilizado no ChatGPT (modelo GPT-4 - Free tier) para gerar o arquivo CSV inicial:

Aja como um gerador de dados simulados para um sistema de chamados de helpdesk. Quero que você crie 1000 linhas de dados fictícios em formato CSV, utilizando ponto e vírgula (;) como separador. As colunas devem ser EXATAMENTE estas e nesta ordem: 

IDChamado;DataAbertura;Solicitante;Departamento;Categoria;DescricaoCurta;Urgencia;Status;TecnicoResponsavel;DataFechamento

Instruções Adicionais:
- Gere IDs sequenciais ou no formato HD-001, HD-002, etc.
- Use datas de abertura variadas nos últimos 6 meses (formato DD/MM/AAAA HH:MM) e em horário comercial.
- Crie nomes de solicitantes e departamentos plausíveis.
- Distribua bem as Categorias, Urgências e Status (inclua chamados ainda abertos ou em andamento).
- Para TecnicoResponsavel, use principalmente 'Gabriel' e 'Guilherme', com alguns como 'Paulo'.
- A coluna DataFechamento (formato DD/MM/AAAA HH:MM) SÓ deve ser preenchida para chamados com Status 'Resolvido' ou 'Fechado', e deve ser sempre posterior à DataAbertura, e horário comercial. Para os demais status, deixe esta coluna vazia.
- Certifique-se de que o resultado seja APENAS o CSV, sem introduções ou explicações adicionais.

## Observação Importante

Reiterando: **Todos os dados são sintéticos e não representam informações reais de qualquer pessoa ou organização.** Foram criados exclusivamente para fins de demonstração técnica neste portfólio.
