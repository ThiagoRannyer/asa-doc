# LAMP

Linux Apache Mariadb PHP

Digite o código

    apt install -y apache2 php mariadb-server libapache2-mod-php php-mysql

Instale o Mysql secure

    mysql_secure_installation

Baixe o cli-wp (faça o download dentro do diretório de instalação /usr/local/bin)

    wget https://raw.githubusercontent.com/wp-cli/builds/gh-pages/phar/wp-cli.phar

Renoear o arquivo baixado para wp

    mv wp-cli.phar wp

Aumentar as permissões do arquivo

    chmod +x wp

Para executar o arquivo wp, precisaremos de um usuário sem ser o root. Então se não tiver nenhum, crie.

    adduser fulano

Faça uma cópia do arquivo 000-default.conf no diretório sites-enabled

    /etc/apache2/sites-enabled/000-default.conf

    cp 000-default.conf docs.conf

altere o documento criado com as informações necessárias para o redirecionamento. Onde o **ServerName** é a URL e o **DocumentRoot** o caminho onde estão os arquivos.

    nano /etc/apache2/sites-enabled/docs.conf(nome dado ao arquivo/servidor)
    
[![docs](https://i.im.ge/2023/11/09/yxJDxm.docs.md.png)](https://im.ge/i/yxJDxm)

Dê as permissões necessárias para o usuário que você criou

    chown fulano:fulano /var/www

faça login como super usuário com o usuário criado 

    su - fulano

com usuário logado, acesse o diretoório criado

    cd /var/www/WP(nome do diretório criado)

em um outro terminal, pegue o ip do container

    ip -br -c -4 a

Execute o wp core onde path=wp é o nome do diretório onde será instalado o WP

    wp core download --local=pt_BR --path=wp

Faça novamente login como root e exacute o mysql

    mysql

Crie um banco de dados (wordpress é o nome do banco de dados, use o nome de sua preferencia ou necessidade)

    create database wordpress CHARSET SET utf8 COLLATE utf8_general_ci;

Crie um usuario e senha

    create user 'usuario'@'localhost' identified by 'senha123';

Dê permissões ao usuário criado ligando ao banco de dados

    grant all privileges on wordpress.* to 'usuario'@'localhost';

Saia do MariaDB

    \q

logue novamente como super usuário com o usuário criado

    su - usuario

Dê permissões a pasta criada com os arquivos WP

    chmod 777 /var/www/WP

