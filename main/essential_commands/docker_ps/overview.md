# 🐳 Comando `docker ps`

O comando `docker ps` é usado para listar os contêineres ativos no Docker. Ele fornece informações úteis sobre o estado dos contêineres em execução, como ID, nome e portas expostas.

---

## 📌 Sintaxe
```bash
docker ps [OPTIONS]
```

### Componentes:
- **`OPTIONS`**: Parâmetros adicionais para filtrar ou detalhar a saída.

---

## 🚀 Opções Principais
1. **`-a`**: Lista todos os contêineres (incluindo os que estão parados).
2. **`-q`**: Exibe apenas os IDs dos contêineres.
3. **`--filter`**: Filtra contêineres com base em critérios como estado ou nome.
4. **`--format`**: Personaliza a saída do comando.

---

## 🛠️ Exemplos Básicos
1. Listar contêineres ativos:
   ```bash
   docker ps
   ```

2. Listar todos os contêineres (ativos e parados):
   ```bash
   docker ps -a
   ```

3. Exibir apenas os IDs dos contêineres:
   ```bash
   docker ps -q
   ```

4. Filtrar contêineres por estado:
   ```bash
   docker ps --filter "status=exited"
   ```

Confira exemplos detalhados em [examples.md](./examples.md).
