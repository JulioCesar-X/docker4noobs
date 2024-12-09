# 🛠️ Criando uma Aplicação Node.js em Docker

Neste tutorial, vamos aprender como criar e executar uma aplicação simples em Node.js usando Docker. Este é um exemplo prático para entender como usar imagens Docker e configurar o ambiente de desenvolvimento. 🚀

---

## 📋 O que você vai aprender?

- Criar um ambiente para desenvolvimento com Node.js.
- Configurar um Dockerfile para a aplicação.
- Construir e rodar a aplicação em um contêiner.

---

## 🛠️ Passo a Passo

### 1️⃣ Configurando o Ambiente

1. Crie um diretório para o projeto:
   ```bash
   mkdir nodejs-docker-app
   cd nodejs-docker-app
   ```

2. Inicialize o projeto Node.js:
   ```bash
   npm init -y
   ```
   - Isso cria um arquivo `package.json` com as configurações básicas.

3. Crie o arquivo principal da aplicação:
   ```bash
   touch app.js
   ```

4. Adicione o seguinte código ao `app.js`:
   ```javascript
   const http = require('http');

   const hostname = '0.0.0.0';
   const port = 3000;

   const server = http.createServer((req, res) => {
       res.statusCode = 200;
       res.setHeader('Content-Type', 'text/plain');
       res.end('Hello, Docker!');
   });

   server.listen(port, hostname, () => {
       console.log(`Server running at http://${hostname}:${port}/`);
   });
   ```

---

### 2️⃣ Criando o Dockerfile

1. No diretório do projeto, crie um arquivo chamado `Dockerfile`:
   ```bash
   touch Dockerfile
   ```

2. Adicione o seguinte conteúdo ao `Dockerfile`:
   ```dockerfile
   # Usando a imagem base do Node.js
   FROM node:14

   # Define o diretório de trabalho dentro do contêiner
   WORKDIR /app

   # Copia o arquivo package.json e instala as dependências
   COPY package*.json ./
   RUN npm install

   # Copia o restante dos arquivos da aplicação
   COPY . .

   # Expõe a porta que o servidor usará
   EXPOSE 3000

   # Comando para iniciar a aplicação
   CMD ["node", "app.js"]
   ```

---

### 3️⃣ Construindo e Executando a Imagem

1. Construa a imagem Docker:
   ```bash
   docker build -t nodejs-app .
   ```
   - **`-t nodejs-app`**: Dá um nome à imagem.
   - **`.`**: Indica o diretório atual como contexto para o build.

2. Execute o contêiner:
   ```bash
   docker run -d -p 3000:3000 nodejs-app
   ```
   - **`-d`**: Roda o contêiner em segundo plano.
   - **`-p 3000:3000`**: Mapeia a porta 3000 no host para a porta 3000 no contêiner.

---

### 4️⃣ Testando a Aplicação

1. Acesse a aplicação no navegador:
   ```
   http://localhost:3000
   ```

2. **O que você verá?**:
   - A página exibirá:
     ```
     Hello, Docker!
     ```

---

## 📝 Resultado Final

- Sua aplicação Node.js está rodando dentro de um contêiner Docker.
- Você criou e gerenciou uma imagem Docker personalizada para sua aplicação.

---

<div align="center">
  <h2>🔗 Próximos Passos</h2>
  <p>Explore mais projetos práticos:</p>
  <ul>
    <li><a href="../mysql_configuration/README.md">Configurando um banco de dados MySQL</a></li>
    <li><a href="../docker_compose/README.md">Orquestração com Docker Compose</a></li>
  </ul>
</div>
