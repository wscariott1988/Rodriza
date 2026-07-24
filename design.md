# Contrato de Design System e Especificação Visual (design.md)
**Projeto:** Landing Page Rodriza — Emissão de NF-e e Suporte Especializado  
**Pipeline:** Google Stitch (Prototipagem Conversional) ➔ Google Antigravity (Desenvolvimento Next.js/React + Tailwind CSS)  
**Versão:** 1.0  

Este documento serve como a **única fonte da verdade (Single Source of Truth)** para a identidade visual, tokens de design, ergonomia de interface e especificações de componentes da Landing Page da Rodriza. Ele foi estruturado para garantir interoperabilidade agentiva entre o protótipo gerado no Google Stitch e a implementação final do código na IDE Antigravity.

---

## 1. Tokens de Design (Tokens de Estilo)

Para garantir consistência visual e facilidade de manutenção, todos os tokens definidos abaixo devem ser centralizados no arquivo de configuração do Tailwind CSS (`tailwind.config.js`) na IDE Antigravity.

### 1.1. Paleta de Cores (Color Palette)
A paleta baseia-se estritamente na identidade oficial da Rodriza, aplicando a regra de acessibilidade WCAG 2.1 (contraste mínimo de 4.5:1 para leitura confortável e sem fadiga visual).

*   **Cor Primária (Confiança e Estrutura):**  
    *   `brand-blue`: `#295399` (Azul oficial Rodriza)
    *   `brand-blue-dark`: `#1A2C54` (Tom escuro profundo derivado, ideal para fundos de seções escuras como a Hero e o Banner final)
*   **Cor de Ação/Destaque (Altíssimo Contraste para Conversão):**  
    *   `brand-red` / `accent-color`: `#CE4F3A` (Vermelho oficial Rodriza. **Uso exclusivo para botões de conversão e elementos de altíssima atenção** para guiar o clique do visitante)
*   **Cores Neutras e Superfícies:**  
    *   `neutral-background`: `#F4F4F6` ou `#FAFAFA` (Cinza claro ultra suave para o fundo de 80% da página, minimizando o cansaço visual comum de fundos brancos puros)
    *   `surface-gray`: `#DEDEDE` (Cinza oficial Rodriza. Utilizado estritamente para bordas finas de cards, divisores horizontais e fundos de inputs desmarcados)
    *   `card-white`: `#FFFFFF` (Fundo dos blocos/cards flutuantes sobre o cinza claro, gerando sensação de profundidade)
*   **Tipografia e Textos:**  
    *   `text-dark` (Texto Principal): `#1E1E24` (Grafite escuro para alta legibilidade sem o contraste agressivo do preto puro)
    *   `text-muted` (Texto Secundário): `#5A5A62` (Para descrições mais longas, subtítulos internos e textos de FAQ)

### 1.2. Tipografia (Typography Stack)
Uma hierarquia de fontes limpa, séria e de excelente visualização em telas de qualquer resolução (essencial para o ambiente industrial).

*   **Títulos Principais (Headlines & Section Titles):**  
    *   **Família:** `Sora` (ou `Inter` configurado em peso negrito pesado)
    *   **Estilo:** Sans-serif moderno, geométrico, transmitindo precisão e robustez.
    *   **Pesos:** `Bold 800` para Hero, `SemiBold 600` para títulos de seções.
*   **Textos de Apoio e Parágrafos (Body Text):**  
    *   **Família:** `Inter` (ou sans-serif equivalente do sistema de alta legibilidade)
    *   **Estilo:** Altamente legível mesmo em telas menores (mobile).
    *   **Pesos:** `Regular 400` para leitura geral, `Medium 500` para diferenciais rápidos e destaques.
*   **Proporções (Font Scale):**
    *   `Display H1` (Hero): `40px` (Desktop) / `32px` (Mobile) — Altura de linha: `1.2`
    *   `H2` (Seções): `32px` (Desktop) / `24px` (Mobile) — Altura de linha: `1.3`
    *   `H3` (Cards/Tópicos): `20px` (Desktop) / `18px` (Mobile)
    *   `Body Text`: `16px` — Altura de linha: `1.6` (Espaçamento ideal para escaneabilidade)
    *   `Micro Labels`: `12px`

### 1.3. Espaçamento e Grid (Spacing & Grid)
*   **Base Spacing Unit:** Multiplos de `8px` (`8px`, `16px`, `24px`, `32px`, `48px`, `64px`, `96px`).
*   **Grid de Layout:**
    *   **Desktop:** 12 colunas, largura máxima de conteúdo centralizado a `1200px`, padding lateral mínimo de `24px`.
    *   **Mobile:** Grid de coluna única responsiva, padding lateral de `16px`.
*   **Padding de Seções (Vertical):** `80px` (Desktop) / `48px` (Mobile) para garantir áreas de "respiro visual" entre as seções.

