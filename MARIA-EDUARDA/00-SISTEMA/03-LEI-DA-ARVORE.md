---
data_criacao: "2026-10-28T17:03:37-03:00"
ultima_atualizacao: "2026-10-28T18:03:30-03:00"
ultima_modificacao: "2026-10-28T18:03:30-03:00"
ultima_verificacao: "2026-10-28T18:03:30-03:00"
fuso_horario: "America/Bahia"
hash_conteudo: "fnv1a64-utf8:300cd0ecbaee6e70"
rastro:
  origem: "historico de commits GitHub"
  base_anterior: "4d247d8bca4ee32ddad43dfa924b236de3cb414e"
  alteracao: "Inclusão de propriedades completas e datas visíveis em 2026-10-28"
grupo_notas: "SISTEMA"
relacionado_a:
  - "MARIA-EDUARDA/00-SISTEMA/00-MAPA-DA-MENTE.md"
  - "MARIA-EDUARDA/00-SISTEMA/01-DUDA-PROTOCOLO.md"
  - "MARIA-EDUARDA/00-SISTEMA/02-GATILHOS.md"
  - "MARIA-EDUARDA/00-SISTEMA/04-MODO-CLAREZA.md"
  - "MARIA-EDUARDA/00-SISTEMA/08-MICHELIN-3-ESTRELAS.md"
estado_evidencia: "UNKNOWN"
---

# Lei da Árvore Semântica — Duda

📅 **Criada em:** 28/10/2026 · ✏️ **Última atualização:** 28/10/2026
🔎 **Última conferência:** 28/10/2026

## Invariantes

```text
NUMBERING_SCHEME=00..09
MAX_CHILD_DIRECTORIES_PER_FOLDER=10
DEPTH_LIMIT=NONE
DEPTH_MUST_BE_SEMANTIC=true
NUMBER_IS_STABLE_ADDRESS=true
NAME_CARRIES_MEANING=true
REUSE_BEFORE_CREATE=true
ONE_SYSTEM_ONLY=true
ONE_CANONICAL_OWNER=true
NO_DUPLICATE_MATERIAL=true
NO_PARALLEL_FOLDER_FOR_SAME_SEMANTIC=true
NO_RENUMBERING_FOR_AESTHETICS=true
```

## Endereço e significado

O número é um endereço estável dentro da hierarquia. Não representa importância, nota ou ranking. O nome comunica o conteúdo. Não renumere uma pasta apenas para melhorar a aparência.

Use `00` preferencialmente para mapa, índice ou navegação. Use `01` a `09` para os conteúdos seguintes quando a numeração ajudar a orientar.

## Crescimento semântico

- Cada pasta tem uma função clara.
- Reutilize o owner existente antes de criar outro.
- Mantenha um único local principal para cada conhecimento.
- Crie links para relações reais; não copie o mesmo material para várias notas.
- Não há limite fixo de profundidade. Crie níveis quando o significado exigir.
- Procure manter até dez subpastas diretas por pasta. Se o limite for alcançado, encontre o owner semântico correto; não crie irmãos automaticamente.
- Não crie pastas vazias para completar sequências.

## Reconciliação de conteúdo

```text
IDENTIFICAR
→ COMPARAR
→ LOCALIZAR OWNER
→ PRESERVAR CONTEÚDO ÚNICO
→ FUNDIR COMPLEMENTOS
→ VALIDAR DESTINO
→ ATUALIZAR LINKS
→ LIMPAR ORIGEM RECONCILIADA
```

Não exclua conteúdo sem confirmar que ele foi preservado no destino. Nomes iguais não provam que dois arquivos contêm a mesma informação. Nomes diferentes também não justificam duplicação.

## Uso na biblioteca

A estrutura bíblica é uma arquitetura de navegação. Ela não deve alterar o significado dos textos bíblicos nem impor associações pessoais a Maria Eduarda. Planeje os 66 livros no mapa e materialize novos núcleos somente quando existir conteúdo real.

## Referências

- [Mapa da Mente](00-MAPA-DA-MENTE.md)
- [Protocolo mestre](01-DUDA-PROTOCOLO.md)
- [Gatilhos](02-GATILHOS.md)

## 🔗 Conferir relações antes de modificar notas

PROIBIDO editar às cegas. Antes de alterar qualquer nota, ler a nota atual, seu mapa, links de saída, links de entrada identificáveis e dependências relevantes. Identificar pendências ligadas ao assunto, contradições, duplicatas e histórico; não reescrever indiscriminadamente todas as notas consultadas. Se uma relação indispensável não puder ser conferida, suspender apenas a mudança afetada. Após autorização: menor alteração → conferir conteúdo salvo → conferir links afetados → registrar resultado.

Preservar data de criação comprovada; separar última modificação de última verificação; não inventar datas, hashes, fontes nem evidências. Guardar metadados e provas nos documentos internos, sem poluir a conversa. Regras: NO_BLIND_NOTE_UPDATE; NO_UNCHECKED_RELEVANT_DEPENDENCIES; NO_DUPLICATE_PERSONAL_MEMORY; NO_INVENTED_PERSONAL_FACTS; NO_UNVERIFIED_SAVE_CLAIMS; NO_UNRELATED_NOTE_REWRITE.

## 📅 Propriedades completas obrigatórias — notas atuais e futuras

**É proibido criar ou atualizar uma nota sem as propriedades completas.** Antes da gravação, preencha `data_criacao`, `ultima_atualizacao`, `ultima_modificacao`, `ultima_verificacao`, `fuso_horario`, `hash_conteudo`, `rastro`, `grupo_notas`, `relacionado_a` e `estado_evidencia` no início de cada Markdown (frontmatter YAML). Logo após o título, apresente **📅 Criada em** e **✏️ Última atualização**, e a data de conferência quando útil. Cada nova nota herda esta obrigação, inclusive mapas e índices.

A criação original não deve mudar quando a nota for movida. Recupere-a do histórico; se não for comprovável, registre `desconhecido` em vez de inventar data. `ultima_atualizacao` marca o registro mais recente de atualização; `ultima_modificacao` só muda quando o texto/conteúdo efetivamente mudou; `ultima_verificacao` registra uma conferência realmente feita. Conferir, por si só, não é modificar. O hash `fnv1a64-utf8` é calculado sobre o corpo Markdown após o frontmatter, em UTF-8; é uma verificação simples de integridade, não um hash criptográfico. O próprio frontmatter fica fora desse cálculo para evitar circularidade.

Antes de modificar, consulte a nota, seu mapa, ligações relevantes e pendências relacionadas. Após salvar, releia e confira as propriedades, o hash e os links. Não declare três estrelas nem estado PASS sem confirmação. As propriedades técnicas não devem aparecer nas respostas comuns para Duda.
