# Logs de acesso

Neste passo, veremos como visualizar os logs de acesso do seu site


Dentro do container criado, acesse o diretório de logs

    cd /var/log/apache2

Dê um ls para visualizar os arquivos de log disponíveis 

    ls

[![ls](https://i.im.ge/2023/11/10/yb8uOx.ls.md.png)](https://im.ge/i/yb8uOx)

Execute o comando abaixo junatamente com o nome do arquivo que deseja ver os logs. Obs. [CCZE](http://docs.thiago.lab/adicionais/) é para vizualizar os logs coloridos, precisa ser instalado antes.

    tail -f /var/log/apache2/access.log | ccze

[![logs](https://i.im.ge/2023/11/10/yb8kiy.logs.md.png)](https://im.ge/i/yb8kiy)