# Nota sobre a Implementação com Microsoft Power Apps

## Status: Exploração Inicial - Não Concluído

Esta pasta foi originalmente destinada a conter a implementação de uma versão do aplicativo de helpdesk utilizando **Microsoft Power Apps**, como parte da exploração multi-plataforma deste projeto de portfólio.

## Obstáculo Encontrado: Barreiras de Licenciamento/Conta Gratuita

Durante a fase inicial de configuração e planejamento para o desenvolvimento com Power Apps, foi encontrada uma barreira significativa relacionada ao acesso a um ambiente de desenvolvimento adequado **sem custos** (free tier):

1.  **Programa de Desenvolvedores do Microsoft 365:** A tentativa de obter um sandbox gratuito através do Microsoft 365 Developer Program (que geralmente inclui licenças E5 com Power Apps) **não foi bem-sucedida**, com a plataforma indicando que a conta utilizada não se qualificava no momento.
2.  **Limitações de Contas Pessoais:** Utilizar uma conta Microsoft pessoal gratuita diretamente no Power Apps apresentava potenciais limitações significativas para este projeto, como:
    *   Necessidade de **conectores Premium** (pagos) para conectar de forma robusta a fontes de dados externas como Google Sheets.
    *   Restrições de **delegação** que poderiam impactar a performance e funcionalidade ao lidar com a base de dados.
    *   Dificuldades inerentes ao **compartilhamento** de um aplicativo funcional para demonstração pública em um portfólio.

## Decisão e Próximos Passos no Projeto

Diante dessas barreiras que impediam a criação de uma solução totalmente funcional e demonstrável dentro do requisito "free tier" do projeto, tomou-se a decisão de **não prosseguir com a implementação completa em Power Apps neste momento**.

O foco do desenvolvimento do aplicativo foi então direcionado para o **Google AppSheet**, que ofereceu um caminho viável e sem custos para atingir os objetivos funcionais com a base de dados no Google Sheets.

## Conteúdo Desta Pasta

Atualmente, esta pasta contém apenas este arquivo `README.md` documentando a razão pela qual a implementação do Power Apps não foi finalizada. Nenhum código ou aplicativo funcional está presente aqui. A experiência, no entanto, serviu como um aprendizado valioso sobre as realidades do licenciamento e dos planos gratuitos na Power Platform (detalhado na seção "Aprendizados e Reflexões" do [README principal do projeto](../../README.md)).
