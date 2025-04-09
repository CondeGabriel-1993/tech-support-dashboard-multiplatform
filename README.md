# Sistema de Helpdesk Simplificado com AppSheet e Power BI

Este repositório documenta a criação de um sistema funcional de suporte técnico (helpdesk) como um projeto de portfólio. O objetivo foi explorar ferramentas No-Code/Low-Code e de Business Intelligence para construir uma solução completa, desde o registro do chamado até a análise de dados, utilizando recursos gratuitos ou de free tier.

**Nota:** A intenção inicial era comparar implementações em múltiplas plataformas (incluindo Power Apps e Looker Studio), porém, devido a barreiras encontradas (detalhadas na seção de Aprendizados), o foco foi consolidado nas ferramentas Google AppSheet e Microsoft Power BI.


## 📊 Visão Geral da Solução Implementada

O projeto consiste em duas partes principais, utilizando um conjunto de dados fictícios (~1000 chamados) gerado via ChatGPT e armazenado no Google Sheets:

1.  **Aplicativo de Registro e Gestão (Google AppSheet):**
    *   Permite registrar novos chamados de suporte.
    *   Visualiza chamados existentes (lista e detalhes).
    *   Implementa ações rápidas para atualizar o status dos chamados (ex: Iniciar Atendimento, Resolver).
    *   Geração automática de ID sequencial para novos chamados.
2.  **Dashboard Analítico (Microsoft Power BI):**
    *   Conecta-se diretamente ao Google Sheets.
    *   Apresenta métricas chave (KPIs) como total de tickets, tickets em aberto.
    *   Visualiza a distribuição de chamados por status, técnico, categoria e departamento.
    *   Mostra a tendência de abertura de chamados ao longo do tempo.


## 🛠️ Tecnologias Utilizadas:

*   **Frontend/App:** Google AppSheet (Plano Gratuito)
*   **Backend/Base de Dados:** Google Sheets (Conta Pessoal Gratuita)
*   **Dashboarding:** Microsoft Power BI Desktop (Gratuito)
*   **Geração de Dados Iniciais:** ChatGPT (Modelo GPT-3.5/4)
*   **Formato de Dados Intermediário:** CSV (para importação inicial)
*   **Controle de Versão/Documentação:** Git / GitHub
  

## 🎥 Demonstração Visual (GIFs)

Como a publicação online gratuita das ferramentas possui limitações (especialmente Power BI para contas pessoais), a funcionalidade é demonstrada através dos GIFs abaixo:

**1. Fluxo no App (Google AppSheet):**

*   **Navegação e Criação de Chamado (Desktop/Web):**
    `![AppSheet Demo - Desktop](link_para_seu_gif_appsheet_desktop.gif)`
*   **Navegação e Ações (Mobile):**
    `![AppSheet Demo - Mobile](link_para_seu_gif_appsheet_mobile.gif)`

**2. Interação com o Dashboard (Power BI):**

*   **Visão Geral e Filtros:**
    `![Power BI Demo](link_para_seu_gif_powerbi.gif)`

    
## 📂 Estrutura do Repositório

- **/data**: Contém os dados brutos e processados
- **/power-bi**: Implementação em Power BI com documentação
- **/looker-studio**: Implementação em Looker Studio com documentação
- **/google-appsheet**: Implementação em Google AppSheet com documentação

## 📝 Documentação Detalhada

**A documentação passo-a-passo, incluindo configurações chave, fórmulas utilizadas (como a de ID sequencial no AppSheet) e screenshots do processo de desenvolvimento, encontra-se nos arquivos README.md dentro das respectivas pastas:**

*   **`/google-appsheet/README.md`**
*   **`/power-bi/README.md`**

## 📊 Comparação entre Plataformas

| Plataforma | Prós | Contras | Melhor para |
|------------|------|---------|-------------|
| Power BI | [a ser preenchido] | [a ser preenchido] | [a ser preenchido] |
| Looker Studio | [a ser preenchido] | [a ser preenchido] | [a ser preenchido] |
| Google AppSheet | [a ser preenchido] | [a ser preenchido] | [a ser preenchido] |

## 🔄 Processo de Desenvolvimento (Resumo da Jornada Real)

1.  **Definição do Escopo e Geração de Dados:** Planejamento inicial do sistema de helpdesk e criação da base de dados fictícia em CSV via ChatGPT.
2.  **Configuração da Base:** Importação dos dados para o Google Sheets.
3.  **Tentativa com Power Apps:** Exploração inicial da plataforma e encontro da barreira de licenciamento/conta gratuita para o caso de uso. **Decisão de pivotar.**
4.  **Desenvolvimento do App:** Criação e configuração completa do aplicativo no Google AppSheet (conexão, views, formulário, colunas virtuais, ID automático, actions).
5.  **Desenvolvimento do Dashboard:** Conexão do Power BI Desktop ao Google Sheets, criação dos visuais (gráficos, KPIs) e formatação básica.
6.  **Criação da Demonstração:** Geração de GIFs para ilustrar o uso do App e a interatividade do Dashboard.
7.  **Documentação:** Criação e detalhamento da estrutura do repositório e dos arquivos README.
## 📚 Aprendizados e Reflexões

*   **A Realidade dos Free Tiers:** O principal obstáculo foi a limitação inesperada no acesso ao ambiente de desenvolvimento do Power Apps com contas pessoais/gratuitas não vinculadas a organizações ou estudantes. Isso reforça a importância de verificar *cuidadosamente* as limitações de licenciamento e uso gratuito antes de se comprometer totalmente com uma ferramenta.
*   **Agilidade do Google AppSheet:** Para criar um CRUD (Create, Read, Update, Delete) funcional e com lógicas básicas (como o ID sequencial e as actions de status) conectado ao Google Sheets, o AppSheet se mostrou extremamente rápido e eficiente, exigindo pouca ou nenhuma codificação tradicional. Ideal para prototipagem rápida ou apps internos simples.
*   **Poder vs. Complexidade (Power BI):** O Power BI Desktop oferece uma gama vasta de opções de visualização e análise, mesmo na versão gratuita. A conexão com o Google Sheets foi direta. A curva de aprendizado para gráficos básicos é suave, mas explorar todo o potencial (DAX, Power Query avançado) exige mais dedicação. A limitação na publicação gratuita para contas pessoais é um ponto negativo significativo para portfólios.
*   **Adaptação é Chave:** A necessidade de abandonar a implementação planejada do Power Apps e focar no AppSheet demonstrou a importância de ser flexível e encontrar soluções alternativas diante de imprevistos técnicos ou de licenciamento.


## 📞 Contato

[Seus dados de contato]
