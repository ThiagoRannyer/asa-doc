# MKdocs

Liste todos os mkdocs disponíveis para instalação

    apt list mkdocs-*

Instale todos os mkdocs disponíveis

    apainstall -y mkdocs-*

Abra o code-server no navegador com o ip configurado e a porta configurada

    240.24.0.223:8080

abra o terminal clicando nos 3 tracinhos no lado superior esquerdo na janela do code e siga o caminho abaixo

    3 tracinhos > view > terminal

No terminal digite o comando abaixo para criar uma nova pasta com os arquivos do mkdocs

    mkdocs new nome-da-pasta

A seguir abra no code-server a pasta criado

    3 tracinhos > nome-da-pasta

clique no arquivo de configuração do mkdocs

    mkdocs.yml

edite o arquivo com as informações necessárias como o caminho do diretório onde será criado os arquivos do site. lembre de criar a pasta no diretório /var/www com o nome da pasta que irá colocar os arquivos e dar as permissões ao usuário.

    site_dir: /var/www/docs

Volte para o code-server, abra o terminal e execute o comando para a criação dos arquivos do site no diretório

    mkdocs build

Abra o arquivo hosts na maquina real e altere o arquivo colocando o ip do container e o dominio do seus arquivos .conf

    nano /etc/hosts

[![hosts](https://i.im.ge/2023/11/10/ybW1xz.hosts.md.png)](https://im.ge/i/ybW1xz)


Reinicie o apache

    systemctl restart apache2

Prontinho, com esse passo a passo e tudo tendo dado certinho, tudo irá funcionar perfeitamente.
 