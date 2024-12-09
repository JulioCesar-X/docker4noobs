# 🐳 Exemplos Práticos de Redes no Docker

Aqui estão exemplos detalhados para configurar e usar redes no Docker, incluindo explicações claras dos comandos e os resultados esperados. 🛠️

---

## 📦 Exemplo 1: Criando e Usando uma Rede Personalizada

1. **Crie uma rede chamada `minha-rede`:**
   ```bash
   docker network create minha-rede
   ```
   - **`docker network create`**: Cria uma nova rede.
   - **`minha-rede`**: Nome atribuído à rede.

   **Saída esperada**:
   ```bash
   docker network ls
   ```
   Resultado:
   ```
   NETWORK ID     NAME          DRIVER    SCOPE
   abc123456789   minha-rede    bridge    local
   ```

2. **Crie dois contêineres conectados à rede:**
   ```bash
   docker run -dit --name container1 --network minha-rede ubuntu bash
   docker run -dit --name container2 --network minha-rede ubuntu bash
   ```
   - **`--name`**: Define um nome para os contêineres (`container1`, `container2`).
   - **`--network minha-rede`**: Conecta os contêineres à rede personalizada.

3. **Teste a comunicação entre os contêineres:**
   - No terminal do `container1`:
     ```bash
     docker exec -it container1 bash
     ping container2
     ```
   - **O que esperar?**: O comando `ping` mostrará respostas do `container2`, confirmando que os dois contêineres podem se comunicar na mesma rede.

   Resultado esperado:
   ```
   PING container2 (172.18.0.3): 56 data bytes
   64 bytes from 172.18.0.3: icmp_seq=1 ttl=64 time=0.123 ms
   ```

---

## 📦 Exemplo 2: Conexão a Múltiplas Redes

1. **Crie duas redes:**
   ```bash
   docker network create rede1
   docker network create rede2
   ```

2. **Inicie um contêiner conectado a ambas as redes:**
   ```bash
   docker run -dit --name multi-network --network rede1 ubuntu bash
   docker network connect rede2 multi-network
   ```
   - **`docker network connect`**: Conecta o contêiner a uma rede adicional.

3. **Verifique as redes do contêiner:**
   ```bash
   docker inspect multi-network
   ```
   - **O que esperar?**: O contêiner estará listado nas duas redes.

   Resultado esperado (parte do JSON):
   ```
   "Networks": {
       "rede1": {
           "IPAddress": "172.19.0.2",
           ...
       },
       "rede2": {
           "IPAddress": "172.20.0.2",
           ...
       }
   }
   ```

---

## 📦 Exemplo 3: Rede `host`

1. **Inicie um contêiner na rede `host`:**
   ```bash
   docker run --network host -dit ubuntu bash
   ```
   - **`--network host`**: Usa a rede do host para o contêiner.

2. **Teste a conectividade com a rede local:**
   - No contêiner, execute:
     ```bash
     curl ifconfig.me
     ```
   - **O que esperar?**: O IP retornado será o mesmo da máquina host, já que o contêiner compartilha a rede do host.

   Resultado esperado:
   ```
   192.168.1.100
   ```

---

<div align="center">
  <h2>🔗 Próximos Passos</h2>
  <p>Explore mais sobre redes e configurações avançadas:</p>
  <ul>
    <li><a href="./networks_basics.md">Voltar para Introdução a Redes</a></li>
    <li><a href="../README.md">Voltar para os Conceitos</a></li>
  </ul>
</div>
