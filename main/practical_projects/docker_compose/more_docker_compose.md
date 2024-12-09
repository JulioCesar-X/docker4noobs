# 🐳 Docker Compose Cheatsheet: Comandos Essenciais com Explicação

Este guia prático apresenta os principais comandos do Docker Compose, com explicações detalhadas e o que esperar como resultado. Use este cheatsheet para dominar a orquestração de contêineres! 🚀

---

## 📋 Lista de Comandos

### 1️⃣ `docker-compose up`
```bash
docker-compose up
```
- **O que faz**: Cria e inicia os serviços definidos no arquivo `docker-compose.yml`.
- **Opções comuns**:
  - `-d`: Executa os serviços em segundo plano (modo detached).
  - `--build`: Reconstrói as imagens antes de iniciar os serviços.

**Exemplo**:
```bash
docker-compose up -d --build
```
**Resultado esperado**:
- Todos os serviços definidos no `docker-compose.yml` estarão em execução.

---

### 2️⃣ `docker-compose down`
```bash
docker-compose down
```
- **O que faz**: Para e remove os contêineres, redes e volumes criados pelo `docker-compose up`.
- **Opções comuns**:
  - `--volumes`: Remove também os volumes usados pelos serviços.
  - `--rmi all`: Remove as imagens criadas pelo Compose.

**Exemplo**:
```bash
docker-compose down --volumes --rmi all
```
**Resultado esperado**:
- Todos os contêineres, volumes e imagens associados ao Compose serão removidos.

---

### 3️⃣ `docker-compose ps`
```bash
docker-compose ps
```
- **O que faz**: Lista o status de todos os serviços gerenciados pelo Compose.

**Exemplo**:
```bash
docker-compose ps
```
**Resultado esperado**:
- Uma tabela com informações como ID do contêiner, status e portas mapeadas.

---

### 4️⃣ `docker-compose logs`
```bash
docker-compose logs
```
- **O que faz**: Exibe os logs de todos os serviços.
- **Opções comuns**:
  - `-f`: Segue os logs em tempo real.
  - `service_name`: Mostra logs de um serviço específico.

**Exemplo**:
```bash
docker-compose logs -f app
```
**Resultado esperado**:
- Os logs em tempo real do serviço `app` aparecerão no terminal.

---

### 5️⃣ `docker-compose build`
```bash
docker-compose build
```
- **O que faz**: Constrói as imagens para os serviços definidos no Compose.
- **Opções comuns**:
  - `--no-cache`: Ignora o cache e força a reconstrução completa.

**Exemplo**:
```bash
docker-compose build --no-cache
```
**Resultado esperado**:
- Todas as imagens serão reconstruídas, ignorando qualquer cache existente.

---

### 6️⃣ `docker-compose restart`
```bash
docker-compose restart
```
- **O que faz**: Reinicia os serviços definidos no Compose.

**Exemplo**:
```bash
docker-compose restart
```
**Resultado esperado**:
- Todos os serviços serão parados e reiniciados.

---

### 7️⃣ `docker-compose exec`
```bash
docker-compose exec <service_name> <command>
```
- **O que faz**: Executa um comando dentro de um contêiner em execução.

**Exemplo**:
```bash
docker-compose exec app bash
```
**Resultado esperado**:
- Você terá acesso ao terminal do serviço `app`.

---

### 8️⃣ `docker-compose stop`
```bash
docker-compose stop
```
- **O que faz**: Para os serviços em execução, mas mantém os contêineres.

**Exemplo**:
```bash
docker-compose stop
```
**Resultado esperado**:
- Os serviços serão parados, mas os contêineres permanecerão disponíveis para reinício.

---

## 📝 Resultado Final

Com esses comandos, você pode gerenciar seus contêineres Docker Compose com facilidade. Lembre-se de usar as opções adicionais para personalizar sua experiência.

---

<div align="center">
  <h2>🔗 Próximos Passos</h2>
  <p>Explore mais sobre Docker Compose:</p>
  <ul>
    <li><a href="./README.md">Voltar para o tutorial de Docker Compose</a></li>
    <li><a href="../README.md">Voltar para Projetos Práticos</a></li>
  </ul>
</div>
