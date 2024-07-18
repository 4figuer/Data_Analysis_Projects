# Projeto de Estudo - Data Analysis

### Análise esportiva de jogadores jogo FIFA 2022

Desenvolvido por: Alan Figueroa



Neste projeto vamos analisar um conjunto de dados dos jogadores "Modo Carreira", do FIFA 2022, amplamente difundido para análise em plataformas de competições e de estudo, como o Kaggle. 

Os dados do jogo FIFA modem ser considerados como uma aproximação/representação dos dados estatísticos reais dos jogadores, mas não idênticos. A EA Sports, desenvolvedora da FIFA, coleta uma vasta quantidade de dados de observações e de analistas de futebol para definir os atributos dos jogadores, sendo atributos como drible, defesa, passes, do jogo, representados de maneira a refletir as habilidades reais dos jogadores. Além disso, o modo carreira coleta também informações de valores e salários, também refletindo os da realidade. Volto a disser que se trata de  generalizações criadas pela percepções dos analistas sobre um jogador.  

O conjunto analisado possui:

- 19.239 registros
- 110 Colunas (variáveis)

O link que usei para ter acesso aos dados foi este:  [link_dataset](https://www.kaggle.com/datasets/elreaper/football-data-analysis-for-2022?select=players_22.csv)



##### Objetivo deste projeto:

Realizar alguns insigths sobre:

- Verificar reputação dos jogadores ranking e distribuição
- Verificar habilidades e características dos jogadores
- Ensaios sobre a remuneração dos jogadores
- Apresentação dos TOP 10 jogadores, clubs, nacionalidades
- Resumo de alguns dados informativos



___

Abaixo apresento algumas informações sobre o que se trata algumas variáveis contidas no dataset, assim você tem uma melhor compreensão do conjunto.

##### Glossário Posições no Futebol:

- **RW (Right Winger)**: Ponta direita
- **ST (Striker)**: Atacante
- **LW (Left Winger)**: Ponta esquerda
- **RCM (Right Center Midfielder)**: Meio-campista central direito
- **GK (Goalkeeper)**: Goleiro
- **CF (Center Forward)**: Centroavante
- **CDM (Central Defensive Midfielder)**: Meio-campista defensivo
- **LCB (Left Center Back)**: Zagueiro central esquerdo
- **RDM (Right Defensive Midfielder)**: Meio-campista defensivo direito
- **RS (Right Striker)**: Atacante direito
- **LCM (Left Center Midfielder)**: Meio-campista central esquerdo
- **SUB (Substitute)**: Reserva
- **CAM (Central Attacking Midfielder)**: Meio-campista ofensivo
- **RCB (Right Center Back)**: Zagueiro central direito
- **LDM (Left Defensive Midfielder)**: Meio-campista defensivo esquerdo
- **LB (Left Back)**: Lateral esquerdo
- **RB (Right Back)**: Lateral direito
- **LM (Left Midfielder)**: Meio-campista esquerdo
- **RM (Right Midfielder)**: Meio-campista direito
- **LS (Left Striker)**: Atacante esquerdo
- **CB (Center Back)**: Zagueiro
- **RES (Reserved)**: Reserva
- **Não Informado**: Posição não especificada
- **RWB (Right Wing-Back)**: Lateral direito (com funções de ala)
- **RF (Right Forward)**: Atacante direito
- **CM (Center Midfielder)**: Meio-campista central
- **LWB (Left Wing-Back)**: Lateral esquerdo (com funções de ala)
- **LAM (Left Attacking Midfielder)**: Meio-campista ofensivo esquerdo
- **LF (Left Forward)**: Atacante esquerdo
- **RAM (Right Attacking Midfielder)**: Meio-campista ofensivo direito

##### Glossário Habilidades no Futebol:

Essas habilidades são usadas para avaliar e classificar as capacidades técnicas e físicas dos jogadores de futebol em diferentes aspectos do jogo.

- **Crossing**: Capacidade de cruzar a bola com precisão para a área adversária.
- **Finishing**: Habilidade de finalizar com precisão e eficiência as jogadas de gol.
- **Heading** **Accuracy**: Precisão ao cabecear a bola em direção ao gol ou para um companheiro de equipe.
- **Short** **Passing**: Habilidade de fazer passes curtos com precisão e controle.
- **Volleys**: Habilidade de finalizar a bola no ar, sem deixá-la cair no chão.
- **Dribbling**: Capacidade de driblar os adversários com habilidade e controle da bola.
- **Curve**: Habilidade de dar efeito à bola em passes, cruzamentos e chutes.
- **FK Accuracy**: Precisão ao bater faltas diretas ao gol.
- **Long Passing**: Habilidade de fazer passes longos com precisão e alcance.
- **Ball Control**: Habilidade de dominar a bola e mantê-la próxima ao corpo.
- **Acceleration**: Velocidade inicial para ganhar velocidade rapidamente.
- **Sprint Speed**: Velocidade máxima em corridas de alta intensidade.
- **Agility**: Agilidade e rapidez de movimento.
- **Reactions**: Capacidade de reagir rapidamente às situações em campo.
- **Balance**: Equilíbrio corporal ao driblar ou disputar a bola.
- **Shot Power**: Força nos chutes a gol.
- **Jumping**: Altura e força de salto.
- **Stamina**: Resistência física para manter o desempenho durante toda a partida.
- **Strength**: Força física para disputar a bola e enfrentar contatos físicos.
- **Long Shots**: Habilidade de finalizar de longa distância com precisão.
- **Aggression**: Determinação e vontade de disputar a bola e pressionar os adversários.
- **Interceptions**: Capacidade de antecipar e interceptar passes adversários.
- **Positioning**: Habilidade de se posicionar adequadamente em campo para criar oportunidades ou marcar os adversários.
- **Vision**: Visão de jogo para identificar espaços e oportunidades de passe.
- **Penalties**: Habilidade de converter penalidades com precisão.
- **Composure**: Calma e controle emocional em situações de pressão.
- **Marking**: Capacidade de marcar de perto e acompanhar um jogador adversário.
- **Standing Tackle**: Tackle em pé para recuperar a posse de bola.
- **Sliding Tackle**: Tackle deslizando no chão para recuperar a posse de bola.
- **GK Diving**: Habilidade do goleiro em se jogar para defender chutes a gol.
- **GK Handling**: Capacidade do goleiro de segurar e controlar a bola após uma defesa.
- **GK Kicking**: Habilidade de chutar a bola com precisão e distância como goleiro.
- **GK Positioning**: Capacidade do goleiro de se posicionar adequadamente em relação ao gol e à jogada.
- **GK Reflexes**: Reação e agilidade do goleiro para fazer defesas rápidas e instintivas.





No notebook eu realizer a criação das variáveis de habilidades de acordo com minha visão subjetiva das habilidades . Você pode criar os seus agrupamentos ou seguir o que subliminarmente o dataset ja informa.

Você pode agrupar as habilidades, exemplo, da seguinte forma: 
(Apenas uma sugestão, eu não segui a risca)

1. Habilidades de ataque:
   - Finishing
   - Heading Accuracy
   - Volleys
   - Curve
   - FK Accuracy
   - Long Shots
   - Shot Power
   - Penalties
2. Habilidades de passe:
   - Crossing
   - Short Passing
   - Long Passing
   - Vision
3. Habilidades de controle de bola:
   - Ball Control
   - Dribbling
4. Habilidades físicas:
   - Acceleration
   - Sprint Speed
   - Agility
   - Jumping
   - Stamina
   - Strength
5. Habilidades de defesa:
   - Aggression
   - Interceptions
   - Positioning
   - Marking
   - Standing Tackle
   - Sliding Tackle
6. Habilidades de goleiro:
   - GKDiving
   - GKHandling
   - GKKicking
   - GKPositioning
   - GKReflexes
7. Habilidades técnicas e mentais:
   - Reactions
   - Balance
   - Composure

Esses grupos são apenas uma sugestão e podem variar de acordo com a forma como você deseja analisar as habilidades dos jogadores de futebol.

