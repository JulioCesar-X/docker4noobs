# 🐳 Exemplos de Uso do `docker run`

Aqui estão alguns exemplos práticos para ajudar você a dominar o comando `docker run`.

---

## 📦 Criando e Executando um Contêiner

1. **Rodar uma imagem interativamente**:
   ```bash
   docker run -it ubuntu bash
   ```
   - **`-it`**: Permite interação com o terminal.
   - **`ubuntu`**: A imagem usada.
   - **`bash`**: O comando a ser executado.

---

## 🚀 Executando em Background

1. **Rodar um servidor NGINX**:
   ```bash
   docker run -d -p 8080:80 nginx
   ```
   - **`-d`**: Roda o contêiner em segundo plano.
   - **`-p`**: Mapeia a porta 8080 no host para a porta 80 no contêiner.
   - **`nginx`**: A imagem usada.

2. **Verificar o contêiner em execução**:
   ```bash
   docker ps
   ```

---

## 🗑️ Limpando após o uso

1. **Remover o contêiner automaticamente**:
   ```bash
   docker run --rm ubuntu echo "Contêiner temporário"
   ```

2. **Verificar que o contêiner foi removido**:
   ```bash
   docker ps -a
   ```

Para mais informações, volte para [overview.md](./overview.md).
