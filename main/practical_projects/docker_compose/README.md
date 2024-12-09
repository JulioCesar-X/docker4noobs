# 🛠️ Orquestração com Docker Compose

O Docker Compose permite gerenciar múltiplos serviços em contêineres com um único arquivo de configuração. Neste tutorial, você aprenderá a orquestrar uma aplicação Node.js e um banco de dados MySQL usando o Compose. 🎯

---

## 📋 O que você vai aprender?

- Criar um arquivo `docker-compose.yml` para orquestrar serviços.
- Configurar uma aplicação Node.js e um banco de dados MySQL.
- Executar e gerenciar múltiplos contêineres com Docker Compose.

---

## 🛠️ Passo a Passo

### 1️⃣ Configurando o Ambiente

1. Crie um diretório para o projeto:
   ```bash
   mkdir nodejs-mysql-compose
   cd nodejs-mysql-compose
   ```

2. Dentro do diretório, crie a estrutura de arquivos:
   ```bash
   mkdir nodejs-app
   touch docker-compose.yml
   ```

3. Adicione o seguinte código ao arquivo `nodejs-app/app.js`:
   ```javascript
   const express = require('express');
   const mysql = require('mysql2');

   const app = express();
   const port = 3000;

   const db = mysql.createConnection({
       host: 'mysql',
       user: 'root',
       password: 'senha123',
       database: 'meubanco'
   });

   app.get('/', (req, res) => {
       db.query('SELECT "Hello, Docker Compose!" as message', (err, result) => {
           if (err) throw err;
           res.send(result[0].message);
       });
   });

   app.listen(port, () => {
       console.log(`App running on http://localhost:${port}`);
   });
   ```

4. Adicione o seguinte código ao `nodejs-app/package.json`:
   ```json
   {
       "name": "nodejs-mysql-compose",
       "version": "1.0.0",
       "main": "app.js",
       "dependencies": {
           "express": "^4.18.2",
           "mysql2": "^2.3.3"
       }
   }
   ```

---

### 2️⃣ Criando o Arquivo docker-compose.yml

Adicione o seguinte conteúdo ao arquivo `docker-compose.yml`:
```yaml
version: '3.8'
services:
  app:
    build:
      context: ./nodejs-app
    ports:
      - "3000:3000"
    depends_on:
      - mysql
  mysql:
    image: mysql:8.0
    environment:
      MYSQL_ROOT_PASSWORD: senha123
      MYSQL_DATABASE: meubanco
    volumes:
      - mysql-data:/var/lib/mysql
volumes:
  mysql-data:
```

**Explicação do arquivo**:
- **`app`**: Define o serviço para a aplicação Node.js.
  - **`build.context`**: Usa o diretório `nodejs-app` para construir a imagem.
  - **`depends_on`**: Garante que o serviço MySQL esteja pronto antes de iniciar a aplicação.
- **`mysql`**: Define o serviço para o banco de dados MySQL.
  - **`environment`**: Configura variáveis de ambiente do MySQL.
  - **`volumes`**: Garante persistência de dados para o MySQL.

---

### 3️⃣ Construindo e Executando os Serviços

1. Instale as dependências do Node.js:
   ```bash
   cd nodejs-app
   npm install
   cd ..
   ```

2. Execute o Docker Compose:
   ```bash
   docker-compose up -d
   ```

3. Verifique se os serviços estão em execução:
   ```bash
   docker-compose ps
   ```

---

### 4️⃣ Testando a Aplicação

1. Acesse no navegador:
   ```
   http://localhost:3000
   ```

2. **O que você verá?**:
   - A página exibirá:
     ```
     Hello, Docker Compose!
     ```

---

## 📝 Resultado Final

- Você criou e orquestrou múltiplos serviços (Node.js e MySQL) com Docker Compose.
- Aprendeu a gerenciar contêineres e volumes com um único arquivo de configuração.

---

<div align="center">
  <h2>🔗 Próximos Passos</h2>
  <p>Explore mais sobre Docker:</p>
  <ul>
    <li><a href="../nodejs_application/README.md">Criando uma aplicação Node.js em Docker</a></li>
    <li><a href="../mysql_configuration/README.md">Configurando um banco de dados MySQL</a></li>
    <li><a href="./more_docker_compose.md">Mais sobre docker compose</a></li>
  </ul>
</div>
