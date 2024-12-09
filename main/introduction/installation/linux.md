
<div align="center">
  <h1>🐧 Instalação do Docker no Linux</h1>
  <p>Configure o Docker rapidamente no Linux e comece a rodar seus contêineres como um mestre!</p>
</div>

---

## ✅ Pré-requisitos

Antes de começar, certifique-se de que você tem:
- Uma distribuição Linux compatível (Ubuntu, Debian, Fedora, CentOS).
- Permissões de administrador (`sudo`).
- Conexão com a internet.

---

<div align="center">
  <h2>🚀 Passo a Passo</h2>
</div>

### 1️⃣ Atualize o sistema
Abra o terminal e execute:
```bash
sudo apt update && sudo apt upgrade -y
```

### 2️⃣ Instale dependências
Estas ferramentas são necessárias para adicionar o repositório do Docker:
```bash
sudo apt install -y ca-certificates curl gnupg lsb-release
```

### 3️⃣ Adicione a chave GPG do Docker
Adicione a chave de segurança do repositório oficial do Docker:
```bash
sudo mkdir -m 0755 -p /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
```

### 4️⃣ Adicione o repositório do Docker
Inclua o repositório estável na lista de fontes do seu sistema:
```bash
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
```

### 5️⃣ Instale o Docker

Agora, instale o Docker e seus componentes principais. Siga os passos abaixo:

1. Atualize a lista de pacotes:
   ```bash
   sudo apt update
   ```

2. Instale o Docker e seus pacotes necessários:
   ```bash
   sudo apt install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
   ```
   - **docker-ce**: A versão principal do Docker (Community Edition).
   - **docker-ce-cli**: A interface de linha de comando do Docker.
   - **containerd.io**: Componente para gerenciar contêineres.
   - **docker-buildx-plugin**: Ferramenta para construção avançada de imagens.
   - **docker-compose-plugin**: Suporte ao Docker Compose.

3. Verifique a instalação:
   ```bash
   docker --version
   ```

Se o comando retornar a versão do Docker, a instalação foi concluída com sucesso! 🎉
---

<div align="center">
  <h2>✨ Configuração Opcional</h2>
</div>

### Permitir uso do Docker sem `sudo`
Se preferir usar o Docker sem digitar `sudo`, adicione seu usuário ao grupo Docker:
```bash
sudo usermod -aG docker $USER
```
Reinicie sua sessão com:
```bash
newgrp docker
```

Agora, você pode usar o Docker sem precisar do `sudo`!

---

<div align="center">
  <h2>🔗 Próximos Passos</h2>
  <p>Agora que o Docker está configurado, você pode explorar:</p>
  <ul>
    <li><a href="../first_container/hello_world.md">Rodar seu primeiro contêiner</a></li>
    <li><a href="../concepts/README.md">Aprender conceitos fundamentais do Docker</a></li>
  </ul>
</div>
