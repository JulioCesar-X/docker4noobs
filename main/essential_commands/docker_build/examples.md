# 🐳 Exemplos de Uso do `docker build`

Aqui estão exemplos práticos para ajudar você a dominar o comando `docker build`.

---

## 📦 Criando Imagens com Dockerfile

1. **Exemplo simples**:
   Crie um arquivo chamado `Dockerfile` com o seguinte conteúdo:
   ```dockerfile
   FROM ubuntu:latest
   RUN apt-get update && apt-get install -y curl
   CMD ["bash"]
   ```
   Em seguida, execute o comando:
   ```bash
   docker build -t minha-imagem:1.0 .
   ```
   - **`-t minha-imagem:1.0`**: Dá um nome e versão à imagem.
   - **`.`**: Define o diretório atual como caminho do `Dockerfile`.

---

## 🚀 Usando Argumentos no Build

1. **Passar variáveis de ambiente**:
   Adicione um argumento ao `Dockerfile`:
   ```dockerfile
   FROM ubuntu:latest
   ARG ENV=development
   RUN echo "Ambiente: $ENV"
   CMD ["bash"]
   ```
   E execute o comando:
   ```bash
   docker build --build-arg ENV=production -t minha-imagem:2.0 .
   ```

---

## 🛠️ Otimizando Builds com Cache

1. **Forçar reconstrução**:
   Para desabilitar o uso de cache durante o build, use:
   ```bash
   docker build --no-cache -t minha-imagem:1.1 .
   ```

2. **Benefícios do cache**:
   Se o `Dockerfile` não mudou, o cache reduz o tempo de build.

Para mais informações, volte para [overview.md](./overview.md).
