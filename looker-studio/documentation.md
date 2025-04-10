# Documentação: Implementação com Google Looker Studio

Este documento detalha o processo de criação do dashboard analítico interativo para o sistema de helpdesk, utilizando a plataforma Google Looker Studio (anteriormente Google Data Studio).

## Sumário

1.  [Configuração Inicial e Conexão de Dados](#1-configuração-inicial-e-conexão-de-dados)
2.  [Estrutura Multi-Páginas](#2-estrutura-multi-páginas)
3.  [Página 1: Incorporação do AppSheet](#3-página-1-incorporação-do-appsheet)
4.  [Página 2: Construção do Dashboard Principal (Gráficos e KPIs)](#4-página-2-construção-do-dashboard-principal-gráficos-e-kpis)
5.  [Página 3: Tabela Detalhada de Chamados](#5-página-3-tabela-detalhada-de-chamados)
6.  [Configuração de Filtros (Ex: KPI "Tickets em Aberto")](#6-configuração-de-filtros-ex-kpi-tickets-em-aberto)
7.  [Estilo e Layout](#7-estilo-e-layout)
8.  [Desafios e Soluções](#8-desafios-e-soluções)
9.  [Publicação e Compartilhamento (Link Público)](#9-publicação-e-compartilhamento-link-público)
10. [Limitações da Versão Gratuita](#10-limitações-da-versão-gratuita)
11. [Screenshots Relevantes](#11-screenshots-relevantes)

---

## 1. Configuração Inicial e Conexão de Dados

1.  **Acesso:** O processo iniciou acessando [lookerstudio.google.com](https://lookerstudio.google.com/) com a mesma conta Google utilizada para o AppSheet e Google Sheets.
2.  **Novo Relatório:** Um novo relatório em branco foi criado (`+ Criar` -> `Relatório`).
3.  **Fonte de Dados:** O conector **`Planilhas Google`** foi selecionado.
4.  **Autorização:** Permissão foi concedida para o Looker Studio acessar os dados do Google Sheets.
5.  **Seleção:** A planilha `chamados_helpdesk` e a aba `Chamados` foram selecionadas como fonte de dados principal. As opções "Usar primeira linha como cabeçalho" foram mantidas.
6.  **Adição:** A fonte de dados foi adicionada ao relatório.  

Tela de seleção da fonte de dados Google Sheets no Looker Studio.  
![Descrição do Screenshot 1](screenshots/nome_do_seu_screenshot_looker1.png)  



## 2. Estrutura Multi-Páginas

Para organizar o conteúdo e integrar o AppSheet, uma estrutura de múltiplas páginas foi adotada:

*   **Criação:** Novas páginas foram adicionadas usando a opção `Página` -> `Nova página` ou clicando no gerenciador de páginas na lateral (se visível).
*   **Renomeação:** Cada página foi renomeada para refletir seu conteúdo (ex: "Sistema", "Dashboard", "Tabela de Tickets") clicando no nome da página.  

Gerenciador de páginas mostrando as 3 páginas criadas.  
![Descrição do Screenshot 1](screenshots/nome_do_seu_screenshot_looker1.png)  


## 3. Página 1: Incorporação do AppSheet

O diferencial desta implementação foi incorporar o próprio aplicativo AppSheet funcional dentro do relatório Looker Studio:

1.  **Componente:** Na primeira página ("Sistema"), foi utilizado o componente `Incorporar URL` (URL embed), acessível pelo menu `Inserir` (Insert) -> `Incorporar URL`.
2.  **Configuração:** No campo `URL externa` (External URL) do componente, foi colado o **link de acesso via navegador (Browser Link)** do aplicativo AppSheet previamente criado.
    *   Link utilizado: `[COLAR O LINK APPSHEET AQUI]`
3.  **Resultado:** Permite que usuários visualizem e interajam com o aplicativo AppSheet (registrar, editar chamados) diretamente dentro do ambiente do Looker Studio.  

Configuração do componente 'Incorporar URL' com o link do AppSheet.  
![Descrição do Screenshot 1](screenshots/nome_do_seu_screenshot_looker1.png)  


## 4. Página 2: Construção do Dashboard Principal (Gráficos e KPIs)

A segunda página ("Dashboard") concentra as análises visuais principais, replicando e adaptando o que foi feito no Power BI:

*   **Gráficos Adicionados:** Utilizando o menu `Adicionar um gráfico`, foram incluídos:
    *   **Pizza/Rosca (Tickets por Status):** `Dimensão`: `Status`, `Métrica`: `Record Count` ou `Contagem distinta` de `IDChamado`.
    *   **Rosca/Barras (Tickets por Técnico):** `Dimensão`: `TecnicoResponsavel`, `Métrica`: `Record Count` / `Contagem distinta` ID. Ordenado por métrica.
    *   **Barras (Tickets por Categoria):** `Dimensão`: `Categoria`, `Métrica`: `Record Count` / `Contagem distinta` ID. Ordenado por métrica.
    *   **Barras (Tickets por Departamento):** `Dimensão`: `Departamento`, `Métrica`: `Record Count` / `Contagem distinta` ID. Ordenado por métrica.
    *   **Gráfico de Linha/Área (Tickets por Mês):** `Dimensão`: `DataAbertura` (agrupado por Ano/Mês), `Métrica`: `Record Count` / `Contagem distinta` ID.
*   **KPIs (Placares):** Utilizando o gráfico `Placar` (Scorecard):
    *   **Total de Tickets:** `Métrica`: `Record Count` ou `Contagem distinta` ID.
    *   **Tickets em Aberto:** `Métrica`: `Record Count` / `Contagem distinta` ID. **Filtro aplicado** (ver seção 6).  

Visão geral da página "Dashboard" com os gráficos e KPIs configurados.  
![Descrição do Screenshot 1](screenshots/nome_do_seu_screenshot_looker1.png)  


## 5. Página 3: Tabela Detalhada de Chamados

Para permitir consulta aos dados brutos, a terceira página ("Tabela de Tickets") contém:

*   **Componente:** Um gráfico do tipo **`Tabela` (Table)** foi adicionado (`Adicionar um gráfico` -> `Tabela`).
*   **Configuração:**
    *   **`Dimensão`:** Foram adicionadas todas as colunas relevantes para visualização (`IDChamado`, `DataAbertura`, `Solicitante`, `Status`, `DescricaoCurta`, etc.).
    *   **`Métrica`:** Nenhuma métrica agregada é necessária aqui, apenas as dimensões.
    *   **`Linhas por página`:** Ajustado para um número razoável (ex: 25 ou 50).
    *   **`Classificação`:** Permitido ao usuário ordenar clicando nos cabeçalhos ou definido um padrão (ex: `IDChamado` decrescente).  

Visão da página "Tabela de Tickets" mostrando a tabela configurada.  
![Descrição do Screenshot 1](screenshots/nome_do_seu_screenshot_looker1.png)  


## 6. Configuração de Filtros (Ex: KPI "Tickets em Aberto")

O KPI "Tickets em Aberto" exigiu um filtro específico para contar apenas os chamados não finalizados:

1.  **Seleção:** O gráfico `Placar` correspondente foi selecionado.
2.  **Adição de Filtro:** No painel `Gráfico` -> `Filtro`, clicou-se em `+ Adicionar um filtro`.
3.  **Configuração do Filtro (`Filtro Status Aberto`):**
    *   `Incluir`
    *   Campo: `Status`
    *   Condição: `Está em (lista)` (In)
    *   Valores: `"Aberto"`, `"Em Andamento"`, `"Aguardando Terceiro"`, `"Aguardando Usuário"` *(Ajuste conforme seus status exatos)*.
4.  **Aplicação:** O filtro foi salvo e aplicado exclusivamente a este placar.  

Janela de configuração do filtro "Filtro Status Aberto".  
![Descrição do Screenshot 1](screenshots/nome_do_seu_screenshot_looker1.png)  


## 7. Estilo e Layout

*   Um **tema escuro** pré-definido foi aplicado através do painel `Tema e layout` para dar uma aparência consistente ao relatório.
*   Títulos foram adicionados aos gráficos e páginas usando caixas de texto (`Inserir` -> `Texto`) ou as opções de formatação de cada gráfico na aba `Estilo`.
*   Os elementos foram redimensionados e posicionados para criar um layout organizado em cada página.  

## 8. Desafios e Soluções

| Desafio                                      | Solução                                                                                                                                |
| :------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------------------- |
| Incorporar AppSheet funcionalmente          | Identificar e utilizar o componente `Incorporar URL` corretamente, utilizando o link "Browser Link" do AppSheet.                        |
| Criar KPI Filtrado ("Tickets em Aberto")    | Entender a aplicação de filtros específicos a um único gráfico (Placar) em vez de filtros de relatório/página. Configurar a condição `In`. |
| Organização Multi-Páginas                    | Planejar o conteúdo de cada página e usar o gerenciador de páginas para navegação clara.                                                 |
| (Menor) Entender Dimensão vs. Métrica       | Compreender que "Dimensão" é o que categoriza/agrupa (texto, data) e "Métrica" é o que é medido/contado (número, contagem).              |

## 9. Publicação e Compartilhamento (Link Público)

O compartilhamento do relatório Looker Studio foi configurado para acesso público (somente visualização):

1.  Botão `Compartilhar` -> `Gerenciar acesso`.
2.  Opção alterada para **`Qualquer pessoa com o link pode ver`**.
3.  O link gerado foi copiado para uso externo (README principal).
4.  **Vantagem:** Este método permite visualização interativa do dashboard por qualquer pessoa com o link, sem exigir login e sem as restrições severas do Power BI gratuito.  

Janela de configuração de compartilhamento do Looker Studio.  
![Descrição do Screenshot 1](screenshots/nome_do_seu_screenshot_looker1.png)  


## 10. Limitações da Versão Gratuita

*   **Recursos Avançados:** Funções de modelagem de dados mais complexas (comparáveis ao Power Query avançado/DAX) são limitadas.
*   **Blending de Dados:** Pode haver limitações no número de fontes que podem ser combinadas.
*   **Performance:** Relatórios extremamente complexos com múltiplas fontes e milhões de linhas podem apresentar lentidão (não aplicável a este projeto).

*(Para a escala e complexidade deste projeto, o Looker Studio gratuito foi mais do que suficiente e ofereceu vantagens significativas no compartilhamento.)*

## 11. Screenshots Relevantes  

Demonstração do Dashboard e suas funcionalidades  
![Demonstração do Dashboard e suas funcionalidades](screenshots/nome_do_seu_screenshot_looker1.png)  

