---
data_criacao: "2026-10-31T09:07:00-03:00"
ultima_atualizacao: "2026-10-31T09:07:00-03:00"
ultima_modificacao: "2026-10-31T09:07:00-03:00"
ultima_verificacao: "2026-10-31T09:07:00-03:00"
fuso_horario: "America/Bahia"
hash_conteudo: "fnv1a64-utf8:c8af4d5b95b4c01e"
rastro:
  origem: "conversa de desenvolvimento do projeto e requisito escolar informado pela usuária; vídeo de referência do IFSP"
  base_anterior: "6d195292b697302835f2d52117f0266c28cf1eb7"
  validacao: "Código de demonstração incluído; nota relida e integridade do corpo conferida após gravação."
  alteracao: "Registro canônico do protótipo Tinkercad, sensor, estimativa de volume e base futura para braço robótico 4 GDL."
grupo_notas: "EVANGELHOS-E-ATOS/ATOS/PROJETOS"
relacionado_a:
  - "MARIA-EDUARDA/00-SISTEMA/00-MAPA-DA-MENTE.md"
  - "MARIA-EDUARDA/00-SISTEMA/01-DUDA-PROTOCOLO.md"
  - "MARIA-EDUARDA/00-SISTEMA/02-GATILHOS.md"
  - "MARIA-EDUARDA/00-SISTEMA/03-LEI-DA-ARVORE.md"
  - "MARIA-EDUARDA/00-SISTEMA/05-KAIZEN.md"
  - "MARIA-EDUARDA/00-SISTEMA/07-ESTADO-ATUAL.md"
  - "MARIA-EDUARDA/00-SISTEMA/08-MICHELIN-3-ESTRELAS.md"
  - "README.md"
estado_evidencia: "EM_ANDAMENTO"
---

# 🤖 Projeto de braço robótico articulado — Tinkercad e 4 GDL

📅 **Criada em:** 31/10/2026 · ✏️ **Última atualização:** 31/10/2026

## Objetivo do registro

Reunir o desenvolvimento escolar do braço robótico articulado no Tinkercad e preservar a base para uma etapa futura: projetar e programar um braço robótico com quatro graus de liberdade (4 GDL). Esta nota é o owner principal do projeto. Atualizações futuras devem ser integradas aqui, sem criar cópias do mesmo conteúdo.

## Origem e requisito da atividade

