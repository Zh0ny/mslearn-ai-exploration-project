# Exploração do Azure AI Studio e IA Generativa
DESAFIO DE PROJETO DO BOOTCAMP DA DIO - DECOLATECH2025
## Visão Geral

Este projeto documenta a jornada de aprendizado através do Azure AI Studio, explorando suas funcionalidades principais, a implantação de modelos de linguagem grande (LLMs), a interação com IA Generativa e a configuração de filtros de conteúdo para garantir o uso responsável da IA. A experiência foi baseada nos seguintes laboratórios do Microsoft Learn:

1.  [Explore the Azure AI Studio](https://microsoftlearning.github.io/mslearn-ai-studio/Instructions/01-Explore-ai-studio.html)
2.  [Explore content filters in Azure AI Studio](https://microsoftlearning.github.io/mslearn-ai-studio/Instructions/06-Explore-content-filters.html)
3.  [Explore generative AI with Azure OpenAI Service (Similar concepts explored via AI Studio/Copilot)](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/12-generative-ai.html)

## Objetivos

*   Familiarizar-se com a interface e os componentes do Azure AI Studio.
*   Aprender a criar um projeto e implantar modelos de IA pré-treinados (como o GPT-4o-mini).
*   Experimentar a interação com modelos de IA generativa no Playground de Chat.
*   Compreender e configurar os filtros de conteúdo para moderação e segurança.
*   Testar a eficácia dos filtros de conteúdo contra prompts inadequados.
*   Explorar outras capacidades de IA, como tradução e interação com ferramentas como o Microsoft Copilot.

## Experiência e Descobertas (Guiado pelas Imagens)

A jornada começou com a exploração inicial do Azure AI Studio.

1.  **Criação e Visão Geral do Projeto:**
    *   Foi criado um projeto no Azure AI Studio.
    *   A interface inicial apresentou um tour guiado (Imagem 2), destacando áreas chave como Catálogo de Modelos, Playgrounds, Serviços de IA e Ativos do Projeto (`My assets`).

    ![Visão Geral do AI Studio](image_2.png) _(Referência: Imagem 2)_

2.  **Implantação de um Modelo (GPT-4o-mini):**
    *   O próximo passo foi implantar um modelo. O `gpt-4o-mini` foi selecionado no catálogo.
    *   Durante a implantação (Imagem 7), foi configurada a versão do modelo (`2024-07-18`), o local do recurso (`East US 2`), e habilitadas as atualizações automáticas. Os limites de taxa de tokens por minuto (TPM) e solicitações por minuto (RPM) foram definidos (neste caso, 200k TPM e 1k RPM inicialmente, com um novo recurso a ser criado).

    ![Implantação do gpt-4o-mini](image_7.png) _(Referência: Imagem 7)_

    *   Após a implantação, as configurações (Imagem 1) mostram o modelo ativo, o tipo de implantação (`Global Standard`), o Serviço OpenAI do Azure conectado, e os limites de cota ajustados (100k TPM / 1k RPM). O filtro de conteúdo `DefaultV2` foi aplicado.

    ![Atualização da Implantação](image_1.png) _(Referência: Imagem 1)_

3.  **Experimentação no Playground de Chat:**
    *   Com o modelo implantado (`gpt-4o-mini: version 2024-07-18`), o Playground de Chat foi utilizado para interagir com a IA (Imagem 3).
    *   Foi possível definir um cenário ou instruções de sistema para guiar o comportamento do assistente de IA. A interface mostra o histórico de chats e a área para inserir prompts.

    ![Playground de Chat - Configuração Inicial](image_3.png) _(Referência: Imagem 3)_

4.  **Configuração e Teste dos Filtros de Conteúdo:**
    *   A seção "Proteção + segurança" foi explorada para entender e configurar os filtros de conteúdo (Imagem 4).
    *   Os filtros padrão (`DefaultV2`) foram revisados, mostrando categorias como Violência, Ódio, Sexual e Auto-mutilação (Self-harm), com ações definidas como "Anotar e bloquear" (Annotate and block) para texto e imagem. Escudos de prompt (Prompt shields) também estavam disponíveis.

    ![Configuração de Filtros de Conteúdo](image_4.png) _(Referência: Imagem 4)_

    *   A eficácia dos filtros foi testada no Playground de Chat com prompts que violavam as políticas de conteúdo:
        *   Um prompt sobre planejamento de atividades ilegais foi bloqueado por Violência (médio) (Imagem 5).
        *   Um prompt solicitando uma piada ofensiva foi bloqueado por Ódio (baixo) (Imagem 10).
    *   Em ambos os casos, o sistema impediu a geração de uma resposta inadequada e informou o motivo da filtragem, demonstrando a funcionalidade da camada de segurança do Azure OpenAI.

    ![Filtro de Conteúdo em Ação - Violência](image_5.png) _(Referência: Imagem 5)_
    ![Filtro de Conteúdo em Ação - Ódio](image_10.png) _(Referência: Imagem 10)_

5.  **Exploração de Outros Recursos:**
    *   O AI Studio também oferece acesso a outros serviços de IA, como a **Tradução de Texto** (Imagem 8), onde um texto em português foi traduzido para o inglês.

    ![Tradução de Texto no AI Studio](image_8.png) _(Referência: Imagem 8)_

    *   Paralelamente, a exploração da IA generativa incluiu o uso de ferramentas como o **Microsoft Copilot** (Imagem 6) para tarefas criativas, como a solicitação de criação de um logo minimalista.

    ![Interação com Microsoft Copilot](image_6.png) _(Referência: Imagem 6)_

6.  **Variações na Implantação (Opcional):**
    *   Durante a exploração, diferentes configurações de implantação foram testadas, como visto na Imagem 9, para o modelo `gpt-4o` com uma versão diferente (`2024-11-20`) e limites de taxa distintos (50k TPM / 60 RPM).

    ![Outra Configuração de Implantação - gpt-4o](image_9.png) _(Referência: Imagem 9)_

## Principais Aprendizados

*   O Azure AI Studio centraliza diversas ferramentas e serviços para desenvolvimento e gerenciamento de IA no Azure.
*   O processo de implantação de modelos como GPT-4o-mini e o GPT-4o é direto, com opções claras para configuração de versões, cotas e filtros.
*   O Playground de Chat é uma ferramenta eficaz para testar rapidamente modelos de linguagem.
*   Os filtros de conteúdo são um componente essencial para garantir a segurança e o uso responsável da IA, bloqueando ativamente prompts e conteúdos prejudiciais.
*   O Azure oferece um ecossistema rico de serviços de IA além dos modelos de chat, como tradução, criação de imagens, análise de documentos entre outras abordagens.

## Conclusão

Esta exploração prática proporcionou uma compreensão valiosa do Azure AI Studio, desde a configuração inicial e implantação de modelos até a interação e, crucialmente, a implementação de medidas de segurança através de filtros de conteúdo. A experiência destacou a capacidade da plataforma Azure para suportar o desenvolvimento de aplicações de IA de forma robusta e responsável.

---
