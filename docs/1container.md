# Container LXC

**Listando Containers**

Para começar, vamos listar se existem containers existentes. Abra seu terminal e digite o seguinte comando:
    
    lxc list -c n4

[![lxc-list](https://i.im.ge/2023/11/07/y9d2vD.lxc-list.md.png)](https://im.ge/i/y9d2vD)

Na imagem a cima, vemos a lista de containers disponiveis e seu respectivo ip.

**Baixando e instalando um container**

    lxc launch images:debian/12/cloud nome-da-maquina
    sendo em sua sequencia debian(nome da distro) 12(versão da distro)

[![lxc-install](https://i.im.ge/2023/11/07/y9dEJS.lxc-install.md.png)](https://im.ge/i/y9dEJS)

**Executando o container**

Digite o comando com o nome da VM e o shell a ser executado. No meu caso, usarei o zsh, mas por padrão se usa o bash.

    lxc exec vm-02 bash

[![exec](https://i.im.ge/2023/11/07/y97Zj4.exec.md.png)](https://im.ge/i/y97Zj4)

Com a VM sendo executada, vamos para os próximis passos.

[](https://pt.wikipedia.org/wiki/Z_shell)
