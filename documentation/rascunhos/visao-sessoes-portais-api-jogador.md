# Rascunho: sessões de RPG, portais e dados do jogador

| Campo | Valor |
| --- | --- |
| Status | **Rascunho — não canônico** |
| Data | 2026-08-11 |
| Fonte | Conversa com o PM (alinhamento de requisitos) |
| Gap | [GAP-010](../../GAPS.md) |

Este arquivo **não** registra produto, serviço, regra nem decisão. Só organiza o que o PM já disse e o que permanece `INFORMAÇÃO AUSENTE`.

## Intenção declarada (PM)

Gerenciar sessões de RPG no ecossistema Delfanor, testando uma variedade de sistemas que depois se conectam a outros serviços.

O **primeiro sistema** apontado pelo PM: API + banco de dados com informações dos jogadores, compartilhado entre múltiplos sistemas/jogos, com renderização diferente em cada um.

Conectado a isso: portais para gerar/gerir mesas — portal de administrador/mestre e portal de jogador.

## Mapa de requisitos

Legenda: **Dito** = falado pelo PM nesta conversa. **Em branco** = `INFORMAÇÃO AUSENTE` (não inventar).

### 1. Serviço compartilhado de dados do jogador

| ID | Item | Estado |
| --- | --- | --- |
| R1 | API + banco para guardar informações dos jogadores | Dito (primeiro sistema) |
| R2 | Dados compartilhados entre múltiplos sistemas / jogos diferentes | Dito |
| R3 | Cada jogo/sistema só renderiza diferente (mesma informação, apresentação distinta) | Dito |
| R4 | Fronteira entre **jogador** (pessoa/conta), **personagem** e **ficha** | Em branco |
| R5 | Quais informações exatamente o banco guarda | Em branco |
| R6 | Um jogador pode ter vários personagens / várias fichas / várias mesas | Em branco |
| R7 | Autenticação, autorização e contas | Em branco |
| R8 | Contrato da API (recursos, eventos, tempo real vs request/response) | Em branco |
| R9 | Nome canônico do serviço e repositório de código | Em branco (GAP-004, inventário de produtos/remotes vazio) |

### 2. Portais e papéis

| ID | Item | Estado |
| --- | --- | --- |
| R10 | Portal para gerar mesas | Dito |
| R11 | Portal de administrador / mestre | Dito (PM usou os dois termos juntos) |
| R12 | Portal de jogador | Dito |
| R12a | Nome pretendido do projeto do portal do jogador: `delfanor-portal-player` | Dito (2026-08-11). **Ainda não** está no inventário de produtos |
| R13 | “Gerar mesas” é o mesmo produto que o portal do mestre, ou outro | Em branco |
| R14 | Administrador e mestre são o mesmo papel ou papéis distintos | Em branco |
| R15 | Quantos produtos/repositórios (um app com papéis vs vários) | Parcial: pelo menos um projeto nomeado (`delfanor-portal-player`). Demais produtos em branco |
| R16 | Quem cria mesa, quem convida, quem entra | Em branco |

### 3. Portal do jogador (`delfanor-portal-player`)

#### Layout e chat

| ID | Item | Estado |
| --- | --- | --- |
| R41 | Layout: página = chat; abas com toggle (ex.: ficha, inventário) | Dito |
| R42 | Sem nenhum toggle ativo, a página é só o chat em tela cheia | Dito |
| R21 | Visão da mesa em andamento | Parcial: a página é um **chat** que renderiza o log da sessão |
| R43 | Existe um **arquivo de log da sessão**, detalhado | Dito (formato, onde vive, quem grava: em branco) |
| R44 | O chat **renderiza** o log (cores, animações, mensagens padronizadas, etc.) | Dito — o que exatamente aparece para o jogador, e como, ainda em branco |
| R45 | Jogador **não inicia** ação que entra no log | Dito |
| R47 | Jogador vê **tudo junto** no chat (log renderizado + conversa) | Dito |
| R48 | Persistência **separada**: conversa vs log de eventos | Dito |
| R49 | O que **sai** do portal do jogador = **só conversa**. Eventos de jogo (cena, combate, rolagem, ações) = log principal, produzido **do lado do mestre** (PM: “acredito que”) | Dito |
| R50 | Distinguir fala vs ação no teclado do jogador | Não se aplica — jogador não dispara ação de log pelo chat |

