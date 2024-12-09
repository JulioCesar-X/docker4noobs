
<div align="center">
  <h1>🖥️ Instalação do Docker no Windows</h1>
  <p>Configure o Docker no Windows com facilidade e aproveite o poder dos contêineres!</p>
</div>

---

## ✅ Pré-requisitos

Antes de começar, certifique-se de que você tem:
- Windows 10 ou 11 (64 bits) com suporte ao WSL 2 (Windows Subsystem for Linux).
- Permissões de administrador na máquina.
- Conexão com a internet.

---

<div align="center">
  <h2>🚀 Passo a Passo</h2>
</div>

### 1️⃣ Baixe o Docker Desktop

1. Acesse o site oficial do Docker: [Docker Desktop para Windows](https://www.docker.com/products/docker-desktop).
2. Clique no botão de download e salve o instalador.

---

### 2️⃣ Habilite o WSL 2

O Docker Desktop requer o **Windows Subsystem for Linux (WSL 2)** para rodar. Ative-o seguindo os passos abaixo:

1. Abra o **PowerShell** como administrador e execute:
   ```bash
   wsl --install
   ```
   Esse comando habilitará o WSL e instalará a distribuição padrão do Linux.
2. Reinicie o computador, caso seja solicitado.

---

### 3️⃣ Instale o Docker Desktop

1. Abra o instalador que você baixou no primeiro passo.
2. Siga as instruções do instalador. Certifique-se de que a opção **WSL 2 backend** esteja habilitada durante a instalação.
3. Após a instalação, inicie o Docker Desktop e conclua as configurações iniciais.

---

<div align="center">
  <h2>🛠️ Testando a Instalação</h2>
</div>

### Verifique se o Docker está instalado

No **PowerShell** ou terminal, digite:
```bash
docker --version
```

Se o comando retornar a versão do Docker, sua instalação foi bem-sucedida! 🎉

---

<div align="center">
  <h2>🔗 Próximos Passos</h2>
  <p>Agora que o Docker está configurado, explore:</p>
  <ul>
    <li><a href="../first_container/hello_world.md">Rodar seu primeiro contêiner</a></li>
    <li><a href="../concepts/README.md">Aprender conceitos fundamentais do Docker</a></li>
  </ul>
</div>
