# 🐳 Imagens e Contêineres no Docker

No Docker, **imagens** e **contêineres** são conceitos fundamentais que você precisa entender. Vamos descomplicar esses dois termos e mostrar como eles trabalham juntos. 🚀

---

## 📌 O que é uma Imagem?

Uma **imagem Docker** é como um modelo ou blueprint. Ela contém:
- Todo o software necessário para rodar um aplicativo (dependências, bibliotecas, etc.).
- Um sistema de arquivos mínimo.
- Configurações para inicializar o contêiner.

As imagens são **imutáveis**, o que significa que elas nunca mudam após serem criadas.

---

## 📦 Exemplo Prático de Imagem

Vamos usar uma imagem do Ubuntu como exemplo. No terminal, digite:
```bash
docker pull ubuntu
```

Isso baixa a imagem oficial do Ubuntu para sua máquina.

---

## 📌 O que é um Contêiner?

Um **contêiner Docker** é uma instância de uma imagem. Ele é como um aplicativo em execução, criado a partir do blueprint da imagem.

Um contêiner é:
- Isolado: Não interfere no sistema operacional do host.
- Portável: Pode ser executado em qualquer máquina com Docker instalado.

---

## 🚀 Como Funcionam Juntos?

1. **Imagem**: O "modelo".
2. **Contêiner**: Uma cópia funcional da imagem, pronta para uso.

Por exemplo:
- Você baixa a imagem do NGINX (servidor web).
- Cria um contêiner a partir dela e o executa.

---

## 🛠️ Exemplo: Criando e Rodando um Contêiner

1. Baixe a imagem do NGINX:
   ```bash
   docker pull nginx
   ```

2. Crie e execute um contêiner:
   ```bash
   docker run -d -p 8080:80 nginx
   ```

3. Acesse o servidor:
   - Abra o navegador e acesse: `http://localhost:8080`.

---

## 📝 Diferença Resumida

| **Imagem**                  | **Contêiner**                |
|-----------------------------|------------------------------|
| Modelo ou blueprint.         | Instância funcional da imagem. |
| É imutável.                  | Pode ser iniciado, parado e removido. |
| Não consome recursos.        | Consome recursos enquanto está em execução. |

---

<div align="center">
  <h2>🔗 Próximos Passos</h2>
  <p>Agora que você entende imagens e contêineres, explore o próximo conceito:</p>
  <ul>
    <li><a href="../dockerfile/dockerfile_basics.md">Aprenda sobre Dockerfile</a></li>
    <li><a href="../README.md">Voltar para os Conceitos</a></li>
  </ul>
</div>