#### Rolagem

| ID | Item | Estado |
| --- | --- | --- |
| R51 | Pedido de rolagem: mestre envia → jogador interage → resultado volta ao mestre | Dito |
| R52 | UI da rolagem: na **barra de escrita**, um **ícone de dado**; anima quando chega notificação do mestre; ao clicar, valores aleatórios são gerados **para o mestre** | Dito. Como é a animação: em branco |
| R53 | Há outros pedidos do mestre além de rolagem (ex.: confirmações) | Em branco |
| R54 | Depois da rolagem, linha de **log no chat**, narrativa (exemplos do PM, não copy fechado): sucesso ≈ “Fulano fez algo!”; falha ≈ “Fulano tentou fazer algo, mas isso aconteceu…” + consequência (ex.: tomou dano, “Está caído!”) | Dito como intenção/exemplo. Copy canônico: em branco |
| R55 | A narrativa **pode incluir** o quanto foi o resultado, com uma **reação** apropriada conforme o quão bom/ruim foi | Dito. Limiares (o que é bom/ruim) e se o número é sempre obrigatório: em branco |
| R56 | Narrativa: **sistema de templates** + ação com **input manual** (a ação varia bastante) | Dito como intenção |
| R57 | Validação: o **mestre valida antes de enviar** o pedido de rolagem. Para o jogador, tudo já está pronto: **só rolar e o resultado acontece** | Dito |

#### Ficha e criação

| ID | Item | Estado |
| --- | --- | --- |
| R17 | Ficha em aba/painel com toggle | Dito |
| R18 | Depois da criação: a ficha tem **partes alteráveis** e **não alteráveis**. Jogador não “edita a ficha inteira”; o que for travado continua consulta | Dito |
| R20 | Depois da criação, **travados**: nome, raça, origem | Dito |
| R58 | **Criação da ficha** acontece no `delfanor-portal-player` — única vez em que o jogador preenche a ficha neste portal | Dito |
| R59 | Criação — **ficha** (não misturar com aparência): **nome** | Dito |
| R60 | Ficha: **raça** (escolha **dentro das opções**) | Dito. Lista de raças: em branco |
| R61 | Ficha: **atributos** — sempre **três: vermelho, azul e verde**. Jogador distribui uma quantidade **X** de pontos | Dito. Valor de X, mínimo/máximo por atributo: em branco |
| R62 | Ficha: **origem** (dentro das opções); origens diferentes **começam com itens diferentes** | Dito — origem **é** campo da ficha (itens iniciais). Lista de origens e itens: em branco |
| R46 | Padrão da ficha na **criação** (neste portal) | Parcial — ficha: R59–R62; aparência (separada): R63. Ainda **não** há área canônica em `documentation/rules/` nem glossário |

#### Aparência (separada da ficha)

| ID | Item | Estado |
| --- | --- | --- |
| R63 | **Aparência é separada da ficha** — campos **só estéticos** | Dito |
| R63a | Corpo: **dois padrões** — feminino e masculino. Não é campo de gênero na ficha; é tipo de corpo da aparência | Dito |
| R63b | Exceção hipotética: classe especial andrógena na história pode ter um só padrão de corpo — **não** é regra fechada | Dito como “talvez” |
| R63c | Aparência: opções de **cabelos** e **marcas no rosto** | Dito. Listas: em branco |
| R63d | Aparência: **roupas** vêm da **origem** | Dito |

#### Inventário, nível e outras abas

