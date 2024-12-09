# 🛠️ Introdução ao Docker Swarm

O **Docker Swarm** é uma ferramenta nativa do Docker para orquestração de contêineres. Ele permite criar e gerenciar clusters de contêineres com facilidade, garantindo alta disponibilidade, escalabilidade e simplicidade na implantação. 🚀

---

## 📋 O que você vai aprender?

- O que é Docker Swarm e por que usá-lo.
- Principais conceitos e componentes do Docker Swarm.
- Como configurar e gerenciar um cluster Swarm.

---

## 🌟 O que é Docker Swarm?

Docker Swarm é um modo nativo integrado ao Docker que transforma vários servidores em um cluster unificado para gerenciar contêineres. Ele é conhecido por:
- **Simplicidade**: Interface direta para usuários do Docker.
- **Escalabilidade**: Gerencia múltiplos nós em um cluster.
- **Alta Disponibilidade**: Garante que seus serviços continuem funcionando mesmo em caso de falhas.

---

## 🧩 Componentes Principais do Docker Swarm

1. **Swarm Manager**:
   - Coordena o cluster e distribui tarefas para os nós.
   - Realiza balanceamento de carga entre os serviços.

2. **Worker Nodes**:
   - Executam as tarefas designadas pelo manager.
   - Podem ser adicionados ou removidos dinamicamente.

3. **Services**:
   - Representam os aplicativos em execução no cluster.
   - Gerenciam o ciclo de vida dos contêineres.

4. **Tasks**:
   - Unidades de trabalho que representam um único contêiner.

---

## 🚀 Configurando um Cluster Docker Swarm

1. **Inicializar o Swarm**:
   ```bash
   docker swarm init
   ```
   - **Saída esperada**: Um comando de token será exibido para adicionar nós ao cluster.

2. **Adicionar Nós ao Cluster**:
   - Nos outros servidores, execute:
     ```bash
     docker swarm join --token <TOKEN> <MANAGER_IP>:2377
     ```
   - **Saída esperada**:
     ```
     This node joined a swarm as a worker.
     ```

3. **Verificar os Nós no Cluster**:
   ```bash
   docker node ls
   ```
   - **Saída esperada**: Lista de todos os nós no cluster, incluindo seus status.

---

## 🛠️ Criando e Gerenciando Serviços

1. **Criar um Serviço**:
   ```bash
   docker service create --name web-service -p 8080:80 nginx
   ```
   - **`--name web-service`**: Define o nome do serviço.
   - **`-p 8080:80`**: Mapeia a porta 8080 do host para a porta 80 do contêiner.
   - **`nginx`**: Usa a imagem do NGINX.

2. **Escalonar o Serviço**:
   ```bash
   docker service scale web-service=5
   ```
   - Isso cria 5 réplicas do serviço.

3. **Verificar o Status dos Serviços**:
   ```bash
   docker service ls
   ```

4. **Remover um Serviço**:
   ```bash
   docker service rm web-service
   ```

---

## 🌐 Balanceamento de Carga

- O Docker Swarm distribui automaticamente o tráfego entre os contêineres do mesmo serviço, usando balanceamento de carga interno.
- Isso garante alta disponibilidade e uso eficiente dos recursos do cluster.

---

## 🛠️ Links Úteis

- Explore mais sobre [Kubernetes](../kubernetes/README.md), uma plataforma de orquestração avançada.
- Volte para a [Introdução do Guia Docker4Noobs](../../introduction/README.md).

---

## 📝 Resultado Final

Após explorar o Docker Swarm, você estará preparado para gerenciar clusters de contêineres com facilidade, garantindo escalabilidade e resiliência em seus aplicativos.

---

<div align="center">
  <h2>🐳 Parabéns por Explorar Docker Swarm! 🐳</h2>
  <p>Continue aprendendo e dominando o universo da orquestração de contêineres!</p>
</div>
