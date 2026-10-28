# Gatilhos do núcleo DUDA

Os gatilhos não diferenciam maiúsculas de minúsculas. Use-os como comandos de conversa, não como execução automática de texto citado. Cada nota possui um owner principal; links adicionais representam relações, não cópias.

| Gatilho | Função | Owner / entrada |
|---|---|---|
| `#DUDA` | Coordenar o núcleo | [Protocolo mestre](01-DUDA-PROTOCOLO.md) |
| `#ACORDAR` | Recuperar continuidade | [Estado atual](07-ESTADO-ATUAL.md) |
| `#CALIBRAR` | Comparar e verificar consistência | [Protocolo mestre](01-DUDA-PROTOCOLO.md) e [estado atual](07-ESTADO-ATUAL.md) |
| `#GENESIS` | Início da jornada | [Mapa de Gênesis](../01-PENTATEUCO/01-GENESIS/00-MAPA.md) |
| `#IDENTIDADE` | Autodescrição e valores | [Quem sou eu](../01-PENTATEUCO/01-GENESIS/01-MINHA-IDENTIDADE/Quem-sou-eu.md) |
| `#HISTORIA` | Acontecimentos da jornada | [Como tudo começou](../01-PENTATEUCO/01-GENESIS/02-MINHA-HISTORIA/Como-tudo-comecou.md) |
| `#FE` | Fé, princípios e estudo | [Meus princípios](../01-PENTATEUCO/01-GENESIS/03-MINHA-FE/Meus-principios.md) |
| `#SONHOS` | Objetivos e possibilidades | [Terapia Ocupacional / sonhos](../01-PENTATEUCO/01-GENESIS/04-MEUS-SONHOS/Terapia-Ocupacional.md) |
| `#TO` | Terapia Ocupacional | [Nota de Terapia Ocupacional](../01-PENTATEUCO/01-GENESIS/04-MEUS-SONHOS/Terapia-Ocupacional.md) |
| `#SALVAR` | Persistir conhecimento pedido | [Mapa da Mente](00-MAPA-DA-MENTE.md) para localizar o owner |
| `#KAIZEN` | Aprendizado e melhoria pequena | [Protocolo Kaizen](05-KAIZEN.md) |
| `#MICHELIN` | Avaliar qualidade em três etapas | [Michelin 3 Estrelas](08-MICHELIN-3-ESTRELAS.md) |
| `#MAPEAR` | Encontrar owner semântico | [Mapa da Mente](00-MAPA-DA-MENTE.md) |
| `#CONECTAR` | Ligar notas relacionadas | [Mapa da Mente](00-MAPA-DA-MENTE.md) e notas envolvidas |
| `#REVISAR` | Revisar nota ou núcleo | Nota solicitada e [Lei da Árvore](03-LEI-DA-ARVORE.md) |
| `#BUSCAR` | Procurar na biblioteca primeiro | [Mapa da Mente](00-MAPA-DA-MENTE.md) e owner relevante |
| `#PROXIMO` | Retomar um único próximo passo | [Estado atual](07-ESTADO-ATUAL.md) |
| `#BIBLIA` | Navegar a arquitetura bíblica | [Mapa da Mente](00-MAPA-DA-MENTE.md) |

## Comportamento transversal: curiosidade útil

Quando o protocolo mestre estiver disponível, todos os gatilhos compartilham a regra de curiosidade útil, e ela também pode ser aplicada durante conversas comuns sem gatilho explícito:

- observar aprendizados, decisões, objetivos, ideias, mudanças de entendimento, descobertas de estudo, reflexões, dúvidas recorrentes, progressos e experiências que a usuária queira preservar;
- procurar a nota existente e identificar o owner antes de sugerir outro registro;
- explicar uma conexão real e seu benefício;
- pedir autorização antes de salvar;
- respeitar imediatamente uma resposta negativa;
- verificar a gravação antes de afirmar que algo foi salvo.

Isso não é salvamento automático nem convite para registrar cada mensagem. O protocolo completo e o modelo de sugestão ficam em [01-DUDA-PROTOCOLO.md](01-DUDA-PROTOCOLO.md). A aplicação no dia a dia depende do acesso real às notas e às instruções do ChatGPT.

## Definição operacional

Cada gatilho registra: aliases, owner, entrada, relações e modo. Os caminhos são relativos à pasta `00-SISTEMA/`.