| ID | Item | Estado |
| --- | --- | --- |
| R19 | Outras abas/painéis além da ficha | Parcial: **inventário** (painel) — e outras abas não listadas |
| R19a | **Inventário** é alterável **no portal** | Dito. O que o jogador pode fazer (equipar, usar, soltar, etc.): em branco |
| R20a | **Atributos** podem subir e descer quando o jogador **sobe de nível**, porque ele **escolhe para onde vão os pontos** | Dito |
| R20b | Valor do atributo **dividido**: **base** (o que o jogador escolhe na criação + o que ganha com nível) e **adicional** (itens, poderes, etc.) | Dito. Como a ficha mostra isso, lista de poderes, como item concede adicional: em branco |
| R20c | Alocação de pontos de nível é **neste portal**, **durante a sessão**, **na própria interface da ficha** | Dito |
| R20d | Gatilho: **mestre ou sistema** avisa que subiu de nível; a ficha mostra os pontos para gastar | Dito. Se é só somar pontos ou também realocar: em branco |

### 4. Portal do mestre / administrador

| ID | Item | Estado |
| --- | --- | --- |
| R22 | Necessidades para mestrar a mesa | Dito (a lista abaixo é o recorte falado) |
| R23 | Iniciar encontros | Dito |
| R24 | Iniciar rolagens de dados | Dito — mestre envia **pedido de rolagem** ao jogador |
| R25 | Iniciar combate | Dito |
| R26 | Separar cenas | Dito |
| R27 | Começar uma sessão | Dito |
| R28 | Terminar uma sessão | Dito |
| R29 | Relação entre sessão, cena, encontro e combate | Em branco |
| R30 | Quem inicia rolagem e quem resolve | Parcial: jogador **não inicia** ação de log. Mestre envia pedido; jogador interage com o processo e devolve o resultado ao mestre. O log, na visão do PM, é feito **do lado do mestre** |
| R31 | Outras necessidades de mestragem (iniciativa, NPCs, mapa, anotações, etc.) | Em branco — PM disse que há mais ideias, a determinar |

### 5. Mesa e sessão

| ID | Item | Estado |
| --- | --- | --- |
| R32 | Gerenciar sessões de RPG | Dito |
| R33 | Gerar / criar mesas | Dito |
| R34 | Diferença entre **mesa**, **campanha** e **sessão** | Em branco |
| R35 | Persistência entre sessões (o que sobrevive ao “terminar sessão”) | Em branco |

### 6. Sistemas de jogo vs sistemas de software

| ID | Item | Estado |
| --- | --- | --- |
| R36 | Variedade de sistemas a testar, depois ligados a outros serviços | Dito |
| R37 | Primeiro sistema de **software**: API + banco do jogador | Dito |
| R38 | “Sistema” também significa sistema de **regras de RPG** (além de software) | Em branco |
| R39 | Qual o primeiro sistema de regras / jogo a renderizar a ficha | Em branco (GAP-002 / GAP-003) |
| R40 | Como a ficha compartilhada se adapta a jogos diferentes | Em branco (além de “renderizado diferente”) |

## Termos candidatos (ainda sem glossário)

Não definidos (GAP-005). Apareceram na conversa ou neste rascunho: **mesa**, **sessão**, **cena**, **encontro**, **combate**, **ficha**, **jogador**, **mestre**, **administrador**, **portal**, **rolagem**, **pedido de rolagem**, **chat**, **log de sessão**, **painel/aba**, **inventário**, **atributos**, **vermelho / azul / verde**, **valor base**, **adicional**, **nível**, **poderes**, **raça**, **origem**, **aparência**, **corpo** (feminino / masculino; andrógeno como talvez), **cabelo**, **marcas no rosto**, **roupas**, **classe**, **ícone de dado**.

Não promover para `documentation/ubiquitous-language/` sem definição aprovada pelo PM.

## O que este rascunho não decide

- Stack, CI, deploy (GAP-008)
- Repositórios externos / remotes (allowlist vazia)
- Regras canônicas de RPG (GAP-002)
- Inventário de serviços ou produtos (GAP-004; produtos = 0)

## Recorte atual (PM)

Visão do jogador em `delfanor-portal-player` (2026-08-11). **Não canônico.** PM pediu para documentar o que falta e pausar o esclarecimento.

### O que já foi dito (visão do jogador)

