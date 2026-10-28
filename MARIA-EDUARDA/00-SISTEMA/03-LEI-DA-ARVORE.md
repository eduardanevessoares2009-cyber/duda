# Lei da Árvore Semântica — Duda

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