### 1.4. Arredondamentos e Sombras (Borders & Shadows)
*   `borderRadius-cards`: `12px` (Suaviza o visual de blocos sem parecer infantilizado).
*   `borderRadius-buttons`: `8px` (Bordas ligeiramente arredondadas, mantendo o aspect corporativo e sério).
*   `boxShadow-soft`: `0 4px 20px rgba(0, 0, 0, 0.05)` (Sombras extremamente leves para destacar cards brancos sobre o fundo cinza claro).

---

## 2. Diretrizes de Ergonomia Visual e Usabilidade Industrial

Sistemas industriais tradicionais costumam falhar ao sobrecarregar a tela com dados e jargões. Na Landing Page da Rodriza, o design deve seguir as seguintes premissas ergonômicas (embasadas no modelo de prevenção de erro visual ISO 9241):

1.  **Prioridade do Computador (Desktop):** O preenchimento e controle de faturamento fiscal de alta densidade exige telas de monitor. Por isso, a hierarquia visual da Landing Page deve priorizar uma visualização impecável em Desktop, usando o Mobile como uma transição leve e rápida de captura de lead.
2.  **Eliminação Total de Distração (Zero Friction):** Não deve existir menu superior clássico com links que tirem o visitante da página (como "Sobre Nós", "Módulos", "Blog"). O único caminho de conversão é o clique no botão de ação, reduzindo a taxa de rejeição de tráfego frio.
3.  **Destaque Cromático para Ação:** A cor vermelha `#CE4F3A` deve ser reservada **exclusivamente** para os botões de ação principal (CTAs). Nenhuma outra parte decorativa do site ou ícone pode usar essa cor, garantindo que o olho do usuário encontre o ponto de clique instantaneamente ao escanear a tela.

---

## 3. Especificação das 5 Seções da Landing Page

Abaixo está o mapeamento detalhado de cada seção para aplicação no editor visual do Google Stitch (usando o assistente de design "Idiate") e posterior exportação para a IDE Antigravity.

### SEÇÃO 1: HERO SECTION (O Topo da Página)
*   **Propósito:** Reter o tráfego frio imediatamente, apresentando a proposta de valor unificada (velocidade na nota + especialista técnico ao lado).
*   **Estilo Visual:** Seção escura e imponente para passar seriedade.
    *   **Fundo:** Azul escuro profundo (`#1A2C54`).
    *   **Lado Esquerdo (6 Colunas):** 
        *   Título principal em branco puro (`#FFFFFF`) com tipografia Sora destacada.
        *   Subtítulo em cinza claro com excelente contraste, explicando o suporte do Daniel integrado à contabilidade.
        *   Lista vertical contendo os **6 Diferenciais Rápidos** com ícones em verde menta (`#4DD9AC`) ou azul claro para acompanhar os textos.
        *   Botão de Ação CTA de tamanho destacado em Vermelho (`#CE4F3A`) com texto em branco: `[⚡ Agendar Conversa com Nosso Especialista]`.
    *   **Lado Direito (6 Colunas - Apenas em Desktop):** 
        *   Mockup limpo e realista de um notebook aberto exibindo a tela de faturamento simplificada do ERP. Uma segunda imagem menor sobreposta pode mostrar uma foto profissional do Daniel com uma tag discreta: *"Daniel — Analista de Faturamento e Processos Industriais"*.

### SEÇÃO 2: EVOLUÇÃO NO SEU RITMO (A Cunha e Expansão)
*   **Propósito:** Mostrar que o cliente resolve a sua urgência atual (faturar), mas que o sistema é robusto e expansível para estoque, compras e financeiro.
*   **Estilo Visual:** Seção clara para facilitar a leitura.
    *   **Fundo:** Cinza ultra suave (`#FAFAFA`).
    *   **Estrutura de Conteúdo:**
        *   Título centralizado e texto introdutório focando em "módulos que se conectam sob demanda".
        *   Abaixo, 3 cards lado a lado (`card-white` com sombra suave e borda fina em `#DEDEDE`).
        *   **Card 1 (Estoque Inteligente):** Ícone de caixa. Texto explicando a baixa/reserva automática do estoque diretamente no Pedido de Venda. Destaque para a flexibilidade de analisar cada caso e integrar o PCP para itens montados.
        *   **Card 2 (Compras Planejadas):** Ícone de carrinho de compras. Texto mostrando como o PCP cruza dados de vendas para gerar ordens de compra automáticas de insumos, sem achismo.
        *   **Card 3 (Financeiro Automatizado):** Ícone de moedas. Texto mostrando que faturar a nota fiscal cria o Contas a Receber instantaneamente no caixa.
    *   **Rodapé da Seção (A Semente):** Uma frase curta destacada lembrando que ele pode iniciar hoje apenas emitindo notas e ativar o restante quando estiver pronto, sem perder dados e sem precisar migrar de software.