1. A página é um **chat**; abas com toggle (ficha, inventário, outras **não listadas**). Sem toggle, só o chat em tela cheia.
2. Jogador vê **tudo junto** no chat: log de sessão renderizado (cores, animações, mensagens padronizadas) + conversa.
3. Persistência **separada**: o que **sai** deste portal = **só conversa**. Eventos de jogo (cena, combate, rolagem, ações) = **log principal**, do lado do **mestre**.
4. Jogador **não inicia** ação de log. Rolagem: mestre **valida e monta antes** (templates + input manual da ação) → envia pedido → ícone de **dado na barra de escrita** anima → clique gera valores **para o mestre** → narrativa no chat. Jogador **só rola e o resultado acontece**.
5. Narrativa (exemplos, não copy fechado): sucesso ≈ “Fulano fez algo!”; falha ≈ “Fulano tentou… consequência”. **Pode** incluir o número e uma **reação** conforme o quão bom/ruim foi.
6. **Ficha ≠ aparência.** Aparência é só estética: corpo feminino ou masculino (gênero **não** é campo da ficha); cabelo e marcas no rosto à escolha; **roupas pela origem**. Andrógeno = “talvez” temático, não regra.
7. **Criação neste portal** (única vez que o jogador preenche a ficha aqui): **nome, raça, vermelho/azul/verde (X pontos), origem**. Origem é ficha (itens iniciais diferentes).
8. Depois da criação: **travados** nome, raça, origem. **Inventário** alterável no portal. Ficha tem partes alteráveis e não alteráveis.
9. Atributos: valor = **base** (criação + nível) + **adicional** (itens, poderes, etc.). No **nível**, mestre/sistema avisa; jogador aloca pontos **durante a sessão, na interface da ficha**. Atributos podem subir e descer porque o jogador escolhe o destino dos pontos.
10. Outras abas e necessidades **existem e não foram listadas** — a lista atual é base, não fechada.

Inventário canônico de produtos continua **vazio** até onboard explícito. Não promover a `documentation/rules/`, glossário, serviços ou produtos sem o PM pedir.

### INFORMAÇÃO AUSENTE — checklist para retomar

Não preencher. Próxima sessão: `clarify-with-pm`, **um tópico por vez**.

**`delfanor-portal-player` — UI / fluxo**

- O que o jogador pode fazer no **inventário** (equipar, usar, soltar, etc.)
- Como a ficha **mostra** base vs adicional
- Alocação de nível: só **somar** pontos ou também **realocar**
- Animação do ícone de dado
- Catálogo do que o chat **mostra** ao jogador, e como (além da intenção de renderizar o log)
- Outros pedidos do mestre além de rolagem
- Outras abas além de ficha e inventário
- Como o jogador **entra na mesa** / passa da criação ao chat da sessão
- Um jogador, vários personagens / fichas / mesas (R6)
- Layout entre sessões (mesmo shell chat+toggles ou não)

**Criação / conteúdo (listas e números)**

- Valor **X** de pontos na criação; mínimo/máximo por atributo
- Lista de **raças**
- Lista de **origens** e **itens iniciais** de cada uma
- Listas de **cabelos** e **marcas no rosto**
- Catálogo de **templates** de ação/narrativa; copy canônico; limiares bom/ruim; se o número na frase é sempre obrigatório
- Quem **grava** o log, formato e onde o arquivo vive

**Portal do mestre / mesa** (quase não fechado nesta sessão)

- Admin vs mestre; gerar mesa = mesmo produto?
- Relação **mesa / campanha / sessão** e o que sobrevive ao terminar sessão
- Relação **sessão / cena / encontro / combate**
- Demais necessidades de mestragem (iniciativa, NPCs, mapa, etc.)
- Quem cria mesa, convida, entra

**API, produtos, regras**

- Fronteira jogador (conta) vs personagem vs ficha
- Contrato da API / o que o banco guarda
- Nome canônico do serviço e repositório (produtos/remotes = 0)
- Stack/CI (GAP-008)
- Promoção a rules/systems/glossary — **não feita**
- Classe na criação: **não confirmada** (só hipótese temática de corpo)

## Próximo passo de alinhamento

PM pausou (2026-08-11). Retomar neste arquivo + `clarify-with-pm`. Não inventar listas, X, copy nem onboard.
