
# 🐳 Exemplos Práticos de Volumes no Docker

Aqui estão exemplos detalhados de como usar volumes no Docker. 🛠️

---

## 📦 Exemplo 1: Criando e Usando um Volume Básico

1. **Crie um volume chamado `meu-volume`:**
   ```bash
   docker volume create meu-volume
   ```
   - **`docker volume create`**: Cria um novo volume no Docker.
   - **`meu-volume`**: Nome que você está atribuindo ao volume.

   **Saída esperada**:
   ```
   meu-volume
   ```

2. **Monte o volume em um contêiner Ubuntu:**
   ```bash
   docker run -v meu-volume:/dados -it ubuntu bash
   ```
   - **`docker run`**: Cria e executa um novo contêiner.
   - **`-v meu-volume:/dados`**: Monta o volume `meu-volume` no diretório `/dados` dentro do contêiner.
   - **`-it`**: Permite interação com o terminal do contêiner.
   - **`ubuntu`**: Usa a imagem oficial do Ubuntu.
   - **`bash`**: Executa o shell Bash.

   No contêiner, crie um arquivo no volume:
   ```bash
   touch /dados/meu-arquivo
   ```

3. **Remova o contêiner e recrie-o:**
   ```bash
   docker rm -f <container_id>
   docker run -v meu-volume:/dados -it ubuntu bash
   ```
   - **`docker rm -f`**: Remove o contêiner especificado.
   - **`docker run`**: Recria o contêiner com o mesmo volume montado.

   Dentro do contêiner, liste os arquivos no diretório `/dados`:
   ```bash
   ls /dados
   ```

   **Saída esperada**:
   ```
   meu-arquivo
   ```

---

## 📦 Exemplo 2: Compartilhando Volumes Entre Contêineres

1. **Monte o mesmo volume em dois contêineres:**
   - Primeiro contêiner:
     ```bash
     docker run -v meu-volume:/dados -it ubuntu bash
     ```
     Dentro do contêiner, crie um arquivo:
     ```bash
     echo "Olá, Docker!" > /dados/mensagem.txt
     ```

   - Segundo contêiner:
     ```bash
     docker run -v meu-volume:/dados -it ubuntu bash
     ```
     Dentro do segundo contêiner, leia o arquivo:
     ```bash
     cat /dados/mensagem.txt
     ```

   **Saída esperada**:
   ```
   Olá, Docker!
   ```

2. **Explicação dos comandos**:
   - Ambos os contêineres usam o volume `meu-volume`, permitindo o compartilhamento de dados.

---

## 📦 Exemplo 3: Montando um Diretório do Host

1. **Monte um diretório local como volume:**
   ```bash
   docker run -v $(pwd)/meus-dados:/dados -it ubuntu bash
   ```
   - **`$(pwd)/meus-dados`**: Diretório do host a ser montado.
   - **`/dados`**: Caminho no contêiner onde o diretório será acessível.

2. **Crie um arquivo no contêiner:**
   ```bash
   echo "Arquivo criado no contêiner" > /dados/host-arquivo.txt
   ```

3. **Verifique o arquivo no diretório do host:**
   ```bash
   cat meus-dados/host-arquivo.txt
   ```

   **Saída esperada**:
   ```
   Arquivo criado no contêiner
   ```

4. **Explicação**:
   - O arquivo criado no contêiner aparece no diretório do host porque o volume foi montado como um espelho.

---

<div align="center">
  <h2>🔗 Próximos Passos</h2>
  <p>Explore mais sobre volumes e contêineres:</p>
  <ul>
    <li><a href="./volumes_intro.md">Voltar para Introdução a Volumes</a></li>
    <li><a href="../README.md">Voltar para os Conceitos</a></li>
  </ul>
</div>
