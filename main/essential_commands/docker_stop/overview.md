# 🐳 Comando `docker stop`

O comando `docker stop` é usado para parar contêineres em execução no Docker. Ele envia um sinal de término ao contêiner, encerrando-o de forma limpa.

---

## 📌 Sintaxe
```bash
docker stop [OPTIONS] CONTAINER [CONTAINER...]
```

### Componentes:
- **`CONTAINER`**: O nome ou ID do contêiner que você deseja parar.
- **`OPTIONS`**: Configurações adicionais, como tempo limite para encerramento.

---

## 🚀 Opções Principais
1. **`--time` ou `-t`**: Define o tempo (em segundos) antes de forçar o encerramento do contêiner (padrão: 10 segundos).

---

## 🛠️ Exemplos Básicos
1. Parar um contêiner específico:
   ```bash
   docker stop meu-container
   ```

2. Parar múltiplos contêineres:
   ```bash
   docker stop container1 container2 container3
   ```

3. Parar um contêiner com tempo personalizado:
   ```bash
   docker stop -t 5 meu-container
   ```

- Confira exemplos detalhados em [examples.md](./examples.md).
- Finalizou? volte para [Comandos Essenciais](../README.md).
