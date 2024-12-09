# 🐳 Exemplos Práticos de Dockerfile

Neste guia, vamos criar imagens Docker personalizadas com explicações passo a passo para cada comando e o que você deve esperar. Ideal para quem está começando! 🚀

---

## 📦 Exemplo 1: Imagem com Apache

1. Crie um arquivo chamado `Dockerfile` com o seguinte conteúdo:
   ```dockerfile
   FROM debian:latest
   RUN apt-get update && apt-get install -y apache2
   EXPOSE 80
   CMD ["apachectl", "-D", "FOREGROUND"]
   ```

   **Explicação dos comandos**:
   - `FROM`: Define a imagem base (neste caso, Debian).
   - `RUN`: Executa comandos no sistema (como atualizar pacotes ou instalar software).
   - `EXPOSE`: Declara a porta que o contêiner usará.
   - `CMD`: Define o comando padrão que será executado quando o contêiner iniciar.

2. Construa a imagem:
   ```bash
   docker build -t apache-image .
   ```
   - **`-t apache-image`**: Dá um nome à imagem.
   - **`.`**: Indica que o `Dockerfile` está no diretório atual.

3. Execute o contêiner:
   ```bash
   docker run -d -p 8080:80 apache-image
   ```
   - **`-d`**: Roda o contêiner em segundo plano.
   - **`-p 8080:80`**: Mapeia a porta 8080 no host para a porta 80 no contêiner.

4. **O que você verá**:
   - Acesse `http://localhost:8080` no navegador e verá a página padrão do Apache.

---

## 📦 Exemplo 2: Imagem com um Script Python

1. Crie um arquivo chamado `app.py`:
   ```python
   print("Hello, Docker!")
   ```

2. Crie um arquivo `Dockerfile` com o seguinte conteúdo:
   ```dockerfile
   # Escolhe a imagem base do Python (versão 3.8).
   FROM python:3.8-slim

   # Copia o script Python para o contêiner.
   COPY app.py /app.py

   # Define o comando padrão para executar o script.
   CMD ["python", "/app.py"]
   ```

   **Explicação dos comandos**:
   - `FROM`: Escolhe a imagem base do Python.
   - `COPY`: Copia o arquivo `app.py` do host para o contêiner.
   - `CMD`: Define o comando padrão para rodar o script.

3. Construa a imagem:
   ```bash
   docker build -t python-app .
   ```

4. Execute o contêiner:
   ```bash
   docker run python-app
   ```

5. **O que você verá**:
   - O terminal exibirá:
     ```
     Hello, Docker!
     ```

---

## 📦 Exemplo 3: Imagem com Variáveis de Ambiente

1. Crie um arquivo `Dockerfile`:
   ```dockerfile
   # Usando a imagem base do Ubuntu.
   FROM ubuntu:latest

   # Define uma variável de ambiente chamada APP_ENV.
   ENV APP_ENV=production

   # Exibe a variável ao iniciar o contêiner.
   CMD ["bash", "-c", "echo O ambiente é $APP_ENV"]
   ```

   **Explicação dos comandos**:
   - `FROM`: Escolhe o Ubuntu como imagem base.
   - `ENV`: Define uma variável de ambiente disponível dentro do contêiner.
   - `CMD`: Executa um comando que exibe o valor da variável.

2. Construa a imagem:
   ```bash
   docker build -t env-example .
   ```

3. Execute o contêiner:
   ```bash
   docker run env-example
   ```

4. **O que você verá**:
   - O terminal exibirá:
     ```
     O ambiente é production
     ```

---

<div align="center">
  <h2>🔗 Próximos Passos</h2>
  <p>Explore mais sobre imagens e contêineres:</p>
  <ul>
    <li><a href="./dockerfile_basics.md">Voltar para Introdução ao Dockerfile</a></li>
    <li><a href="../README.md">Voltar para os Conceitos</a></li>
  </ul>
</div>
