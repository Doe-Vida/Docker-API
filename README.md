# Doe vida ❣

## Iniciando com Docker 🚢
Primeiramente para iniciar a configuração é necessário que você tenha instalado o docker em sua máquina, segue link para configuração do mesmo: 

- Windows: https://docs.docker.com/desktop/install/windows-install/
- Linux: https://docs.docker.com/desktop/install/linux-install/
- Mac: https://docs.docker.com/desktop/install/mac-install/

Com o Docker Hub instalado, inicie o software.

## Configurações do Ambiente ⛲
Vamos criar uma API CRUD Rest em Python, usando:
- Flask (estrutura da Web em Python) 🐍
- SQLAlquimia (ORM) 🛠
- PostgresSQL (banco de dados) 🎲
- Docker (containerização) 🚢
- Docker Compose (para executar o aplicativo e o banco de dados em contêineres) ⏫

### 🚩
Abra seu Powershell (terminal para computadores windows), provavelme ele iniciará dentro do seguinte caminho:
```ps
    C:\Users\usuario
```

Digite os seguintes comandos dentro do terminal:
```ps
    cd /
    mkdir Projetos
    cd .\Projetos\
```

Dentro da pasta projetos, clone o repositório usando o comando:
```ps 
    git clone https://github.com/FrancoEdu/doe-vida-API.git
    cd .\doe-vida-API\
    code .
```

Após seguir esse passo à passo provalvente irá abrir o VS Code da pasta

### 👟 Executar o contêiner Postgres e teste com SQLTools Extension
Para essa etapa precisamos instalar algumas extensões do VS Code em nossa máquina, São elas:
- https://marketplace.visualstudio.com/items?itemName=mtxr.sqltools
- https://marketplace.visualstudio.com/items?itemName=mtxr.sqltools-driver-pg

Com as extensões instaladas devemos realizar os seguintes comandos:
- Para iniciar o container do PostgresSQL:
```docker
    docker compose up -d flask_db
```
O parâmetro -d é para executar o contêiner no modo desanexado, portanto, ele será executado em segundo plano

O Docker está puxando (baixando) a imagem do Postgres em nossa máquina local e está executando um contêiner baseado nessa imagem do Postgres.
Para verificar se o contêiner está em execução:
```docker
    docker compose logs
```
Se a última linha for ```LOG: If the last line is LOG: database system is ready to accept connections```, significa que o container está rodando e o servidor Postgres está pronto para aceitar conexões

Agora, para testar a conexão com o banco, nós usaremos a ferramenta instalada anteriormente:

<img src="/assets/dbicon.png" alt="Icone db">

Com o banco aberto você visualizará outra tela, e preencha com as seguintes informações:
- Connection name* = Database_doe_vida
- Database = postgres
- Username = postgres
- Use Password = Ask on connect

### 🛠 Construindo e iniciando a Flash Application

Agora, vamos criar e executar o aplicativo Flask.
Vamos voltar para a pasta onde o ```docker-compose.yml``` está localizado e digitar
```docker
    docker compose build
```

### ⚗️ Execute o serviço flask_app
Estamos quase terminando, mas uma última etapa é executar um contêiner com base na imagem que acabamos de criar.
Para fazer isso, podemos apenas digitar:
```docker
    docker compose up flask_app
```

Agora se você abrir seu Docker Hub, verá que a aplicação estará Running:
<img src="/assets/dockerRunning.png" alt="Docker db">