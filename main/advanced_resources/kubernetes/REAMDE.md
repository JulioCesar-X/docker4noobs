
# 🛠️ Introdução ao Kubernetes

O **Kubernetes**, muitas vezes abreviado como **K8s**, é uma plataforma de orquestração de contêineres poderosa e amplamente usada. Ele ajuda a gerenciar múltiplos contêineres em escala, garantindo alta disponibilidade, escalabilidade e automação. 🚀

---

## 📋 O que você vai aprender?

- O que é Kubernetes e por que usá-lo.
- Principais componentes do Kubernetes.
- Como funciona o ciclo de vida de um aplicativo no Kubernetes.
---

## 🌟 O que é o Kubernetes?

O Kubernetes é uma plataforma de código aberto criada pela Google, que permite:
- Gerenciar múltiplos contêineres em clusters de servidores.
- Automatizar o deployment, escalonamento e manutenção de aplicativos.
- Garantir que suas aplicações estejam sempre disponíveis, mesmo em caso de falhas.

**Por que escolher o Kubernetes?**
- Ele resolve os desafios de gerenciar múltiplos contêineres manualmente.
- Oferece suporte nativo para recuperação de falhas, escalonamento automático e distribuição de carga.

---

## 🧩 Componentes Principais do Kubernetes

1. **Cluster**:
   - Um conjunto de máquinas que executam o Kubernetes.
   - Dividido em **nós de controle** (Control Plane) e **nós de trabalho** (Worker Nodes).

2. **Pod**:
   - A menor unidade do Kubernetes.
   - Um Pod pode conter um ou mais contêineres que compartilham armazenamento e rede.

3. **Deployment**:
   - Gerencia o ciclo de vida dos Pods.
   - Garante que um número desejado de Pods esteja sempre rodando.

4. **Service**:
   - Um ponto de acesso estável para os Pods.
   - Gerencia a comunicação entre os Pods e com o mundo externo.

5. **ConfigMap** e **Secrets**:
   - Usados para gerenciar configurações e credenciais de forma segura.

6. **Ingress**:
   - Gerencia acesso externo para os serviços do cluster, incluindo balanceamento de carga e HTTPS.

---

## 🚀 Ciclo de Vida de um Aplicativo no Kubernetes

1. **Criar o Manifesto**:
   - Um arquivo YAML define o estado desejado do aplicativo (exemplo: número de réplicas, imagem do contêiner, etc.).
   ```yaml
   apiVersion: apps/v1
   kind: Deployment
   metadata:
     name: exemplo-app
   spec:
     replicas: 2
     selector:
       matchLabels:
         app: exemplo
     template:
       metadata:
         labels:
           app: exemplo
       spec:
         containers:
         - name: exemplo-container
           image: nginx:latest
           ports:
           - containerPort: 80
   ```

2. **Aplicar o Manifesto**:
   - Use o comando `kubectl` para criar ou atualizar os recursos no cluster:
     ```bash
     kubectl apply -f exemplo-deployment.yaml
     ```

3. **Verificar o Status**:
   - Monitore o status dos Pods e Deployments:
     ```bash
     kubectl get pods
     kubectl get deployments
     ```

4. **Escalonar o Aplicativo**:
   - Aumente ou reduza o número de réplicas:
     ```bash
     kubectl scale deployment exemplo-app --replicas=5
     ```

5. **Expor o Serviço**:
   - Torne o aplicativo acessível:
     ```bash
     kubectl expose deployment exemplo-app --type=LoadBalancer --port=80
     ```

---

## 🛠️ Links Úteis

- Explore mais sobre [Docker Swarm](../docker_swarm/README.md), uma alternativa para orquestração de contêineres.
- Volte para a [Introdução do Guia Docker4Noobs](../../introduction/README.md).

---

## 📝 Resultado Final

Após explorar o Kubernetes, você terá o poder de gerenciar múltiplos contêineres em escala, automatizando e simplificando operações complexas. O Kubernetes é uma das ferramentas mais avançadas disponíveis para arquiteturas modernas baseadas em contêineres.

---

<div align="center">
  <h2>🐳 Parabéns por Avançar para Kubernetes! 🐳</h2>
  <p>Continue explorando, aprendendo e dominando o universo da orquestração de contêineres!</p>
</div>
