
# 🐳 Introdução a Redes no Docker

No Docker, as redes permitem que os contêineres se comuniquem entre si e com o mundo exterior. Entender como as redes funcionam é essencial para construir aplicações distribuídas e conectadas.

---

## 📌 O que é uma Rede no Docker?

Uma rede no Docker é um ambiente virtual que conecta contêineres, permitindo:
- **Comunicação entre contêineres** na mesma rede.
- **Isolamento** entre diferentes redes.
- **Conexão com a internet**, se necessário.

---

## 🚀 Tipos de Redes no Docker

1. **`bridge`** (padrão):
   - Ideal para contêineres no mesmo host.
   - Os contêineres podem se comunicar entre si usando nomes ou IPs.

2. **`host`**:
   - Compartilha a rede do host.
   - Não há isolamento entre contêiner e host.

3. **`none`**:
   - Remove o acesso à rede.
   - Útil para contêineres que não precisam de conectividade.

4. **Redes personalizadas**:
   - Criadas pelo usuário para controlar configurações específicas, como sub-redes e gateways.

---

## 🛠️ Comandos Básicos para Redes

1. **Listar redes existentes**:
   ```bash
   docker network ls
   ```
   - Exibe todas as redes criadas pelo Docker.

2. **Criar uma rede personalizada**:
   ```bash
   docker network create minha-rede
   ```
   - Cria uma rede com o nome `minha-rede`.

3. **Conectar um contêiner a uma rede**:
   ```bash
   docker network connect minha-rede meu-container
   ```
   - Conecta o contêiner `meu-container` à rede `minha-rede`.

4. **Desconectar um contêiner de uma rede**:
   ```bash
   docker network disconnect minha-rede meu-container
   ```
   - Remove o contêiner `meu-container` da rede `minha-rede`.

---

## 📝 Benefícios das Redes no Docker

- **Isolamento**: Garantem que os contêineres só possam se comunicar quando necessário.
- **Escalabilidade**: Permitem configurar redes complexas para múltiplos serviços.
- **Facilidade de Configuração**: A comunicação entre contêineres na mesma rede é automática.

---

<div align="center">
  <h2>🔗 Próximos Passos</h2>
  <p>Explore mais sobre redes:</p>
  <ul>
    <li><a href="./examples.md">Veja exemplos práticos de redes no Docker</a></li>
    <li><a href="../README.md">Voltar para os Conceitos</a></li>
  </ul>
</div>