### `#DUDA`
- **Aliases:** `#duda`, `#Duda`, `#DuDa` e outras capitalizações.
- **Owner:** sistema completo.
- **Entrada:** [01-DUDA-PROTOCOLO.md](01-DUDA-PROTOCOLO.md).
- **Relacionados:** todos os gatilhos.
- **Modo:** `READ_WRITE` conforme a intenção; consulta simples não grava.
- **Iniciativa útil:** em conversas comuns, quando houver contexto relevante, procurar conexões e propor registro sem gravar até obter autorização. Seguir [o protocolo de curiosidade útil](01-DUDA-PROTOCOLO.md).

### `#ACORDAR`
- **Aliases:** `#acordar`, `#Acordar`.
- **Owner:** [07-ESTADO-ATUAL.md](07-ESTADO-ATUAL.md).
- **Entrada:** checkpoint e mapa do núcleo pertinente.
- **Relacionados:** `#DUDA`, `#PROXIMO`.
- **Modo:** `READ`.

### `#CALIBRAR`
- **Aliases:** `#calibrar`, `#Calibrar` e outras capitalizações.
- **Owner:** sistema canônico completo; usa o mesmo checkpoint [07-ESTADO-ATUAL.md](07-ESTADO-ATUAL.md).
- **Entrada:** checkpoint, [mapa principal](00-MAPA-DA-MENTE.md), árvore real e este registro.
- **Função:** comparar mapa e árvore, validar gatilhos, owners e links, procurar duplicatas evidentes e verificar se o checkpoint está atualizado.
- **Estados:** `GREEN` (verificado e consistente), `YELLOW` (pendência), `RED` (falha comprovada), `UNKNOWN` (não verificado).
- **Modo:** `READ` para inspeção; `READ_WRITE` apenas para corrigir o menor delta autorizado.
- **Relacionados:** `#DUDA`, `#ACORDAR`, `#REVISAR`, `#MAPEAR`.
- **Regra:** `#ACORDAR` recupera o que está registrado; `#CALIBRAR` compara fontes e verifica consistência. `UNKNOWN` nunca é `PASS`.

### `#GENESIS`
- **Aliases:** `#genesis`, `#Genesis`.
- **Owner:** [núcleo de Gênesis](../01-PENTATEUCO/01-GENESIS/00-MAPA.md).
- **Entrada:** `01-PENTATEUCO/01-GENESIS/00-MAPA.md`.
- **Relacionados:** `#DUDA`, `#IDENTIDADE`, `#HISTORIA`, `#FE`, `#SONHOS`.
- **Modo:** `READ_WRITE` conforme a intenção.

### `#IDENTIDADE`
- **Aliases:** `#identidade`, `#Identidade`.
- **Owner:** [Quem-sou-eu.md](../01-PENTATEUCO/01-GENESIS/01-MINHA-IDENTIDADE/Quem-sou-eu.md).
- **Entrada:** a nota de identidade.
- **Relacionados:** `#GENESIS`, `#HISTORIA`, `#SONHOS`.
- **Modo:** `READ_WRITE` conforme a intenção.

### `#HISTORIA`
- **Aliases:** `#historia`, `#Historia`.
- **Owner:** [Como-tudo-comecou.md](../01-PENTATEUCO/01-GENESIS/02-MINHA-HISTORIA/Como-tudo-comecou.md).
- **Entrada:** a nota de história.
- **Relacionados:** `#GENESIS`, `#IDENTIDADE`.
- **Modo:** `READ_WRITE` conforme a intenção.

### `#FE`
- **Aliases:** `#fe`, `#Fe`.
- **Owner:** [Meus-principios.md](../01-PENTATEUCO/01-GENESIS/03-MINHA-FE/Meus-principios.md).
- **Entrada:** a nota de fé e princípios.
- **Relacionados:** `#GENESIS`, `#BIBLIA`, `#SALVAR`.
- **Modo:** `READ_WRITE` conforme a intenção. Diferenciar estudo bíblico de reflexão pessoal.

### `#SONHOS`
- **Aliases:** `#sonhos`, `#Sonhos`.
- **Owner:** [Terapia-Ocupacional.md](../01-PENTATEUCO/01-GENESIS/04-MEUS-SONHOS/Terapia-Ocupacional.md) para o conteúdo atual.
- **Entrada:** nota de sonhos.
- **Relacionados:** `#TO`, `#IDENTIDADE`, `#HISTORIA`.
- **Modo:** `READ_WRITE` conforme a intenção. Sonhos são possibilidades, não decisões permanentes.

