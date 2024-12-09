# 🐳 Exemplos de Uso do `docker ps`

Aqui estão exemplos práticos para ajudar você a dominar o comando `docker ps`.

---

## 📦 Listando Contêineres

1. **Contêineres ativos**:
   Para listar apenas os contêineres em execução:
   ```bash
   docker ps
   ```

2. **Todos os contêineres (ativos e parados)**:
   Inclua a opção `-a` para listar todos os contêineres:
   ```bash
   docker ps -a
   ```

---

## 🚀 Filtrando Contêineres

1. **Filtrar por estado**:
   Listar apenas os contêineres parados:
   ```bash
   docker ps --filter "status=exited"
   ```

2. **Filtrar por nome**:
   Listar contêineres cujo nome contém "meu-app":
   ```bash
   docker ps --filter "name=meu-app"
   ```

---

## 🛠️ Personalizando a Saída

1. **Exibir apenas os IDs dos contêineres**:
   Use a opção `-q`:
   ```bash
   docker ps -q
   ```

2. **Formato personalizado**:
   Para exibir apenas o nome e a porta do contêiner:
   ```bash
   docker ps --format "table {{.Names}}	{{.Ports}}"
   ```

Para mais informações, volte para [overview.md](./overview.md).
