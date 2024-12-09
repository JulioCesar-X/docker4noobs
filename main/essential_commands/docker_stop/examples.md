# 🐳 Exemplos de Uso do `docker stop`

Aqui estão exemplos práticos para ajudar você a dominar o comando `docker stop`.

---

## 📦 Parando Contêineres

1. **Parar um contêiner específico**:
   ```bash
   docker stop meu-container
   ```
   - **`meu-container`**: Nome ou ID do contêiner.

2. **Parar múltiplos contêineres ao mesmo tempo**:
   ```bash
   docker stop container1 container2 container3
   ```
   - Liste todos os contêineres que deseja parar.

---

## 🚀 Definindo Tempo para Encerramento

1. **Parar com tempo limite personalizado**:
   ```bash
   docker stop -t 5 meu-container
   ```
   - O Docker esperará 5 segundos antes de forçar o encerramento.

2. **Comportamento padrão (10 segundos)**:
   Sem a opção `-t`, o Docker usará o padrão de 10 segundos:
   ```bash
   docker stop meu-container
   ```

---

## 🛠️ Verificando Contêineres Após Parar

1. **Verifique contêineres parados**:
   ```bash
   docker ps -a --filter "status=exited"
   ```

2. **Reinicie um contêiner parado**:
   ```bash
   docker start meu-container
   ```

Para mais informações, volte para [overview.md](./overview.md).
