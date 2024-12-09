
# 🛠️ Configurando um Banco de Dados MySQL com Docker

Neste tutorial, vamos aprender como configurar e executar um banco de dados MySQL em um contêiner Docker. Este exemplo é ideal para entender como usar volumes para persistência de dados e garantir que o banco sobreviva à reinicialização do contêiner. 📦

---

## 📋 O que você vai aprender?

- Configurar e executar um banco de dados MySQL em Docker.
- Usar volumes para persistir dados.
- Conectar-se ao banco de dados a partir do host.

---

## 🛠️ Passo a Passo

### 1️⃣ Configurando o Contêiner do MySQL

1. Execute o seguinte comando para criar e rodar o contêiner:
   ```bash
   docker run --name mysql-container -e MYSQL_ROOT_PASSWORD=senha123 -e MYSQL_DATABASE=meubanco -v mysql-data:/var/lib/mysql -p 3306:3306 -d mysql:8.0
   ```
   **Explicação do comando**:
   - **`--name mysql-container`**: Dá um nome ao contêiner.
   - **`-e MYSQL_ROOT_PASSWORD=senha123`**: Define a senha para o usuário root do MySQL.
   - **`-e MYSQL_DATABASE=meubanco`**: Cria automaticamente o banco de dados `meubanco`.
   - **`-v mysql-data:/var/lib/mysql`**: Usa um volume chamado `mysql-data` para persistir os dados do banco.
   - **`-p 3306:3306`**: Mapeia a porta 3306 do host para a porta 3306 do contêiner.
   - **`-d mysql:8.0`**: Usa a imagem oficial do MySQL versão 8.0 e executa em segundo plano.

---

### 2️⃣ Verificando o Contêiner

1. Liste os contêineres em execução:
   ```bash
   docker ps
   ```
   **Saída esperada**:
   ```
   CONTAINER ID   IMAGE       COMMAND                  ...   PORTS                     NAMES
   abc123456789   mysql:8.0   "docker-entrypoint.s…"   ...   0.0.0.0:3306->3306/tcp    mysql-container
   ```

2. Verifique os volumes:
   ```bash
   docker volume ls
   ```
   **Saída esperada**:
   ```
   DRIVER    VOLUME NAME
   local     mysql-data
   ```

---

### 3️⃣ Conectando-se ao Banco de Dados

1. Use o cliente MySQL no host (instale-o, se necessário) para se conectar:
   ```bash
   mysql -h 127.0.0.1 -P 3306 -u root -p
   ```
   - **`-h 127.0.0.1`**: Host local.
   - **`-P 3306`**: Porta do MySQL.
   - **`-u root`**: Usuário root.
   - **`-p`**: Solicita a senha (use `senha123`).

2. Liste os bancos de dados:
   ```sql
   SHOW DATABASES;
   ```
   **Saída esperada**:
   ```
   +--------------------+
   | Database           |
   +--------------------+
   | information_schema |
   | meubanco           |
   | mysql              |
   | performance_schema |
   | sys                |
   +--------------------+
   ```

---

### 4️⃣ Persistência de Dados com Volumes

1. Pare e remova o contêiner:
   ```bash
   docker stop mysql-container
   docker rm mysql-container
   ```

2. Recrie o contêiner com o mesmo volume:
   ```bash
   docker run --name mysql-container -e MYSQL_ROOT_PASSWORD=senha123 -e MYSQL_DATABASE=meubanco -v mysql-data:/var/lib/mysql -p 3306:3306 -d mysql:8.0
   ```

3. Conecte-se novamente e verifique os dados:
   ```sql
   SHOW DATABASES;
   ```
   **Saída esperada**:
   - O banco de dados `meubanco` ainda estará disponível, mostrando que os dados foram preservados no volume.

---

## 📝 Resultado Final

- Você configurou e executou um banco de dados MySQL em Docker.
- Usou volumes para garantir persistência de dados.
- Conectou-se ao banco e confirmou sua funcionalidade.

---

<div align="center">
  <h2>🔗 Próximos Passos</h2>
  <p>Explore mais projetos práticos:</p>
  <ul>
    <li><a href="../nodejs_application/README.md">Criando uma aplicação Node.js em Docker</a></li>
    <li><a href="../docker_compose/README.md">Orquestração com Docker Compose</a></li>
  </ul>
</div>
