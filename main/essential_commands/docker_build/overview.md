
# 🐳 Comando `docker build`

O comando `docker build` é usado para criar imagens personalizadas no Docker a partir de um arquivo chamado **Dockerfile**. Este é um dos comandos mais importantes para automatizar e padronizar seus ambientes.

---

## 📌 Sintaxe
```bash
docker build [OPTIONS] PATH
```

### Componentes:
- **`PATH`**: O diretório que contém o `Dockerfile`. Pode ser um caminho relativo ou absoluto.
- **`OPTIONS`**: Configurações adicionais, como tags e cache.

---

## 🚀 Opções Principais
1. **`-t`**: Define uma tag (nome) para a imagem.
2. **`--no-cache`**: Desabilita o cache para forçar a reconstrução completa.
3. **`--build-arg`**: Passa variáveis de ambiente para o build.

---

## 🛠️ Exemplos Básicos
1. Criar uma imagem com uma tag:
   ```bash
   docker build -t minha-imagem:1.0 .
   ```

2. Forçar a reconstrução sem usar cache:
   ```bash
   docker build --no-cache -t minha-imagem:1.0 .
   ```

3. Passar argumentos para o build:
   ```bash
   docker build --build-arg ENV=production -t minha-imagem:1.0 .
   ```

- Confira exemplos detalhados em [examples.md](./examples.md).
- Finalizou? volte para [Comandos Essenciais](../essential_commands/README.md).