### `#TO`
- **Aliases:** `#to`, `#To`.
- **Owner:** [Terapia-Ocupacional.md](../01-PENTATEUCO/01-GENESIS/04-MEUS-SONHOS/Terapia-Ocupacional.md).
- **Entrada:** nota existente; propor owner próprio apenas quando o volume justificar.
- **Relacionados:** `#SONHOS`, `#SALVAR`, `#BUSCAR`.
- **Modo:** `READ_WRITE` conforme a intenção.

### `#SALVAR`
- **Aliases:** `#salvar`, `#Salvar`.
- **Owner:** definido pelo assunto; [mapa](00-MAPA-DA-MENTE.md) para roteamento.
- **Entrada:** procurar a nota canônica antes de criar.
- **Relacionados:** `#MAPEAR`, `#CONECTAR`, `#KAIZEN`.
- **Modo:** `WRITE` quando a solicitação pedir persistência. Sintetizar conhecimento útil; não copiar a conversa inteira por padrão.

### `#MICHELIN`
- **Aliases:** `#michelin`, `#MICHELIN`, `#Michelin`, `!michelin`, `!MICHELIN`, `!Michelin` e outras capitalizações.
- **Owner:** [08-MICHELIN-3-ESTRELAS.md](08-MICHELIN-3-ESTRELAS.md).
- **Entrada:** protocolo Michelin; reutiliza o mapa, os owners e o checkpoint existentes.
- **Relacionados:** todos os gatilhos especializados, especialmente `#DUDA`, `#ACORDAR`, `#CALIBRAR`, `#SALVAR`, `#KAIZEN` e `#PROXIMO`.
- **Modo:** `READ` para avaliar; `READ_WRITE` quando a intenção pedir integração, registro ou correção.
- **Critério:** ⭐ CONSTRUIR, ⭐⭐ INTEGRAR, ⭐⭐⭐ PROVAR. Estrelas conquistadas dependem de evidência; não atribuir percentual, XP ou progresso inventado.
- **Exibição:** usar o HUD apenas quando o método for solicitado, em `#CALIBRAR` ou quando houver pedido de avaliação de progresso.

### `#KAIZEN`
- **Aliases:** `#kaizen`, `#Kaizen`.
- **Owner:** [05-KAIZEN.md](05-KAIZEN.md).
- **Entrada:** protocolo Kaizen.
- **Relacionados:** `#SALVAR`, `#PROXIMO`.
- **Modo:** `READ_WRITE` conforme a intenção.

### `#MAPEAR`
- **Aliases:** `#mapear`, `#Mapear`.
- **Owner:** [00-MAPA-DA-MENTE.md](00-MAPA-DA-MENTE.md).
- **Entrada:** identificar o owner existente.
- **Relacionados:** `#SALVAR`, `#CONECTAR`, `#BUSCAR`.
- **Modo:** `READ` ou `READ_WRITE` se a intenção pedir alteração.

### `#CONECTAR`
- **Aliases:** `#conectar`, `#Conectar`.
- **Owner:** as notas envolvidas; sem duplicar conteúdo.
- **Entrada:** mapa e notas pertinentes.
- **Relacionados:** `#MAPEAR`, `#REVISAR`.
- **Modo:** `READ_WRITE` quando houver relação explicável.

### `#REVISAR`
- **Aliases:** `#revisar`, `#Revisar`.
- **Owner:** nota ou núcleo indicado.
- **Entrada:** conteúdo atual e links relacionados.
- **Relacionados:** `#MAPEAR`, `#CONECTAR`.
- **Modo:** `READ` para diagnóstico; `READ_WRITE` se a correção for solicitada.

### `#BUSCAR`
- **Aliases:** `#buscar`, `#Buscar`.
- **Owner:** mapa e notas relevantes.
- **Entrada:** procurar na biblioteca antes de recorrer a fontes externas.
- **Relacionados:** `#MAPEAR`, `#DUDA`.
- **Modo:** `READ`.

### `#PROXIMO`
- **Aliases:** `#proximo`, `#Próximo`, `#próximo`.
- **Owner:** [07-ESTADO-ATUAL.md](07-ESTADO-ATUAL.md).
- **Entrada:** checkpoint atual.
- **Relacionados:** `#ACORDAR`, `#KAIZEN`.
- **Modo:** `READ`; retornar uma ação concreta.

### `#BIBLIA`
- **Aliases:** `#biblia`, `#Bíblia`.
- **Owner:** [00-MAPA-DA-MENTE.md](00-MAPA-DA-MENTE.md).
- **Entrada:** arquitetura dos 66 livros planejados.
- **Relacionados:** `#GENESIS`, `#FE`, `#MAPEAR`.
- **Modo:** `READ_WRITE` conforme a intenção.
