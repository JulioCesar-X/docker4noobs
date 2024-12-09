# 🐳 Introdução ao Dockerfile

O **Dockerfile** é um arquivo de texto que contém uma lista de instruções para construir uma imagem Docker personalizada. É como uma receita que o Docker segue para criar uma imagem. 📜

---

## 📌 O que é um Dockerfile?

Um Dockerfile:
- Define o sistema base para a imagem (exemplo: Ubuntu, Alpine, etc.).
- Adiciona dependências, arquivos e configurações necessários.
- Automatiza a criação de imagens para diferentes ambientes.

---

## 📋 Estrutura Básica de um Dockerfile

Um Dockerfile típico segue esta estrutura:

```dockerfile
# Imagem base
FROM ubuntu:latest

# Adiciona dependências
RUN apt-get update && apt-get install -y curl

# Copia arquivos para o contêiner
COPY app/ /app/

# Define o comando a ser executado no contêiner
CMD ["bash"]
```

---

## 🚀 Comandos Importantes do Dockerfile

1. **`FROM`**:
   - Define a imagem base.
   - Exemplo:
     ```dockerfile
     FROM ubuntu:latest
     ```

2. **`RUN`**:
   - Executa comandos no contêiner durante o build.
   - Exemplo:
     ```dockerfile
     RUN apt-get update && apt-get install -y curl
     ```

3. **`COPY`** ou **`ADD`**:
   - Copia arquivos para dentro do contêiner.
   - Exemplo:
     ```dockerfile
     COPY app/ /app/
     ```

4. **`CMD`**:
   - Define o comando padrão ao iniciar o contêiner.
   - Exemplo:
     ```dockerfile
     CMD ["bash"]
     ```

---

## 🛠️ Criando uma Imagem com Dockerfile

1. Crie um arquivo chamado `Dockerfile` com o conteúdo:
   ```dockerfile
   FROM ubuntu:latest
   RUN apt-get update && apt-get install -y curl
   CMD ["bash"]
   ```

2. No terminal, execute:
   ```bash
   docker build -t minha-imagem:1.0 .
   ```

3. Verifique a imagem criada:
   ```bash
   docker images
   ```

---

<div align="center">
  <h2>🔗 Próximos Passos</h2>
  <p>Agora que você entende Dockerfiles, explore o próximo conceito:</p>
  <ul>
    <li><a href="./examples.md">Veja exemplos práticos</a></li>
    <li><a href="../README.md">Voltar para os Conceitos</a></li>
  </ul>
</div>
