# Configuração Serviço de DNS

Este documento detalha os passos necessários para realizar a configuração de um servidor DNS. Atividade que faz parte da disciplina Rdes de Computadores 2 do curso de Sistemas para Internet `IFRS Poa`.


## Configuration

### VirtualBox

Para passo-a-passo foi utilizado o VirtualBox, que pode ser baixado neste link [VirtualBox](https://www.virtualbox.org/wiki/Downloads). Os comandos e etapas necessários para instalação do VirtualBox você pode conferir neste [link](https://www.techtudo.com.br/dicas-e-tutoriais/noticia/2013/03/descubra-como-instalar-o-virtualbox-e-seu-pacote-de-extensoes-e-facil.html)

### Máquina virtual

Após a instalação do VirtualBox, baixe esta [máquina virtual](http://www.pop-rs.rnp.br/~cesar/Redes-EAD-12.04.ova). Com o VirtualBox aberto, importe a máquina virtual baixada. Se você não souber como fazer isso, veja [esse exemplo](https://www.youtube.com/watch?v=b74I9f9SNx0). NÃO DÊ O PLAY!!! É necessário fazer alguns ajustes antes.

![Máquina Virtual importada](./Imagem1.PNG)

### VirtualBox-Ajuste!!

Antes de dar o Play, é preciso fazer alguns ajustes na máquina virtual importada.

1.  Selecione a opção Configurações no menu do VirtualBox e, no menu esquerdo da janela que irá aparecer, selecione a opção Redes. Desmarque a opção "Habilitar Placa de Rede" do adaptador 1 e habilite o adaptador 2 em modo Bridge.
Após realizar essas configurações, inicie a máquina virtual.
![Configuração inicial Máquina Virtual](./Imagem2.PNG)

2.  Aguarde a máquina iniciar completamente, etapa que pode demorar alguns minutos. Se uma tela semelhante à imagem a seguir surgiu no seu monitor, significa que você está no caminho certo.
Agora digite o usuário "aluno" e a senha "aluno". 
![Configuração inicial Máquina Virtual](./Imagem3.PNG)

3.  
