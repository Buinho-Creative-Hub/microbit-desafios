# Faísca · programa companheiro (micro:bit V2)

Este é o programa que se grava **uma vez** em cada micro:bit V2 para ele falar com a **Faísca Desafios** por Bluetooth.

## Gravar no micro:bit (5 minutos, uma vez por placa)

1. Abre <https://makecode.microbit.org/#github:Buinho-Creative-Hub/microbit-desafios>
2. Liga o micro:bit por USB e carrega em **Transferir** (ou arrasta o `.hex` para a unidade MICROBIT).
3. O micro:bit mostra um losango pequeno: está pronto para a Faísca.

Já vem com **sem emparelhamento** (No Pairing Required), por isso a Faísca liga directamente.

## Na Faísca

Carrega em **Ligar micro:bit** e escolhe o «BBC micro:bit [...]». O micro:bit mostra um visto e apaga-se.
A partir daí, o que os blocos fazem no ecrã acontece também no micro:bit verdadeiro, e agitar, botões, logótipo e pinos do micro:bit verdadeiro contam para os desafios.

## Ligações

| Desafio | Ligação |
|---|---|
| 5 · Piano de fruta | crocodilo do **P1** à fruta; outro crocodilo no **GND**, seguro na mão |
| 6 · Luz de fora | LED: perna comprida no **P2**, perna curta no **GND** |

## Protocolo (UART Bluetooth, uma linha por mensagem)

| Direcção | Mensagem | Significado |
|---|---|---|
| Faísca → micro:bit | `I<ícone>` | mostrar ícone (`Heart`, `Happy`, `Sad`…) |
| Faísca → micro:bit | `X` | limpar ecrã |
| Faísca → micro:bit | `S<som>` | som do V2 (`giggle`, `happy`…) |
| Faísca → micro:bit | `N<freq>:<ms>` | tocar tom |
| Faísca → micro:bit | `D<pino><0\|1>` | gravação digital P0/P1/P2 |
| Faísca → micro:bit | `W<0\|1>` | enviar (ou não) o nível de luz |
| micro:bit → Faísca | `G` `O` `A` `B` `AB` `P0` `P1` | agitou, logótipo, botões, pinos tocados |
| micro:bit → Faísca | `L<0-255>` | nível de luz (de 1 em 1 s, se `W1`) |

O ficheiro `desafios.md` é uma versão dos desafios como tutorial do MakeCode (alternativa sem a Faísca).

Buinho FabLab · Messejana · CC BY-SA 4.0
