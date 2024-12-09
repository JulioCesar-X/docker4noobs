
# 🐳 Introdução a Volumes no Docker

Volumes no Docker são usados para armazenar dados persistentes que não se perdem quando o contêiner é removido. Eles permitem que seus dados sobrevivam ao ciclo de vida dos contêineres, sendo uma ferramenta essencial para muitos casos de uso.

---

## 📌 O que é um Volume?

Um volume:
- Armazena dados fora do sistema de arquivos do contêiner.
- É gerenciado pelo Docker e pode ser acessado por múltiplos contêineres.
- É ideal para armazenar bancos de dados, logs ou outros dados importantes.

---

## 🚀 Como Volumes Funcionam?

### Sem Volume:
Se você criar um arquivo dentro de um contêiner, ele será perdido assim que o contêiner for removido:
```bash
docker run -it ubuntu bash
touch /meu-arquivo
exit
docker rm <container_id>
```
Resultado: o arquivo criado será perdido.

### Com Volume:
Quando você usa volumes, os dados são persistentes, mesmo que o contêiner seja removido:
```bash
docker run -v meu-volume:/dados -it ubuntu bash
touch /dados/meu-arquivo
exit
docker rm <container_id>
docker run -v meu-volume:/dados -it ubuntu bash
ls /dados
```
Resultado: o arquivo ainda estará no volume.

---

## 🛠️ Criando e Usando Volumes

1. **Criar um volume**:
   ```bash
   docker volume create meu-volume
   ```

2. **Usar o volume em um contêiner**:
   ```bash
   docker run -v meu-volume:/dados -it ubuntu bash
   ```

3. **Verificar volumes existentes**:
   ```bash
   docker volume ls
   ```

4. **Remover um volume**:
   ```bash
   docker volume rm meu-volume
   ```

---

## 📝 Por que usar Volumes?

1. **Persistência**: Dados sobrevivem ao ciclo de vida dos contêineres.
2. **Compartilhamento**: Múltiplos contêineres podem acessar o mesmo volume.
3. **Desempenho**: Mais rápido e eficiente do que montar diretórios do host.

---

<div align="center">
  <h2>🔗 Próximos Passos</h2>
  <p>Explore mais sobre volumes:</p>
  <ul>
    <li><a href="./examples.md">Veja exemplos práticos de uso</a></li>
    <li><a href="../README.md">Voltar para os Conceitos</a></li>
  </ul>
</div>
