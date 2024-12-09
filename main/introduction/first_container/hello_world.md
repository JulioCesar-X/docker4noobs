
<div align="center">
  <h1>🌍 Rodando seu Primeiro Contêiner!</h1>
  <p>Chegou a hora de colocar o Docker para trabalhar! Vamos rodar o clássico contêiner <strong>Hello, World!</strong> e garantir que sua instalação está funcionando.</p>
</div>

---

## O que você vai aprender?

- Rodar seu primeiro contêiner Docker.
- Confirmar que a instalação do Docker está funcionando corretamente no **Linux**, **Windows** e **macOS**.
- Compreender o básico sobre como o Docker executa um contêiner.

---

<div align="center">
  <h2>🐧 Para Linux</h2>
</div>

1. Abra o terminal e execute o seguinte comando:
   ```bash
   docker run hello-world
   ```

2. O Docker fará o seguinte:
   - Buscará a imagem `hello-world` no Docker Hub.
   - Baixará a imagem caso ela ainda não esteja no seu sistema.
   - Criará e executará um contêiner a partir da imagem.
   - Exibirá a mensagem de boas-vindas do Docker.

3. Se tudo der certo, você verá algo assim no terminal:
   ```
   Hello from Docker!
   This message shows that your installation appears to be working correctly.
   ```

---

<div align="center">
  <h2>🖥️ Para Windows</h2>
</div>

1. Abra o **PowerShell** ou o **Prompt de Comando** e digite:
   ```bash
   docker run hello-world
   ```

2. O Docker realizará as mesmas etapas:
   - Buscará e baixará a imagem `hello-world` (se necessário).
   - Criará e executará o contêiner.
   - Mostrará a mensagem de boas-vindas no terminal.

3. Resultado esperado:
   ```
   Hello from Docker!
   This message shows that your installation appears to be working correctly.
   ```

---

<div align="center">
  <h2>🍎 Para macOS</h2>
</div>

1. No **Terminal**, execute o comando:
   ```bash
   docker run hello-world
   ```

2. Assim como nos outros sistemas, o Docker:
   - Baixará a imagem `hello-world` (se necessário).
   - Criará um contêiner e o executará.
   - Exibirá a mensagem de sucesso.

3. Mensagem esperada:
   ```
   Hello from Docker!
   This message shows that your installation appears to be working correctly.
   ```

---

<div align="center">
  <h2>🎉 Conclusão</h2>
</div>

- Se você viu a mensagem de sucesso do Docker, parabéns! 🎉 Você rodou seu primeiro contêiner.
- Caso tenha encontrado algum erro, verifique se o Docker está instalado corretamente e se o serviço está em execução.

---

<div align="center">
  <h2>🔗 Próximos Passos</h2>
  <p>Agora que você rodou seu primeiro contêiner, continue aprendendo:</p>
  <ul>
    <li><a href="../../concepts/README.md">Aprenda mais sobre conceitos do Docker</a></li>
    <li><a href="../../essential_commands/README.md">Descubra comandos essenciais do Docker</a></li>
  </ul>
</div>
