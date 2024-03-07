<h1 align="center"> Maitatech Boilerplate Python + FastAPI</h1>

### Setando Variaveis de Ambiente

Um arquivo example.env foi adicionando no repositorio como exemplo.

#### Configuração do app
```sh
APP_NAME="Boilerplate"
APP_DESCRIPTION="Esqueleto para inicio de desenvolvendo CRUD"
APP_VERSION="1.0"
CONTACT_NAME="Rodrigo"
CONTACT_EMAIL="rpaivadamasceno@gmail.com"
LICENSE_NAME="licensa"
```
#### Configuração do database
```sh
POSTGRES_USER="rodrigopd"
POSTGRES_PASSWORD="123456"
POSTGRES_SERVER="db"
POSTGRES_PORT=5432
POSTGRES_DB="postgresdb"
```
#### Configuração do pgadmin

```sh
PGADMIN_DEFAULT_EMAIL="teste@gmai.com"
PGADMIN_DEFAULT_PASSWORD="123456"
PGADMIN_LISTEN_PORT=80
```
#### Gerando e setando Secret
Para gerar uma secret_key:
```sh
openssl rand -hex 32
```
adicionar:
```sh
SECRET_KEY= "secret"
```
#### Configuração para admin

```sh
ADMIN_NAME="admin"
ADMIN_EMAIL="admin@gmail.com"
ADMIN_USERNAME="admin"
ADMIN_PASSWORD="123456"
```
#### redis
```sh
REDIS_CACHE_HOST="redis"
REDIS_CACHE_PORT=6379
REDIS_QUEUE_HOST="redis"
REDIS_QUEUE_PORT=6379
```

### Rodando projeto com Docker Compose:

```sh
docker compose up
```

### Criando Super Usuario

O usuario é criado de acordo com o que foi colocado nas variaveis que começam com 'ADMIN_'

Dentro do container web rodar o comando(/code):

```sh
python -m scripts.create_first_superuser
```

ou

```sh
docker exec web bash -c "python -m scripts.create_superuser"
```

## Pytest

OBS: Essa parte do teste foi implementada mas não efetivamente testada. O tempo ficou curto.

Setar as variaveis de ambiente para teste no .env:

```
# ------------- test -------------
TEST_NAME="tester"
TEST_EMAIL="tester@gmail.com"
TEST_USERNAME="tester"
TEST_PASSWORD="123456"
```

Para criar novos testes é só adicionar os aquivos com nome iniciando com "test_".py dentro do /tests

```sh
docker-compose up -d
```
ou

```sh
docker-compose run --rm pytest
```
