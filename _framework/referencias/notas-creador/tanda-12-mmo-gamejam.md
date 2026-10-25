Introdução
0:00
Eu criei um MMO de mundo aberto com
0:03
geração de mundo procedural infinito que
0:06
roda diretamente no navegador. Tudo isso
0:08
em apenas 30 dias porque eu decidi
0:11
participar de uma Game Gam que valia
0:13
25.000 pro primeiro colocado, ou melhor,
0:17
R$ 128.000.
0:19
No total, foram 945 jogos enviados e o
0:22
meu foi um deles. Se você quer saber
0:25
qual colocação eu fiquei, o processo
0:27
completo da criação do jogo, fica aí que
0:29
eu vou te mostrar tudo. Mas beleza,
A Game Jam
0:31
vamos começar do começo, né? Vou dar um
0:33
pouco mais de contexto do que se trata
0:35
essa Game Gem, de onde ela veio, qual o
0:38
propósito e tudo mais. Não sei se você
0:40
conhece, mas tem um carinha na gringa
0:42
que chama Peter Levels. Ele ficou famoso
0:44
porque ele fez muito SAR de sucesso e
0:47
ele compartilhava todo o progresso e seu
0:49
faturamento nas redes sociais. Ele
0:51
influenciou uma galera a seguir esse
0:53
mesmo movimento chamado Ind hacking, que
0:56
eu também participei, lancei os meus
0:58
produtos e deu super certo. Daí do nada
1:01
ele decidiu fazer uma parceria com um
1:03
curso e outros patrocinadores também
1:05
para criar uma Game Gam. E para quem não
1:08
sabe, uma Game Jam é um período
1:10
específico de tempo, onde vários
1:12
jogadores criam seus jogos e no final
1:14
eles são avaliados por uma banca de
1:16
jurados que decide quem vai ser premiado
1:19
ou não. A única regra dessa game era que
1:22
pelo menos 90% do jogo deveria ser feito
1:24
com IA no intervalo de 30 dias. Mas
1:28
calma, se você não curte a segura aí que
1:30
eu não segui o famoso vibe coding que
1:33
você deixa aí a tomar as decisões e
1:36
fazer o jogo do zero. Meu processo foi
1:38
totalmente diferente disso. Coloquei
1:40
técnicas reais de desenvolvimento de
1:42
jogos que já são utilizados aí há mais
1:44
de 20, 30 anos. Isso claramente saiu no
1:47
resultado final. Então com certeza você
1:49
vai aprender alguma coisa aqui nesse
1:51
vídeo. E por que eu sei todas essas
1:53
coisas? Bom, antes do surgimento da IA,
1:56
antes de todo mundo decidir fazer jogos
1:58
usando prompts, eu já criei os meus
2:00
próprios jogos, onde eu codei do zero,
2:02
estudei, pensei, sofri com a física e
2:06
matemática de tudo, mas no final eu
2:08
cheguei no resultado sem utilizar
2:10
inteligência artificial. Isso era
2:12
meiados de 2023 e eu já tava
2:14
compartilhando o progresso desses jogos
2:16
lá no Twitter. Isso faz total diferença
2:18
hoje porque me dá uma base sólida no
2:21
desenvolvimento de jogos, principalmente
2:23
quando se utiliza inteligência
2:24
artificial. Uma coisa é você falar: "E,
2:26
ah, me faça um jogo". Outra coisa
2:29
completamente diferente é você falar:
2:30
"Cria uma grama utilizando shaders com a
2:33
técnica de perlinis para criar o
2:35
movimento do vento. Um mostra a técnica
2:37
e o outro não." Beleza? A Game Jam não
Planejando o jogo
2:40
tinha uma temática em específico, ou
2:43
seja, eu poderia fazer um jogo sobre
2:45
qualquer coisa.
2:47
Então eu sentei e colocou no papel todas
2:49
as funcionalidades que eu gostaria que o
2:51
jogo tivesse. Mas uma única coisa que
2:53
não poderia faltar era que o jogo
2:55
chamasse atenção logo de cara. O que eu
2:57
queria causar nas pessoas era que elas
2:59
pensassem: "Poxa, isso roda no
3:01
navegador". E para isso seria
3:03
fundamental eu utilizar todas as
3:05
técnicas que eu já aprendi e também
3:07
outras que eu fui pesquisar durante esse
3:09
um mês de desenvolvimento. Muit das
3:12
vezes eu parava o que eu estava fazendo
3:13
para pesquisar sobre algo que eu tinha
3:15
que aprender para fazer e atingir o
3:17
resultado que eu queria. Então, assisti
3:19
muitos, muitos e muitos tutoriais de
3:22
game devs no YouTube. A maioria deles
3:24
sendo em engines mais tradicionais, como
3:27
a Unit, Godo e principalmente a Unreal,
3:30
que eles têm muitos tutoriais de como
3:32
fazer cenas bonitas igual essa daqui. E
3:35
o ponto principal que eu quero passar é,
3:37
no fim, uma engine é código. Eles
3:40
abstraem o código que roda por baixo dos
3:43
panos em apenas cliques. Então, se você
3:45
for parar para pensar, você consegue
3:47
reproduzir essas mesmas funcionalidades
3:49
em qualquer lugar, com tanto que esteja
3:52
apto a escrever o código. E foi
3:54
exatamente isso que eu fiz. Eu utilizei
3:57
inteligência artificial para recriar
3:58
todas essas técnicas que são utilizadas
4:00
em engines e jogos, só que no 3DS, que
4:03
roda no navegador. E só isso já me fez
4:06
passar na frente da grande maioria dos
4:08
participantes. Isso se refletiu
4:10
claramente quando eu postei o progresso
4:12
do meu jogo no Twitter e simplesmente
4:14
explodiu na gringa. Várias pessoas
4:17
elogiando, várias pessoas falando
4:19
exatamente o que eu queria que elas
4:20
falassem, perguntando: "Isso roda no
4:23
navegador?" E até o próprio organizador
4:25
da Game Jam, o Peter Levels, comentou
4:28
perguntando como que eu fiz para atingir
4:29
esse resultado. Ele também tinha o
4:32
costume de compartilhar os jogos que ele
4:34
mais gostavam para os seus 800.000
4:36
seguidores e o meu apareceu duas vezes.
4:39
Isso claramente mostrou que eu estava no
4:40
caminho certo, o que me deixou muito
4:43
empolgado e com muitas expectativas do
4:46
que eu poderia fazer nessa Kim Gam. Eu
Construindo o jogo
4:48
poderia mostrar cada técnica que eu
4:50
utilizei nesse jogo aqui nesse vídeo,
4:52
mas se eu fizesse isso, ele teria duas
4:54
horas de duração. Então vou fazer um
4:56
speed run aqui de todas as features que
4:58
eu mais gostei, compartilhando o
5:00
processo desde o início da criação do
5:02
jogo para vocês terem uma ideia de como
5:04
funciona e também pegar de inspiração
5:07
para aplicar no seu próprio jogo. O
5:09
principal diferencial aqui foi que ao
5:11
invés de pedir a IA para simplesmente
5:13
fazer a funcionalidade e eu aceitar ou
5:15
pedir ajustes dando o texto, que é muito
5:17
impreciso, eu sempre pedi a inteligência
5:19
artificial para criar um debugger, onde
5:22
eu poderia ajustar todos os parâmetros
5:24
de tudo que estava sendo feito. O que se
5:26
for parar para pensar é um processo
5:28
similar a uma engine de jogos também,
5:30
né? Então eu poderia ajustar a altura da
5:32
grama, a força e velocidade do vento e
5:35
etc. Então eu comecei fazendo o básico,
5:38
o terreno. Para isso, desde o início, eu
5:41
queria fazer um mundo infinito com
5:43
geração procedural estilo Minecraft. Ou
5:46
seja, não importa onde você for, sempre
5:49
vai ter uma parte do mundo gerada usando
5:51
programação. E para isso, eu usei uma
5:54
técnica chamada Perlin noise. É uma
5:56
técnica muito difundida no
5:58
desenvolvimento de jogos, que é
6:00
utilizada simplesmente para fazer tudo.
6:02
Ela foi descoberta por um cara chamada
6:04
Klin em 1983 e é amplamente usada na
6:08
computação gráfica no geral, jogos,
6:11
modelagens e até no cinema. Serve para
6:13
fazer grama, geração de terreno, geração
6:16
de fumaça, água e muitas outras coisas.
6:19
A ideia do perlinoise é simplesmente uma
6:22
função matemática que gera aleatoriedade
6:24
de forma fluida. Ou seja, se você criar
6:27
um script no seu computador para gerar
6:29
números aleatórios, o resultado vai ser
6:31
uma bagunça, com valores totalmente sem
6:34
lógica, de um pro outro, mas não no
6:36
perlim, porque cada valor tem uma
6:38
transição suave com seu vizinho. Ou
6:41
seja, se você colocar isso num plano e
6:43
definir que as partes brancas definem a
6:45
elevação do terreno, você consegue
6:47
formar montanhas. Na mesma lógica, se
6:50
você fizer esse mesmo padrão, se
6:51
movimentar e aplicar o vento nas partes
6:53
brancas, você consegue simular vento na
6:56
sua grama. É um tópico simples, mas
6:59
complexo, que te permite criar muitas e
7:01
muitas coisas mesmo. E por esse motivo,
7:03
o Kerlin ganhou o Oscar da tecnologia em
7:06
1997, porque o cara literalmente
7:09
revolucionou a computação gráfica com
7:11
essa técnica. E com terreno gerado,
7:13
chegou a hora de começar a popular ele
7:15
com informações. A primeira coisa que eu
7:17
fiz foi colocar grama. E a grama assim
7:20
que você coloca já dá uma diferença
7:22
total no seu cenário. É simplesmente
7:24
vários triângulos posicionados no chão
7:26
que se movimentam usando shaders,
7:29
aplicando a técnica do perlin noise
7:30
também. E para quem não sabe, um shader
7:33
é um código específico que roda na sua
7:35
GPU ou placa de vídeo, onde você pode
7:38
simplesmente manipular qualquer objeto
7:40
na cena que você tem. Tipo, esse
7:42
triângulo tem vértices, certo?
7:45
Basicamente no shader você consegue
7:47
reposicionar essas vértices utilizando o
7:49
código em tempo de execução do jogo para
7:51
fazer a grama se movimentar. Mas tem que
7:54
tomar muito cuidado com isso, porque
7:55
pode ficar muito pesado se você não
7:57
tomar cuidado. Computação gráfica é
8:00
pesado. Eu apliquei uma técnica que
8:03
geralmente já é padrão no mercado hoje.
8:05
A grama só renderiza perto do
8:07
personagem. Então, se você olhar lá na
8:09
frente, você consegue reparar que não
8:11
tem grama nenhuma, apenas na parte que o
8:14
personagem se movimenta. E o mesmo se
8:16
aplica no terreno. O mundo é infinito,
8:19
mas você não consegue ver ele o tempo
8:20
todo porque ele não está sendo
8:22
processado. Eu sei que parece complexo e
8:25
é um pouquinho, você precisa dar uma
8:26
estudada. E o ponto positivo da IA foi
8:29
que ela conseguiu implementar isso de
8:31
forma bem tranquila. Beleza? Depois veio
8:34
as árvores e elas têm uma técnica bem
8:37
legal também, são alfa maps. Por baixo
8:40
dos panos é uma lógica parecida com
8:42
perlinoides, porém a gente aplica
8:45
diretamente a um objeto, geralmente um
8:48
plano. É simples. Onde é branco, a gente
8:51
fala para GPU manter renderizando e na
8:54
parte preta a gente exclui. Então, com
8:56
isso a gente consegue girar folhas,
8:58
vegetação e tudo mais. Pensa num plano
9:01
verde. A gente aplica esse alfa map em
9:03
cima e a gente tem as nossas folhas. Daí
9:06
é só colocar várias dessas em paralelo
9:09
que vai se formando uma árvore. Legal,
9:12
né? Depois só juntar tudo e posicionar
9:14
no cenário. Mas eu percebi que o cenário
9:16
ainda tava muito sem nada, então eu
9:18
coloquei esses arbustos também
9:20
utilizando as mesmas folhas das árvores.
9:23
Beleza, o cenário já estava bom, já
9:26
tinha geração infinita de terreno, já
9:28
tinha árvores, grama, mas se você
9:30
reparar, parece que ainda falta algo,
9:33
parece que está faltando vida no
9:35
cenário, sabe? E para resolver isso, eu
9:37
tenho uma técnica muito legal que se
9:39
chama verticalização.
9:41
Se você reparar, cenários bonitos
9:42
geralmente tem uma coisa em comum.
9:44
Geralmente ele tem pontos altos, como
9:47
montanhas, rochas, pedras, faz o jogador
9:51
querer pensar: "Quero ir para lá". E foi
9:54
isso que eu fiz. Eu gerei dois modelos
9:56
de rochas e espalhei elas aleatoriamente
9:59
no terreno e o resultado foi esse. E
10:01
para trazer ainda mais vida no jogo, eu
10:03
coloquei um ciclo de dia e de noite,
10:06
efeitos de pós-prococessamento para
10:07
deixar ele ainda mais bonito e apliquei
10:10
também um efeito cartoon. Agora o
10:13
personagem, eu confesso que ele ficou um
10:15
pouco bugado. Eu também utilizei
10:17
inteligência artificial para gerar esse
10:18
personagem, mas por algum motivo ele
10:21
ficou com esse braço bugado aí. Então eu
10:23
pensei lá no final eu corrijo, mas como
10:26
vocês devem imaginar não deu tempo e
10:29
ficou assim mesmo. E uma coisa que eu
10:31
queria muito colocar também inspirada no
10:33
Zelda Breath of the Wild é que o
10:35
personagem pudesse escalar nas coisas.
10:38
Porque lembra do que eu falei? Aquela
10:39
sensação de quero ir para lá.
10:42
Agora o jogador tinha essa sensação no
10:43
meu jogo. Então tem essas montanhas, eu
10:46
queria permitir que ele pudesse subir
10:47
elas. Então, depois de um bom trabalho
10:50
em alguns prompets, eu consegui chegar
10:52
nesse resultado. Não é perfeito, mas
10:54
vende a ilusão direitinho. Eu fiquei
10:56
satisfeito e eu fiquei tão esperado
10:58
nessa funcionalidade escalar que eu quis
11:00
levar ainda mais adiante. Eu quis
11:02
aplicar a técnica do inverse kinematics.
11:05
O Inverse Kinematics é basicamente fazer
11:08
com que o seu personagem, mais
11:10
especificamente o esqueleto dele, reaja
11:12
conforme o ambiente. A forma mais básica
11:15
de aplicar o Inverse Kinematics é no pé
11:17
do personagem. Se você não aplicar,
11:19
geralmente quando você sobe um morro, o
11:21
pé do personagem fica meio flutuando, o
11:23
que é meio irrealista. Originalmente eu
11:26
queria aplicar essa técnica na mão do
11:28
personagem para ele posicionar a mão
11:30
exatamente onde ele deveria escalar, mas
11:33
essa parte foi realmente difícil, estava
11:36
perder muito tempo, então eu deixei o
11:38
Invest Camatics só pro pé do personagem
11:40
mesmo. Eu sei que não ficou perfeito,
11:42
mas tá aí um detalhe super legal para
11:44
quem gosta desses conteúdos técnicos,
11:47
OK? O mundo tava pronto, o personagem
11:49
tava pronto, tudo no jeito. Agora
11:52
faltava algo crucial pro jogo, que é o
11:54
que faz um jogo ser um jogo, um
11:56
objetivo. Eu tinha todo esse mundo para
11:59
explorar, mas não tinha o que fazer.
12:01
Então comecei a implementar o sistema de
12:03
sobrevivência. A ideia inicial era que o
12:06
jogador passasse fome, tivesse que
12:08
coletar recursos, construir sua casa e
12:11
também enfrentar inimigos. Eu consegui
12:13
implementar boa parte disso, mas não
12:15
tudo, o que acabou pesando muito no
12:18
final. E eu vou explicar o porquê.
12:20
Então, eu implementei o sistema de
12:22
construção. Agora você poderia construir
12:24
sua casa, colocar rampas, paredes,
12:27
chãos, teto, portas, baús, fogueira e
12:30
etc. Também coloquei essas vaquinhas aí
12:32
para você coletar os recursos e também
12:34
implementei o que faz o jogo ser um MMO,
12:37
o multiplayer. E essa parte, meus
12:39
amigos, deu muita dor de cabeça. Mas
12:42
aqui, se você tá nesse vídeo até agora,
12:44
quer dizer que você tá gostando, né?
12:46
Então, acho que rola dar aquele like e
12:47
se inscrever aí. Valeu demais. Bom,
A semana final
12:51
agora vamos falar do final, né? E o que
12:53
falar desse final? caótico. Desde a
12:56
parte de entregar o jogo até depois da
12:58
game ter acabado, faltava mais ou menos
13:00
uma semana para entrega e eu ainda tinha
13:03
muitas coisas para implementar,
13:05
incluindo o multiplayer. Então eu que
13:07
estava todo iludido, achando que ia
13:08
entregar o jogo perfeito, exatamente
13:10
aquele que eu tinha na minha cabeça,
13:12
comecei a lidar com o fato que eu teria
13:14
que cortar muita coisa. Então eu cortei
13:16
os inimigos que teriam no jogo, cortei o
13:18
combate avançado com arc flash, que eu
13:20
acho que seria muito legal, cortei
13:22
eventuais habilidades especiais que o
13:24
jogador ia liberar, roupas e armaduras
13:26
diferentes também, enfim, muita coisa
13:28
ficou de fora, mas uma coisa que não
13:30
podia faltar era o multiplayer, que era
13:32
o principal de tudo. Então eu
13:34
implementei utilizando Coliseus, é uma
13:37
biblioteca que facilita bastante na hora
13:40
de implementar multiplayer com Node JS.
13:43
Inclusive o criador é brasileiro. Eu
13:45
tive a oportunidade de encontrar ele lá
13:46
na Gamescom. Então abraço aí pro Wendel
13:49
que fez uma biblioteca muito boa e
13:51
acelerou bastante o processo. Mas ainda
13:53
assim implementar multiplayer é um
13:55
processo bem difícil. Você tem que lidar
13:58
com sincronização dos jogadores, lag,
14:00
ping alto, hacks, scripts que vão
14:03
derrubar o servidor, enfim, tem muita
14:05
coisa e valeria um vídeo só para isso.
14:07
Então você já percebeu que a lógica não
14:09
bate, né? uma semana para implementar um
14:11
multiplayer complexo com combate e
14:14
inventário compartilhado. Ou seja, se um
14:17
jogador morresse, ele teria que deixar
14:19
os seus itens no cenário e todos os
14:21
outros jogadores teriam acesso a esses
14:23
itens e a partir do momento que alguém
14:25
pegasse, ele sumiria para todos os
14:27
outros. Sem falar nas construções, as
14:30
vacas, enfim, tudo tinha que estar
14:32
sincronizado de forma perfeita e sem
14:34
bugs. E bom, teve muitos bugs. Eu fiquei
14:37
a semana inteira implementando,
14:39
corrigindo e ajustando. Cara, eu tive
14:42
que ficar até o último dia da Game DM,
14:44
até às 4 horas da manhã, corrigindo
14:46
esses bugs que não paravam de aparecer.
14:48
Eu só podia utilizar a inteligência
14:50
artificial para fazer esse jogo. E nessa
14:52
altura do campeonato ela já tava ficando
14:54
doida. Porque para quem não sabe, quanto
14:56
mais código o seu jogo tem, maior
14:59
contexto e mais dificuldade a IA tem
15:01
para entender tudo e executar os seus
15:03
promps da forma correta. No início, ela
15:06
começa perfeita. A Code base é pequena,
15:09
é fácil de entender, fácil de
15:10
implementar, mas no final é caos. E para
15:13
piorar a situação, na última semana eu
15:16
fui convidado a participar da GamesC que
15:18
teve em São Paulo, que é o último vídeo
15:20
aqui do canal. Estava lá eu no meio da
15:22
GamesC implementando o multiplayer do
15:24
meu jogo e pronto, a Game Jan tinha
Esperando o resultado
15:26
acabado. Eu enviei meu jogo, fui dormir
15:29
porque ninguém é de ferro e agora é só
15:31
esperar os resultados. Mas a comunidade
15:33
estava bem ativa e um usuário do Twitter
15:36
criou uma plataforma muito legal, onde
15:38
todo mundo poderia avaliar os jogos de
15:40
todo mundo. Então 945 jogos foram
15:43
listados lá e você pode entrar e dar uma
15:46
avaliação de uma a cinco estrelas. O meu
15:49
jogo estava muito bem posicionado.
15:51
Muitas pessoas estavam falando dele e
15:53
colocando ele como um dos favoritos para
15:55
ganhar. Porém, isso não se refletia nas
15:57
notas desse site. As primeiras
15:59
avaliações parece que vieram de quem
16:01
queria zoar com o meu jogo. Muitas
16:03
avaliações com uma estrela e muita gente
16:05
comentando o mesmo comentário. Muitos
16:08
glitch, o que era curioso porque o jogo
16:10
não tinha tantos glitches assim. Mas aos
16:13
poucos isso foi mudando. Boas avaliações
16:15
começaram a aparecer e o meu jogo foi
16:18
subindo. E ele terminou as avaliações em
16:20
primeiríssimo lugar dentre os 945 jogos.
16:24
uma média de 4.6 estrelas em 310
16:27
avaliações. Mas eu tenho que ser justo
16:30
aqui. Eu compartilhei sobre o jogo em um
16:32
vídeo que eu fiz aqui e muita gente do
16:35
canal foi lá avaliar o jogo. Então, com
16:37
certeza isso teve um impacto positivo
16:39
nas avaliações. E, aliás, obrigado a
16:41
todo mundo que foi lá votar. Vocês são
16:43
bravos. E bom, chegou um momento
16:45
crucial. Chegou o momento de esperar o
16:48
resultado. E esse resultado demorou,
16:50
viu? Ele estava previsto para sair em 15
16:53
dias. Mas acabou demorando dois meses. E
16:56
para quem estava na expectativa de
16:58
ganhar, essa espera foi muito difícil.
17:01
Todo dia, toda hora tava lá eu
17:03
atualizando Twitter para ver se já tinha
17:05
saído. E relembrando, o primeiro ia
17:08
ganhar $5.000,
17:10
o segundo 10.000 e o terceiro cinco. E a
A avaliação
17:13
avaliação foi definida da seguinte
17:14
forma, e eu ter três etapas. A primeira,
17:18
o organizador Peter Levels e outro
17:20
jurado, ambos especialistas em vibe
17:22
coding, iriam jogar os 945 jogos e eles
17:27
iriam classificar eles como simplesmente
17:29
gostei ou não gostei. Os jogos que os
17:32
dois marcaram como gostei passavam pra
17:35
próxima etapa. E a cada etapa, a cada
17:37
atualização, o Peter Lev estava
17:40
atualizando no seu Twitter e ele
17:42
compartilhou que 100 jogos foram
17:44
selecionados pra segunda etapa. e eu
17:46
tinha certeza que o meu jogo estava ali.
17:48
A segunda etapa também seria avaliada
17:50
pelos dois, só que dessa vez eles iriam
17:53
jogar os top 100 jogos de forma mais
17:55
dedicada e dariam uma nota de zer a 10
17:58
para cada. Os top 30 seriam selecionados
18:01
para ir pra etapa três. E essa etapa
18:04
seria ainda mais rigorosa do que as duas
18:06
primeiras, porque quatro desenvolvedores
18:08
jogos profissionais iriam avaliar esses
18:11
jogos. E bom, paraa minha sorte, um
18:13
desses jurados decidiu fazer uma live
18:15
avaliando os top 30 jogos ao vivo e
18:19
dando nota para cada um deles. E eu não
18:21
tinha outra escolha a não ser pegar o
18:23
meu chá e assistir essa live. Então eu
18:26
fui assistindo bem polgado, jogo a jogo,
18:29
vendo a avaliação de cada um em tempo
18:30
real. E alguns jogos aqui realmente
18:33
mereciam estar no top 30, são muito
18:35
bons. Outros eu achei meio estranhos,
18:38
mas tudo bem. Com tanto meu jogo
18:40
estivesse ali, eu estava feliz demais,
18:42
porque se ele tivesse no top 30,
18:44
significaria que ele não foi
18:46
desqualificado ainda e ainda tinha
18:48
chance de ganhar o prêmio. E um a um, os
18:51
jogos foram sendo avaliados, 5, 10, 15,
18:55
20 jogos. chegou no 20º e meu jogo ainda
18:58
não tinha aparecido, o que começou a me
19:00
deixar um pouco preocupado. Depois foi
19:03
25, 26, 27 jogos e nada do meu. O
19:08
nervosismo já tava insano. Se o meu jogo
19:11
fosse o último, seria o roteiro perfeito
19:14
para esse vídeo aqui, né? Então foi 28,
19:17
29,
19:19
30. Meu jogo não tava no top 30. E cara,
19:23
isso acabou comigo. 30 dias investidos
19:25
nesse jogo e o meu jogo não foi
19:28
selecionado nem nos top 30. Isso gerou
19:31
um questionamento muito grande e não só
19:33
para mim. Muitas outras pessoas foram no
19:35
Twitter levantar esse mesmo ponto.
19:37
Muitos jogos que não estavam no top 30
19:40
eram jogos muito melhores do que alguns
19:43
que foram selecionados. Eu tenho que
19:44
tomar muito cuidado aqui para não soar
19:46
como aquela pessoa que perdeu e tá
19:48
xingando o resultado, mas eu tenho que
19:50
ser justo. O modelo de avaliação dessa
19:52
Game Gam foi um pouco estranho, porque
19:55
duas pessoas que não t experiência em
19:57
desenvolvimento de jogos cortaram
20:00
literalmente 900 jogos da avaliação de
20:03
quem realmente entende. Isso foi o
20:04
principal fator pelo qual o pessoal
20:06
reclamou. Eles responderam esses
20:08
questionamentos falando que o principal
20:10
fator foi a diversão e não o polimento.
20:14
Cada um vai ter sua opinião e faz
20:15
sentido. Só que a minha é a seguinte, eu
20:18
não concordo muito e achei que esse
20:20
resultado foi muito desbalanceado. Um
20:22
jogo tem vários aspectos, como
20:24
ambientação, cenário, gráfico, gam play,
20:28
diversão, várias outras coisas. e pegar
20:32
só um desses parâmetros, que é o da
20:34
diversão, e julgar todos os jogos em
20:36
cima disso, com certeza o resultado vai
20:39
ser desbalanceado. Eu sei que o meu jogo
20:41
não é o mais divertido da lista, mas ele
20:43
tem muitos pontos positivos que foram
20:45
simplesmente ignorados. Eu não quero
20:47
falar mal do jogo de ninguém aqui,
20:49
porque todo mundo se dedicou e enviou
20:51
seu jogo, que é o mais difícil, mas com
20:54
certeza tem muitos jogos que são dignos
20:56
de estarem no top 30 e outros que estão,
20:59
mas não deveria. Mas essa minha opinião,
21:02
cada um vai ter a sua. Mas dado isso, eu
21:04
decidi fazer uma coisa. Eu fui
21:06
diretamente nesse seu jurado que fez a
21:08
live avaliando os jogos e mandei o meu
21:11
jogo sem pretensão, pedindo ele para
21:13
avaliar e dar uma nota. E cara, foi a
21:16
reação que eu estava esperando. Ele
21:18
falou que o meu jogo era muito bom e que
21:20
realmente deveria estar no top 30. E a
21:22
nota que ele deu, curiosamente, colocava
21:25
o meu jogo no top 10, talvez até no top
21:28
3. E ao saber disso, eu fiquei muito
21:31
chateado, porque dependendo do jurado
21:33
que tivesse avaliado o meu jogo antes,
21:35
eu estaria muito melhor posicionado. Mas
Os vencedores
21:37
bom, vocês estão querendo saber quem
21:39
ganhou, né? Então vamos até a
21:41
curiosidade de vocês e compartilhar os
21:43
top três jogos. O terceiro colocado foi
21:45
o Wware. Meio difícil de pronunciar, um
21:48
jogo estilo Geogesser, mas a diferença é
21:51
que o lugar onde você é colocado é um
21:53
ambiente histórico de determinada época.
21:56
Você pode ser colocado no Japão medieval
21:59
em Nova York da década de 50, no Brasil
22:02
na época dos índios e essa imagem é
22:05
feita com inteligência artificial, então
22:07
se encaixa na categoria da Game Gen. E
22:09
esse jogo literalmente explodiu a bolha,
22:12
ele viralizou, ele pegou mais de 1
22:14
milhão de gameplays e o criador desse
22:16
jogo ganhou $.000. Agora o segundo
22:20
colocado foi o Phantom Megaart, um jogo
22:23
super polido, onde o seu objetivo é
22:25
pegar itens no supermercado mais rápido
22:28
do que o seu adversário. Era basicamente
22:30
isso, simples, mas muito bem feito e
22:33
divertido. Ganhou.
22:35
E o primeiro colocado que também quebrou
22:37
a bolha e para mim foi super mega
22:39
merecido foi o Cap Bowers Delivering
22:42
Fruit, um jogo feito por um brasileiro
22:44
chamado Léo, que criou esse jogo super
22:47
temático, onde você é uma capivara que
22:50
trabalha pro iFood. O cenário é super
22:52
bem feito, tem esse estilo retrô de PS1
22:55
e tem uma vibe muito boa de jogar.
22:58
Também viralizou fora da bolha e teve
23:00
muitos gameps e TikTok virais. Ganhou.
23:05
ou como é brasileiro, R$ 128.000.
23:09
Parabéns, Léo. Eu não conheço ele, mas
23:11
se ele quiser dar um alô aí nos
23:12
comentários, vai ser muito massa. E logo
23:14
após que o resultado dos vencedores foi
23:16
anunciado, também veio uma série de
23:18
bonificações extras que não estava
23:20
planejado. Eles anunciaram 12 premiações
23:23
e os vencedores iriam ganhar $. 1.000
23:26
cada. E essas foram as categorias e os
23:29
vencedores. O jogo mais original, o jogo
23:32
mais jogado, o jogo mais zen, o jogo
23:35
mais louco, o jogo mais engraçado, o
23:38
jogo mais polido, o jogo mais único, o
23:42
jogo com melhor atmosfera, o jogo mais
23:44
estranho, o jogo mais raid kit, o jogo
23:47
que recebeu maior número de jogadores
23:50
pelo portal e o jogo com melhor direção
23:52
de arte. E não, meu jogo não ganhou
23:56
nenhum deles. Eu sei que o meu jogo não
Considerações finais
23:58
ficou perfeito, mas eu fiquei muito
23:59
feliz com o meu desempenho, fiquei feliz
24:01
com o resultado e também fiquei feliz
24:04
com o feedback que eu recebi do pessoal.
24:06
Muita gente no Twitter falou que o meu
24:08
jogo deveria ter ficado no top três e
24:10
isso é muito legal de se ouvir. E eu
24:12
acho que eu consegui mostrar que com
24:13
inteligência artificial você até que
24:15
consegue fazer algo bem rápido se você
24:17
souber aplicar boas técnicas de
24:20
desenvolvimento de jogos. Eu ainda não
24:22
sei o que que eu vou fazer com esse jogo
24:24
agora que a game acabou, mas dependendo
24:27
do que eu decidir, vocês vão ficar
24:28
sabendo aqui no canal. Comenta aí se
24:30
você tem alguma sugestão para ele. E
24:33
claro, o link para jogar vai tá aí na
24:35
descrição e eu estou sempre aberto a
24:37
feedbacks. E essa foi minha experiência
24:39
participando de uma game gen de 30 dias.
24:41
Se você gostou, não esquece de deixar o
24:44
like, se inscrever e mandar para aquele
24:46
amigo que você sabe que vai gostar desse
24:48
vídeo. Isso faz muita diferença aqui pro
24:50
canal. E é isso, tamo junto até a
24:52
próxima. Falou.
