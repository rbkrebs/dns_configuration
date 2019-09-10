# Configuração Serviço de DNS

Este documento detalha os passos necessários para realizar a configuração de um servidor DNS. Atividade que faz parte da disciplina Redes de Computadores 2 do curso de Sistemas para Internet `IFRS Poa`. Atividade realizada junto com a colega [Rafaela](https://github.com/rafcristina152)


## Configuration

### VirtualBox

Para passo-a-passo foi utilizado o VirtualBox, que pode ser baixado neste link [VirtualBox](https://www.virtualbox.org/wiki/Downloads). Os comandos e etapas necessários para instalação do VirtualBox você pode conferir neste [link](https://www.techtudo.com.br/dicas-e-tutoriais/noticia/2013/03/descubra-como-instalar-o-virtualbox-e-seu-pacote-de-extensoes-e-facil.html)

### Putty

Para simular acesso remoto ao servidor, para a atividade nós utilizamos o [PuTTy](https://www.putty.org/). Baixe a versão mais estável do seu sistema operacional. 

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

3.  Após fazer o login, execute o comando `ifconfig` para verificar as configurações das interfaces de rede. Caso liste apenas a interface local, devemos fazer mais algumas configurações para habilitar a conexão Ethernet.

![Comando ifconfig](./Imagem4.PNG)

4.  Execute o comando `ip link show` para verificar as características dos dispositivos de rede. Na imagem abaixo, temos os dispositivos **lo** e **eth3** (preste bastante atenção no número após o eth).

![resultado do ip link show](./Imagem5.PNG)

5.  Para que o dispositivo **eth3** apareça após o comando ifconfig, é necessário listá-lo dentro do arquivo que registra as interfaces de rede. Para isso, digite `vi /etc/network/interfaces`. Importante: para fazer alterações nesses arquivos, você deve estar com a permissão de super usuário `sudo su`.

![informações arquivo interfaces](./Imagem6.PNG)

6.  Observe que o arquivo apresenta o dispositivo **eth0** e não o **eth3** que é o nosso dispositivo. Precisamos, então, editar este arquivo com a informação correta para que ele apareça listado após o `ifconfig`. Selecione a **tecla I** ou **Insert** para poder editar o texto e utilize as setas do teclado para navegar até a linha desejada. Onde estiver escrito **eth0**, troque para eth + o número que apareceu na etapa 4. Aperte a **tecla ESC** para sair do modo de edição e digite `:wq` para salvar as alterações e sair do arquivo.

![resultado final arquivo interfaces](./Imagem7.PNG)

7.  Agora você deve executar o comando `/etc/init.d/networking restart` para reiniciar o serviço.

![restart networking](./Imagem8.PNG)

8.  Agora o dispositivo **eth3** deverá aparecer após o comando `ifconfig`.

![eth3 configurado](./Imagem9.PNG)

> [!WARNING]
> Para evitar possíveis erros, execute o comando apt-get update para atualizar os pacotes de todas as fontes configuradas.
> Até o momento, fizemos algumas verificações e configurações. A instalação do serviço de DNS começa a partir daqui.