### SEÇÃO 3: OS TRÊS PILARES DE SEGURANÇA (Redução de Ansiedade)
*   **Propósito:** Quebrar as objeções de transição sem entrar em detalhes complexos de infraestrutura de TI que possam assustar o comprador.
*   **Estilo Visual:** Fundo claro com divisores discretos.
    *   **Fundo:** `#FAFAFA` com os 3 blocos estruturados em colunas no desktop.
    *   **Bloco 1 (Suporte Humano Próximo):** Ícone de balão de conversa ou WhatsApp. Texto focado na dor de "ficar preso no suporte de robôs e tickets dos ERPs gigantes". A Rodriza entrega atendimento rápido pelo WhatsApp sempre com a mesma pessoa que conhece o seu caso.
    *   **Bloco 2 (Importação Sem Dor):** Ícone de envio de arquivo/planilha. Texto explicando que a Rodriza faz o trabalho pesado de importar os dados antigos de clientes e produtos gratuitamente para ele faturar no primeiro dia.
    *   **Bloco 3 (Diagnóstico de Processo):** Ícone de calendário ou aperto de mãos. Explicação de que, antes de fechar qualquer negócio, é agendada uma conversa (online ou presencial) para alinhar as regras fiscais com o contador do cliente.

### SEÇÃO 4: A CARTA DO ESPECIALISTA (Aproximação Humana)
*   **Propósito:** Estabelecer autoridade técnica e criar conexão emocional profunda de confiança. O Daniel deixa de ser o "programador" e assume o papel de "conselheiro de processos".
*   **Estilo Visual:** Seção com fundo texturizado ou sutilmente diferenciado para parecer um editorial.
    *   **Fundo:** Azul suave lavanda (`#F4EFFF`).
    *   **Lado Esquerdo (4 Colunas):** Foto profissional e acolhedora do Daniel, com o cargo de *"Analista de Processos Industriais e Fundador da Rodriza"*.
    *   **Lado Direito (8 Colunas):** Texto corrido da carta do Daniel em tipografia altamente legível, reforçando o compromisso pessoal de ligar diretamente para o contador do cliente se houver alterações de regras fiscais e oferecer melhorias personalizadas sob medida (sob orçamento).

### SEÇÃO 5: FAQ & CHAMADA DE CONVERSÃO (O Fechamento)
*   **Propósito:** Eliminar as últimas dúvidas pontuais e forçar o clique final para o WhatsApp.
*   **Estilo Visual:** Seção dividida em duas etapas.
    *   **Fundo da Etapa FAQ:** Cinza claro suave (`#FAFAFA`).
    *   **Estrutura do FAQ:** Accordion (sanfona) contendo as 5 perguntas estruturadas (homologação estadual de notas, funcionamento online/offline híbrido, migração de dados, suporte direto com o contador e política de assinatura mensal previsível sem fidelidade).
    *   **Banner Final de Conversão (Fundo Escuro):**
        *   Fundo em Azul Escuro Profundo (`#1A2C54`) para fechar o contraste da página.
        *   Título de impacto direto: *"Vamos organizar o faturamento da sua indústria?"*.
        *   Texto de apoio convidando para o agendamento de um diagnóstico gratuito de processos de faturamento em 15 minutos.
        *   Botão de Ação CTA proeminente em Vermelho (`#CE4F3A`): `[⚡ Agendar Conversa com o Especialista]`.

---

## 4. Diretrizes para Prototipagem e Geração de Código

### 4.1. Instruções para o Google Stitch (Prototipagem)
Quando for criar a estrutura visual das telas dentro do Google Stitch, utilize as seguintes diretrizes conversacionais no assistente para manter a fidelidade com este guia:
*   Use adjetivos como **"Sério, corporativo, focado em processo industrial e seguro"** para orientar o algoritmo de estilo em direção a cantos mais retos, fontes limpas e estrutura sólida (evite bordas excessivamente arredondadas ou cores neon sem propósito).
*   Utilize o recurso de **Style Injection** inserindo referências de sistemas industriais modernos para que a IA capture os padrões de grids e tabelas limpas.
*   Trabalhe com a granularidade tela a tela: configure a Hero com o fundo escuro e use o editor de anotações (ferramenta de desenho e seleção) para remover elements que fujam do fluxo estático de conversão direta.

### 4.2. Integração de Código no Google Antigravity (Tailwind)
Ao exportar o protótipo funcional para código Next.js/React na IDE Antigravity, certifique-se de:
1.  Isolar os tokens de design do arquivo `design.md` diretamente no `theme.extend` do `tailwind.config.js`.
2.  Criar um componente de botão reutilizável (`Button.tsx`) contendo a animação padrão de escala no hover (`hover:scale-105 transition duration-300`) e a cor vermelha de contraste fixa (`bg-brand-red` / `hover:bg-opacity-90`), prevenindo duplicações de classes CSS em strings longas pelas páginas do app.
3.  Utilizar componentes estáticos estruturados, garantindo carregamento instantâneo da página no primeiro clique de tráfego frio.