Referência em vídeo: [Projeto de Robótica Industrial — Braço Robótico em Ação, IFSP Itapetininga, Grupo 4](https://www.youtube.com/watch?v=Ivr-kj7d0BQ).

A atividade solicita:
- criar um programa para controlar um braço robótico articulado conforme a movimentação apresentada no vídeo;
- usar um sensor de presença para identificar objetos e iniciar o programa de controle;
- informar qual sensor foi utilizado e onde foi instalado;
- calcular o volume de trabalho durante o movimento;
- considerar a altura da base de 6 cm e a distância de 2 cm entre a garra e o solo;
- estimar as dimensões dos elos conforme o projeto.

## Protótipo atual no Tinkercad

### Componentes escolhidos

- Arduino Uno R3 como controlador.
- Sensor ultrassônico HC-SR04 para detectar a presença de um objeto pela distância.
- Quatro servomotores no protótipo inicial.
- Estrutura articulada e garra, a serem representadas conforme a montagem mecânica disponível.

### Instalação do sensor

O HC-SR04 foi proposto na parte frontal da base, apontado para a área de coleta. No código de demonstração, a detecção ocorre quando a distância medida é igual ou inferior a 10 cm.

O HC-SR04 é um sensor de distância ultrassônico; ele funciona como detector de presença dentro de uma faixa configurada, não como sensor infravermelho.

### Ligações propostas

| Componente | Pino Arduino |
|---|---:|
| Servo da base | 9 |
| Servo do ombro | 10 |
| Servo do cotovelo | 11 |
| Servo da garra | 6 |
| HC-SR04 TRIG | 2 |
| HC-SR04 ECHO | 3 |
| VCC do sensor | 5 V |
| GND do sensor | GND |

Compartilhar o GND entre Arduino, sensor e alimentação dos servos. Em montagem física, dimensionar uma fonte externa adequada para os servomotores; não presumir que o pino de 5 V do Arduino suporte a corrente de todos eles.

### Sequência lógica demonstrada

1. O Arduino inicia os servos em posições de repouso.
2. O sensor mede a distância até a área de coleta.
3. Quando um objeto é detectado a até 10 cm, o programa inicia o ciclo.
4. O braço se posiciona para pegar a peça.
5. A garra fecha e segura o objeto.
6. A base gira em direção ao ponto de entrega.
7. A garra abre e libera a peça.
8. O braço retorna à posição inicial.
9. O programa aguarda o objeto sair da área de detecção antes de aceitar outro ciclo.

O código apresentado anteriormente usa posições angulares fixas e tempos de espera. Esses ângulos são apenas valores iniciais de simulação e precisam ser calibrados para a geometria real. A espera até o objeto sair da zona do sensor também é uma limitação: a lógica futura deverá evitar disparos repetidos e considerar a posição do objeto durante o transporte.

## Código atual de demonstração para Tinkercad

Este é o exemplo de partida para o circuito com HC-SR04 e quatro servos. Ele usa ângulos fixos, não cinemática inversa, e precisa ser ajustado à montagem real.

```cpp
#include <Servo.h>

Servo base;
Servo ombro;
Servo cotovelo;
Servo garra;

const int TRIG = 2;
const int ECHO = 3;
const int DISTANCIA_DETECCAO = 10;

long duracao;
float distancia;

void mover(int b, int o, int c, int g) {
  base.write(b);
  ombro.write(o);
  cotovelo.write(c);
  garra.write(g);
  delay(700);
}

float medirDistancia() {
  digitalWrite(TRIG, LOW);
  delayMicroseconds(2);
  digitalWrite(TRIG, HIGH);
  delayMicroseconds(10);
  digitalWrite(TRIG, LOW);

  duracao = pulseIn(ECHO, HIGH, 30000);
  if (duracao == 0) return 999;

  return duracao * 0.0343 / 2.0;
}

void posicaoInicial() {
  mover(90, 90, 90, 70);
}

void pegarObjeto() {
  mover(45, 110, 70, 70);
  mover(45, 125, 55, 70);
  mover(45, 125, 55, 110);
  mover(45, 90, 85, 110);
}

void transportarObjeto() {
  mover(135, 90, 85, 110);
  mover(135, 120, 60, 110);
  mover(135, 120, 60, 70);
  mover(135, 90, 85, 70);
}

void setup() {
  Serial.begin(9600);
  pinMode(TRIG, OUTPUT);
  pinMode(ECHO, INPUT);

  base.attach(9);
  ombro.attach(10);
  cotovelo.attach(11);
  garra.attach(6);

  posicaoInicial();
}

void loop() {
  distancia = medirDistancia();

  Serial.print("Distancia: ");
  Serial.print(distancia);
  Serial.println(" cm");

  if (distancia <= DISTANCIA_DETECCAO) {
    delay(200);

    if (medirDistancia() <= DISTANCIA_DETECCAO) {
      pegarObjeto();
      transportarObjeto();
      posicaoInicial();

      while (medirDistancia() <= DISTANCIA_DETECCAO) {
        delay(100);
      }
    }
  }

  delay(100);
}
```

## Atenção: definição correta dos 4 graus de liberdade

No protótipo inicial, os quatro servos foram associados à base, ombro, cotovelo e garra. Isso demonstra quatro atuadores, mas não garante quatro graus de liberdade de posicionamento: abrir e fechar a garra normalmente é uma ação do efetuador final, não necessariamente um eixo de posicionamento do braço.

Para o projeto definitivo, definir explicitamente os quatro movimentos independentes do braço (por exemplo: rotação da base, movimento do ombro, movimento do cotovelo e orientação do punho) e tratar a abertura/fechamento da garra como atuador do efetuador final. Se a convenção da atividade contar a garra como um dos quatro movimentos, registrar essa escolha e adaptar a arquitetura. A quantidade final de servos dependerá dessa definição e do mecanismo construído.

## Estimativa inicial do volume de trabalho

Dimensões estimadas para o exercício:
- altura da base: 6 cm;
- elo 1: 12 cm;
- elo 2: 10 cm;
- distância mínima da garra ao solo: 2 cm.

Alcance máximo simplificado dos dois elos, quando alinhados:

`R = L_1 + L_2 = 12 + 10 = 22\text{ cm}`

Altura geométrica máxima estimada:

`H_{max} = 6 + 12 + 10 = 28\text{ cm}`

Altura útil simplificada, descontando a distância mínima ao solo:

`H = 28 - 2 = 26\text{ cm}`

Volume do cilindro envolvente adotado como aproximação:

`V = \pi R^2H = \pi(22)^2(26) = 12\,584\pi \approx 39\,533\text{ cm}^3 = 39,53\text{ L}`

**Limite da estimativa:** 39,53 L é o volume do cilindro envolvente escolhido para o exercício, não o volume exato alcançável pelo braço. O espaço realmente acessível depende dos limites angulares, da posição das juntas, da orientação do punho/garra, das colisões e da geometria efetiva. O valor deverá ser recalculado quando as dimensões e os limites do modelo estiverem definidos.

## Base para o futuro código de 4 GDL

Esta atividade é um protótipo inicial, não o controlador final. Para evoluir:
1. definir a arquitetura mecânica e identificar os quatro eixos independentes;
2. medir os comprimentos reais de cada elo e a posição dos eixos;
3. definir limites mínimo e máximo de cada servo e calibrar os sentidos de movimento;
4. estabelecer posições de repouso, coleta, transporte e entrega;
5. converter posições desejadas em ângulos por cinemática adequada ao mecanismo;
6. integrar a leitura do HC-SR04 com filtragem, limiar e lógica de ciclo;
7. testar cada junta separadamente e depois a sequência completa;
8. verificar colisões, alcance e volume de trabalho com a geometria real.

Conceitos a conectar: Arduino/C++, servomotores, sensores ultrassônicos, eletrônica básica, geometria, trigonometria, cinemática direta e inversa, planejamento de movimento e simulação no Tinkercad.

## Conexões na biblioteca

- [Mapa principal da Mente](../../../00-SISTEMA/00-MAPA-DA-MENTE.md)
- [Protocolo mestre #DUDA](../../../00-SISTEMA/01-DUDA-PROTOCOLO.md)
- [Registro de gatilhos](../../../00-SISTEMA/02-GATILHOS.md)
- [Lei da Árvore Semântica](../../../00-SISTEMA/03-LEI-DA-ARVORE.md)
- [Kaizen](../../../00-SISTEMA/05-KAIZEN.md)
- [Estado atual](../../../00-SISTEMA/07-ESTADO-ATUAL.md)
- [Michelin 3 Estrelas](../../../00-SISTEMA/08-MICHELIN-3-ESTRELAS.md)
- [README da biblioteca](../../../../README.md)

## Estado do trabalho

- **CONSTRUIR:** protótipo conceitual, escolha do sensor, ligações e sequência básica documentados.
- **INTEGRAR:** base de cálculo e conceitos relacionados reunidos nesta nota.
- **PROVAR:** simulação completa, calibração mecânica, alcance real e controle de 4 GDL ainda precisam ser testados. Não considerar o braço definitivo concluído.

## Próximo passo

Definir a estrutura mecânica do braço de 4 GDL: quais são exatamente os quatro eixos de movimento, onde fica cada servo e se a garra terá um servo independente. Depois disso, elaborar a tabela de ângulos e o código de controle correspondente.
