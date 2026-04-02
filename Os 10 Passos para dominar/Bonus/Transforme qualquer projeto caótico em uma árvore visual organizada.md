
> [!tldr]  
> Transforme qualquer projeto caótico em uma árvore visual organizada com estrutura ASCII, indicadores de status e barras de progresso atualizadas em tempo real. Esse framework ajuda a mapear tarefas, acompanhar evolução e manter clareza operacional durante toda a conversa.

---

# Project Tree: Visualizador dinâmico de progresso e fluxo

## 1. O que é a Project Tree?

A **Project Tree** é um framework que converte o planejamento caótico de projetos em uma hierarquia visual clara, usando uma árvore em ASCII com acompanhamento de progresso em tempo real.  
A ideia central é representar projetos, subprojetos e tarefas em uma estrutura simples, legível e atualizável ao longo da conversa.

> [!question] Por que isso funciona bem?
> 
> - Organiza projetos complexos visualmente;
>     
> - Deixa o progresso fácil de acompanhar;
>     
> - Melhora a clareza sobre o que já foi feito e o que falta;
>     
> - Permite atualizações naturais durante a conversa;
>     
> - Facilita transformar discussões soltas em planos acionáveis.
>     

---

## 2. Problema → Solução

O framework foi pensado para resolver quatro dores principais da organização de projetos via prompts.

### 2.1. Arquitetura do framework

- **🌳 Caos no projeto** → Visualizador em árvore ASCII com mapeamento hierárquico inteligente.
    
- **📊 Dificuldade de acompanhar progresso** → Sistema dinâmico de status com barras de progresso autoatualizáveis.
    
- **📈 Falta de clareza sobre o estado das tarefas** → Indicadores visuais inteligentes como `✓`, `▶️`, `⏳` e `⭘`.
    
- **⚡ Atualização manual trabalhosa** → Processamento de linguagem natural para aceitar atualizações escritas de forma natural.
    

---

## 3. Como usar a Project Tree

Você pode começar um projeto do zero ou aplicar o framework no meio de uma conversa já em andamento.

### 3.1. Começando do zero

Basta pedir para estruturar com base no seu objetivo:

```markdown
Create project tree for [seu projeto]
```

### 3.2. Organização no meio da conversa

Se você já estiver discutindo funcionalidades ou requisitos, pode pedir à IA que consolide tudo:

```markdown
Com base no que discutimos até agora, crie a Project Tree organizando todos os requisitos e tarefas.
```

Isso faz com que o sistema reorganize o que já foi discutido em uma árvore de projeto coesa.

### 3.3. Atualizações durante o fluxo

Você pode enviar comandos ou linguagem natural para atualizar status, como:

```markdown
Update project tree: Task A is complete, Task B has started.
```

O sistema atualiza a árvore, reflete as porcentagens e recalcula métricas.

---

## 4. Estrutura e formatação

Para usar a Project Tree eficientemente, instrua o sistema com este bloco base:

### 4.1. Configuração do framework

```markdown
## Core Function: Project Tree Visualizer

1. Structure Guidelines
- Represent projects and tasks in ASCII tree format.
- Keep hierarchies clean and simple.
- Preserve consistent spacing.

2. Display Options (Block Format)
- Project [Percentage]
  ├── Task A ▶️ [60%]
  │   ├── Sub-task 1 ✓ [100%]
  │   └── Sub-task 2 ⏳ [20%]
  └── Task B ⭘ [0%]
  
- Progress Bar: [██████░░░░] 60%

3. Status & Progress Trackers
- Update parent nodes automatically based on child completion.
- Re-calculate progress in real-time.
- Status symbols:
  * 0% = Not started ⭘
  * 1-99% = In progress ▶️
  * 100% = Complete ✓
  * Blocked = ⏳
```

### 4.2. Regras de cálculo

Ao usar a estrutura acima, o prompt exige que o modelo calcule o progresso de forma dinâmica:

- Progresso do nó pai = média das tarefas filhas finalizadas.
- O avanço impacta nas barras visuais imediatamente na próxima saída.

---

## 5. Protocolo de atualização dinâmico

Para garantir que a árvore não se perca no meio do contexto, defina comandos rápidos para a IA:

### 5.1. Comandos Básicos suportados

```markdown
- "Show project tree": Mostra a árvore atual.
- "Show project status": Apenas porcentagem geral.
- "Update: [descrição]" : Aplica mudança e renderiza árvore.
```

### 5.2. Gestão de Contexto

Instrua a IA a sempre manter a árvore nos trilhos:

```markdown
## Context Management
- Track updates throughout the conversation.
- Handle state changes gracefully.
- Validate changes before applying them to the tree.
- Preserve history and ignore unrelated conversation branches.
```

---

## 6. Exemplo de renderização final

A saída visual deve ficar da seguinte forma após comandos de atualização:

```markdown
Project: Lançamento de Site
[█████░░░░░] 50% Overall Progress

├── 1. Planejamento ▶️ [50%]
│   ├── Definição de escopo ✓ [100%]
│   └── Levantamento de requisitos ⭘ [0%]
│
└── 2. Execução ▶️ [30%]
    ├── Backend ✓ [100%]
    └── Frontend ⏳ [20%]
        └── Testes Unitários ⭘ [0%]
```

Esse formato deixa claro o estado de desenvolvimento, a arquitetura de tarefas e ajuda muito a revisar planos de ação diretamente do chat.

---

## 7. Quando usar esse framework?

Ele é ideal quando você quer:

- Quebrar projetos grandes em pacotes de trabalho menores e gerenciáveis;
- Acompanhar visualmente metas de longo prazo com a IA sem usar ferramentas externas;
- Organizar brainstormings dispersos em uma estrutura única acionável;
- Recuperar o controle de conversas complexas que perderam o rumo organizacional.

> [!success] Vantagem Prática
> Ao usar a Project Tree, você transforma a interface de texto do ChatGPT/Claude em um mini-gerenciador de projetos que responde a linguagem natural.