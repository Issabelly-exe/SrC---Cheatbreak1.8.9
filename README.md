<!-- Banner -->
<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=rect&color=0:7F7FD5,100:86A8E7&height=120&section=header&text=CheatBreaker%201.8.9&fontColor=ffffff&fontSize=38&fontAlignY=35&desc=Minecraft%20Client%20%7C%20Java%208%20%7C%20Gradle&descAlignY=70" alt="CheatBreaker Banner">
</p>

# ✨ CheatBreaker (Client 1.8.9)

<p align="center">
  <a href="https://www.minecraft.net"><img src="https://img.shields.io/badge/Minecraft-1.8.9-3C873A?logo=minecraft&logoColor=white" alt="Minecraft 1.8.9"></a>
  <a href="https://adoptium.net/releases.html?variant=openjdk8"><img src="https://img.shields.io/badge/Java-8-007396?logo=java&logoColor=white" alt="Java 8"></a>
  <a href="https://gradle.org/"><img src="https://img.shields.io/badge/Build-Gradle-02303A?logo=gradle&logoColor=white" alt="Gradle"></a>
  <a href="https://imperceptiblethoughts.com/shadow/"><img src="https://img.shields.io/badge/Shadow%20Jar-enabled-6E40C9" alt="Shadow Jar"></a>
  <img src="https://img.shields.io/badge/Plataformas-Windows%20%7C%20macOS%20%7C%20Linux-666666" alt="Plataformas">
</p>

> 🎮 Cliente para Minecraft 1.8.9 construído em Java 8, com módulos, overlays, Discord RPC, amigos, cosméticos e muito mais.

Cliente para Minecraft 1.8.9 construído em Java 8. O projeto inclui um conjunto de módulos e utilitários focados em experiência do jogador, sobreposições (overlay), integração com Discord (RPC), sistema de amigos, cosméticos e vários gerenciadores de recursos.

Este repositório utiliza Gradle e gera um JAR “fat” (sombrado) com todas as dependências necessárias para distribuição.

## 🧭 Visão geral
- Versão alvo do Minecraft: 1.8.9
- Linguagem/SDK: Java 8
- Build: Gradle (com Wrapper incluso)
- Saída: artefato sombreado via plugin Shadow Jar

## 🧩 Principais funcionalidades (não exaustivo)
- Overlay de HUD e elementos de UI personalizáveis
- Módulos diversos (ex.: keystrokes) via ModuleManager
- Sistema de configuração e perfis (ConfigManager)
- Integração com Discord Rich Presence (RPC)
- Sistema de amigos (FriendsManager)
- Suporte a cosméticos e assets remotos (CosmeticManager; WSNetHandler)
- Títulos e borda do mundo (TitleManager / WorldBorderManager)
- Eventos e barramento (EventBus)

📁 Pastas/classes de referência:
- `com.cheatbreaker.client.CheatBreaker` — ponto central de inicialização do cliente
- `ui/` — UI, menus e overlay
- `module/` — módulos do cliente
- `network/` — comunicação (plugin messages / WebSocket)
- `util/` — utilitários (Discord RPC, sessões, etc.)

## ✅ Requisitos
- JDK 8 (Java 1.8)
- Acesso à internet para recursos opcionais (ex.: Discord RPC, servidores de assets)
- Windows/macOS/Linux suportados para build via Gradle; execução final depende do ambiente de Minecraft 1.8.9

## 🛠️ Como compilar
Use o Gradle Wrapper incluído no repositório (não é necessário ter Gradle instalado globalmente).

No Windows (PowerShell ou Prompt):
```
./gradlew.bat clean build
```

No macOS/Linux (Shell):
```
./gradlew clean build
```

Isso irá:
1. Resolver dependências
2. Gerar recursos automáticos (ex.: `app.properties` com informações de versão/commit, quando disponíveis)
3. Compilar o código
4. Executar o empacotamento Shadow (JAR “all”)

### 📦 Artefatos gerados
- JAR padrão: `build/libs/CheatBreaker-Beta.jar`
- JAR sombreado (recomendado): `build/libs/CheatBreaker-Beta-all.jar`

Observação: o nome pode variar conforme o `version` em `build.gradle`.

## 🧪 Testes
Se existirem testes em `src/test/java`, você pode executá-los com:
```
./gradlew.bat test
```
(ou `./gradlew test` em Unix-like)

## 🚀 Execução
Este projeto gera um cliente para o ecossistema Minecraft 1.8.9. A execução final normalmente requer integração com um launcher/ambiente compatível e bibliotecas nativas adequadas da versão 1.8.9. O repositório não fornece um launcher pronto para produção.

## 🗂️ Estrutura do projeto (resumo)
```
Client-1.8.9/
├─ build.gradle           # Configuração de build (Shadow, dependências, tasks)
├─ settings.gradle        # Nome do projeto
├─ src/
│  ├─ main/java/          # Código-fonte principal
│  ├─ main/resources/     # Recursos (inclui assets e META-INF)
│  └─ test/java/          # Testes (quando houver)
├─ gradle/                # Wrapper do Gradle
└─ natives/, obf/         # Recursos específicos do ambiente Minecraft (se aplicável)
```

## 💡 Dicas e observações
- O processo de build gera `assets/minecraft/client/properties/app.properties` com informações de versão/commit quando disponíveis (tarefa `generateAppProperties`).
- O JAR `-all` contém dependências empacotadas e é o indicado para distribuição do cliente.
- Algumas funcionalidades (ex.: Discord RPC) são opcionais e controladas por configurações no runtime.

## 🤝 Contribuindo
1. Faça um fork do repositório
2. Crie um branch de feature: `git checkout -b feature/minha-feature`
3. Commit suas mudanças: `git commit -m "Descrição da mudança"`
4. Envie o branch: `git push origin feature/minha-feature`
5. Abra um Pull Request descrevendo claramente o que foi alterado e por quê

Siga boas práticas:
- Mantenha compatibilidade com Java 8
- Evite introduzir dependências desnecessárias
- Adicione comentários quando mexer em partes críticas (ex.: inicialização, rede, rendering)

## ⚖️ Aviso legal
- Este repositório é fornecido “no estado em que se encontra”, sem garantias. Use por sua conta e risco.
- O uso do cliente pode estar sujeito às regras de servidores de terceiros. Respeite os termos de uso das plataformas onde você joga.
- Marcas comerciais e nomes de terceiros pertencem aos seus respectivos proprietários.

## 📝 Licença
Nenhuma licença explícita foi incluída neste repositório até o momento. Na ausência de uma licença, todas as permissões são reservadas pelo(s) autor(es). Se você pretende reutilizar o código, abra uma issue/PR para discutir a inclusão de uma licença adequada.

## 🙌 Créditos
- Comunidade de código aberto e bibliotecas utilizadas (consulte `build.gradle`)
- Agradecimentos aos contribuidores do projeto

---
Se você encontrar problemas, abra uma issue com passos claros para reprodução, logs relevantes e detalhes do ambiente (SO, versão do Java, comando de build usado).