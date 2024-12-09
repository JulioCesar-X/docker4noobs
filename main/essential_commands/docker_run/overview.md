
# 🐳 Comando `docker run`

O comando `docker run` é um dos mais usados no Docker. Ele permite criar e executar um contêiner a partir de uma imagem. Vamos entender os conceitos e opções principais.

---

## 📌 Sintaxe
```bash
docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
```

### Componentes:
- **`IMAGE`**: A imagem que será usada para criar o contêiner.
- **`OPTIONS`**: Parâmetros que configuram o comportamento do contêiner.
- **`COMMAND`**: Um comando opcional a ser executado no contêiner.
- **`ARG`**: Argumentos opcionais para o comando.

---

## 🚀 Opções Principais
1. **`-d`**: Executa o contêiner em modo "desanexado" (background).
2. **`-p`**: Mapeia portas entre o host e o contêiner.
3. **`--name`**: Dá um nome ao contêiner.
4. **`-v`**: Monta volumes no contêiner.
5. **`--rm`**: Remove automaticamente o contêiner após ele ser encerrado.

---

## 🛠️ Exemplos Básicos
1. Executar um contêiner interativo:
   ```bash
   docker run -it ubuntu bash
   ```

2. Executar em background:
   ```bash
   docker run -d nginx
   ```

3. Mapeando portas:
   ```bash
   docker run -d -p 8080:80 nginx
   ```

- Confira exemplos detalhados em [examples.md](./examples.md).
- Finalizou? volte para [Comandos Essenciais](../README.md).
