#Librino

Jogo de associação que contribui com o processo de alfabetização de crianças deficientes auditivas. O jogo possui um display com palavras de fácil compreensão e cartas com os sinais dessas palavras em libras. Uma palavra aparecerá no display, e o objetivo será aproximar a carta que corresponda ao texto. Em caso de acerto, as LEDs acenderão e ficarão verdes, no contrário, serão vermelhas.

##Circuito

1. Conexão do RFID:
Para conectar o leitor RFID é bastante simples, é só conectar o SDA e SCK respectivamente no pino 10 e 13, o MOSI e o MISO vão no 11 e 12, e o RST vai para o pino 9 . E por fim o GND vai no GND e o 33V vai no 33V, o IRQ não vai em ninguém mesmo.

2. Conexão do display:
E para conectar o display é mais fácil ainda, conecte o SDA e o SCL nos pinos A4 e A5. O GND vai no GND e o VCC no 5 volts. 

3. Conexão dos LEDs:
 Leds Verdes:4 e 5
 Leds Vermelhos:2 e 8

##Preparando

1. Instalando as bibliotecas:
Ainda falta instalar duas bibliotecas necessárias do leitor e do display em sua máquina para funcionar. Para instalá-las, abra a IDE do arduino, vá para:
Sketch" >  Incluir biblioteca > Gerenciar bibliotecas
e procure por “MFRC522” (do RFID)  e ”Liquidcrystal 12C” (do display LCD I2C). E clique para finalmente instalar 


##Carregando o código

Primeiro conecte seu arduino ao computador, abra a IDE e copie e cole o código no arquivo “sketch_arduino” aqui no github. Em seguida selecione a placa correta (Arduino Uno) e a porta correta, clique para carregar o código do computador para o arduino. Uma vez baixado para o arduino, pode desconectar do computador pois equipamos uma bateria

##Cadastrando os cards para o RFID

Agora com o código já implementado,primeiramente  use o código no arquivo “DumpInfo MFRC522 Library” para ser possível identificar os IDs dos cartões.
Feito isso deve-se abrir o monitor serial na IDE do arduino e aproximar o card que irá ser cadastrado, o monitor serial vai responder vários números enormes, porém só iremos precisar do número ao lado do “CARD UID” que é o ID do nosso card.
Agora basta apenas atualizar no código principal, seguindo os modelos das palavras já cadastradas em nosso código principal. Por exemplo:
#define cartaTelefone "93CF6832" (exemplo de ID)
Também é preciso adicionar uma palavra nova correspondente no array PALAVRAS.


##Pondo em prática!

Agora com tudo pronto basta seguir esse passo a passo para se divertir e aprender com o librino:

Para ligar o equipamento, basta acionar o switch para o estado "ON"
Em seguida, o jogo começará. A cada rodada, será exibida uma palavra aleatória na tela
O objetivo do jogo é escolher a carta com o sinal de Libras que corresponde à palavra exibida na tela
Após escolher a carta, o jogador deve aproximá-la ao sensor no topo do dispositivo
Se a escolha estiver correta, as luzes verdes se acenderão e será exibido "Carta correta!" na tela
Se a escolha estiver errada, as luzes vermelhas se acenderão e será exibido "Carta incorreta!" na tela
Em seguida, uma nova rodada é iniciada
Para desligar o equipamento, basta acionar o switch de volta para o estado "OFF".

