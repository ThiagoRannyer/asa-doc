# Code-server

Nesse passo, instalaremos o code-server, seria o VScode na versão para navegador.

Sugiro que instale o TREE para melhor visualização de um arquivos que iremos precisar.

**instalando o tree**

    apt install tree

**instale o curl**

    apt install -y curl

**baixe o code server**

    curl -fsSL https://code-server.dev/install.sh | sh

**Crie um usuário**

    adduser thiago

**Ative o code-server**

    systemctl enable --now code-server@thiago

*thiago será substituído pele nome do usuário que foi criado.

**Verifique se o arquivo config.yaml foi criado**

    tree ~thiago/.config

[![tree](https://i.im.ge/2023/11/07/y9LXPJ.tree.md.png)](https://im.ge/i/y9LXPJ)

**Acessando o code-server**

Para acessar o code server, precisamos editar um arquivo de configuração, alterando seu ip para acesso via navegador.

    nano ~thiago/.config/code-server/config.yaml

[![config1](https://i.im.ge/2023/11/07/y9LB1M.config1.md.png)](https://im.ge/i/y9LB1M)

Altere o ip para a o ip do seu container e a palavra 'password' para 'none'

[![config2](https://i.im.ge/2023/11/07/y9LeZD.config2.md.png)](https://im.ge/i/y9LeZD)

Reinicie o apache2

    systemctl restart apache2

Se seguiu o passo direitinho e estiver tudo correto, você acessa o code-server pelo seu navegador. 

    Digite seu_ip:8080 no navegador

e o seu code server deverá abrir.

