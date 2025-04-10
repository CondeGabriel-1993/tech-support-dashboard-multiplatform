# Screenshots e GIFs: Implementação Google AppSheet

Esta pasta contém os arquivos visuais (screenshots estáticos e GIFs animados) que documentam o processo de desenvolvimento e a funcionalidade do aplicativo de helpdesk criado com Google AppSheet, como parte do projeto `tech-support-dashboard-multiplatform`.

## Conteúdo

Abaixo está uma descrição dos principais arquivos visuais presentes nesta pasta:

**1. Configuração Inicial:**

*   `HelpdeskAPP_Inicio1.png`: Tela inicial do AppSheet para criação de um novo app.
*   `HelpdeskAPP_inicio2.png`: Seleção da fonte de dados (Google Sheets).
*   `HelpdeskAPP_inicio3.png`: Seleção da planilha específica (`chamados_helpdesk`) como base.
*   `HelpdeskAPP_inicio4.png`: Protótipo inicial gerado automaticamente pelo AppSheet.

**2. Configuração da Tabela (Data -> Columns):**

*   `HelpdeskAPP_Colunas.png`: Visão geral da configuração das colunas da tabela `Chamados`, mostrando os tipos de dados ajustados (Number, DateTime, Enum, etc.) e propriedades chave (Editable, Require).

**3. Lógica e Automação (Auto Compute):**

*   `HelpdeskAPP_formula_Initial_Dataabertura.png`: Detalhe da configuração do `INITIAL VALUE` para a coluna `DataAbertura` usando a fórmula `NOW()`.
*   `HelpdeskAPP_formula_Initial_IDchamado.png`: Detalhe da configuração do `INITIAL VALUE` para a coluna `IDChamado` usando a fórmula `(MAX(Chamados[IDChamado]) + 1)` para geração sequencial.

**4. Configuração da Interface (UX -> Views):**

*   `HelpdeskAPP_Config_Telas.gif`: GIF animado mostrando a configuração das diferentes Views do aplicativo (Lista tipo Deck, Formulário, Detalhes) e seus respectivos ajustes (Column order, Sort by, etc.).

**5. Configuração das Ações (Behavior -> Actions):**

*   `HelpdeskAPP_Config_Actions.gif`: GIF animado demonstrando a configuração das Actions `Iniciar Atendimento` e `Resolver Chamado`, incluindo os gatilhos, colunas alteradas e condições de exibição.

**6. Compartilhamento:**

*   `HelpdeskAPP_Compartilhar_links.png`: Tela mostrando as opções de compartilhamento do aplicativo finalizado (Browser Link, Install Link).

**7. Demonstração Funcional:**

*   `APPSheet_HelpDesk_APP_Desktop_Web.gif`: GIF demonstrando o fluxo de uso principal do aplicativo na interface Web/Desktop (navegação, criação de chamado).
*   `APPSheet_HelpDesk_APP_Mobile.gif`: GIF demonstrando o uso do aplicativo na interface Mobile, incluindo a utilização das Actions rápidas.

## Contexto

Para uma explicação detalhada de cada etapa e como estas imagens/GIFs se encaixam no processo completo de desenvolvimento do AppSheet, consulte o **[README principal da implementação AppSheet](google-appsheet/README.md)** (localizado na pasta pai `/google-appsheet/`).

Estes arquivos visuais servem como evidência e ilustração do processo de configuração e do resultado final do aplicativo.
