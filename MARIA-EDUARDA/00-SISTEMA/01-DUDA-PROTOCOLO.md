# Protocolo mestre — #DUDA

```text
#DUDA = MASTER_TRIGGER
TRIGGER_CASE_SENSITIVE=false
TRIGGER_NORMALIZATION=UPPERCASE
TRIGGER_ROUTING=SEMANTIC
SOURCE_OF_TRUTH=GITHUB
REUSE_BEFORE_CREATE=true
ONE_CANONICAL_OWNER=true
NEXT_CURSOR_REQUIRED=true
```

## Ativação

Reconheça `#DUDA`, `#duda`, `#Duda` e outras combinações de maiúsculas e minúsculas como o mesmo comando quando usados para acionar o núcleo. A normalização também vale para os gatilhos especializados.

Não execute um gatilho apenas porque aparece como exemplo, dentro de documentação, citação ou bloco de código.

## Ciclo mestre

1. Ler o [README](../../README.md).
2. Ler o [mapa principal](00-MAPA-DA-MENTE.md).
3. Ler este protocolo e recuperar o [estado atual](07-ESTADO-ATUAL.md) quando a continuidade for relevante.
4. Entender a intenção atual.
5. Localizar o owner semântico.
6. Consultar somente as notas relacionadas.
7. Reutilizar o conteúdo que já existe.
8. Executar o menor delta necessário.
9. Validar gravações, destinos e links.
10. Apresentar o resultado e o `NEXT_CURSOR`.

## Regras de operação

- Quando a mensagem contiver somente `#DUDA`, recupere o estado e indique o próximo passo útil. Não altere arquivos sem uma intenção de escrita.
- Não leia o repositório inteiro por padrão. Use mapas e gatilhos para localizar o contexto necessário.
- Não invente memórias, fatos biográficos, crenças, experiências ou decisões.
- Diferencie conteúdo encontrado no GitHub, conhecimento externo e inferência.
- `UNKNOWN ≠ FACT`; `NÃO ENCONTRADO ≠ NÃO EXISTE`; `CRIADO ≠ VERIFICADO`; `ESCRITO ≠ SALVO`.
- Só declare uma gravação depois que a ferramenta confirmar a operação. Só declare verificação depois de ler o conteúdo salvo.
- Não crie agentes, robôs ou automações. Os gatilhos são comandos conversacionais.
- Se o conector não estiver disponível, informe isso claramente e não simule leitura ou escrita.

## Formato de resposta

Use somente os campos necessários:

```text
INTENÇÃO:
CURRENT:
OWNER:
DELTA:
PROVA:
NEXT_CURSOR:
```

Resultado primeiro. Explicação necessária depois.

## Protocolo canônico relacionado

- [Mapa da Mente](00-MAPA-DA-MENTE.md)
- [Gatilhos](02-GATILHOS.md)
- [Lei da Árvore](03-LEI-DA-ARVORE.md)
- [Modo Clareza](04-MODO-CLAREZA.md)
- [Kaizen](05-KAIZEN.md)
- [Estado atual](07-ESTADO-ATUAL.md)
