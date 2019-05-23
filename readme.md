# Ambiente Apache/PHP/MariaDB/Composer com XDEBUG habilitado

O diretório `.vscode` possui o arquivo de  configuração para o VS Code conseguir debuggar. É necessário instalar a extensão [PHP Debug](https://marketplace.visualstudio.com/items?itemName=felixfbecker.php-debug).

Caso o debugger não estiver funcionando, talvez seja necessário colocar o IP do seu host dentro do arquivo `docker-compose.yml`. Ao invés de `remote_host=host.docker.internal`, utilize `remote_host=IP_DO_SEU_HOST`. Isso normalmente faz-se necessário quando usado a ToolBox do Docker.

O arquivo `.docker/vhost.conf` está configurado para projetos em `lumen/laravel`. Caso não for usado `lumen/laravel`, remover o diretório `public` desse arquivo.

Se necessário, alterar as portas no arquivo `docker-compose.yml`

O ambiente está com SSL configurado, então é possível acesso via `https://`.

Por fim, basta executar o comando abaixo:
```bash
docker-compose up --build -d
```