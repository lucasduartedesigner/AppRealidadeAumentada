# Guia de Compilação: App de Realidade Aumentada com Unity

Este documento descreve o processo para configurar o ambiente de desenvolvimento, clonar o projeto e compilá-lo para a plataforma Android.

## Pré-requisitos

Antes de começar, certifique-se de que você possui as seguintes ferramentas instaladas:

- **Git:** Para clonar o repositório.
  - [Download do Git](https://git-scm.com/downloads)
- **Unity Hub:** Para gerenciar as versões do Unity e os projetos.
  - [Download do Unity Hub](https://unity.com/download)
- **Unity Editor (Versão 2021.3.1f1 ou superior):** O projeto foi criado nesta versão. Para evitar problemas de compatibilidade, é crucial instalar o módulo de **Android Build Support**.
  - Durante a instalação do Editor pelo Unity Hub, marque a opção:
    - `Android Build Support`
      - `OpenJDK`
      - `Android SDK & NDK Tools`

---

## Método 1: Compilar o APK Diretamente do Unity (Recomendado)

Este é o caminho mais rápido e direto para gerar um arquivo de aplicativo (`.apk`) que pode ser instalado em qualquer dispositivo Android.

### 1. Clonar o Repositório

Abra um terminal ou Git Bash e execute o seguinte comando para baixar o projeto:

```bash
git clone [https://github.com/lucasduartedesigner/AppRealidadeAumentada.git](https://github.com/lucasduartedesigner/AppRealidadeAumentada.git)
```

### 2. Abrir o Projeto no Unity

1.  Abra o **Unity Hub**.
2.  Na aba **Projects**, clique em **Open**.
3.  Navegue até a pasta `AppRealidadeAumentada` que você acabou de clonar e selecione-a.
4.  Aguarde o Unity importar e carregar o projeto. Isso pode levar alguns minutos.

### 3. Compilar (Build) para Android

1.  Com o projeto aberto no Unity, vá ao menu **File > Build Settings**.
2.  Na lista **Platform**, selecione **Android**.
3.  Se a plataforma atual não for Android, clique no botão **Switch Platform** e aguarde o processo terminar.
4.  (Opcional mas recomendado) Clique em **Player Settings...** e, nas configurações que se abrem, vá para **Other Settings > Identification**. Altere o **Package Name** para um nome único (ex: `com.seu-nome.realidade-aumentada`).
5.  Feche a janela de `Project Settings` e volte para `Build Settings`.
6.  Clique em **Build**.
7.  Escolha um local e um nome para o seu arquivo (ex: `AppRA.apk`) e clique em **Save**.

O Unity irá compilar o projeto e gerar o arquivo `.apk` no local escolhido. Este arquivo está pronto para ser transferido e instalado em um dispositivo Android.

---

## Método 2: Exportar para Android Studio (Avançado)

Use este método apenas se precisar fazer modificações nativas no projeto Android (como adicionar permissões complexas, integrar bibliotecas Java/Kotlin, etc.).

### 1. Siga os Passos 1 e 2 do Método 1

Certifique-se de que o projeto está aberto e funcionando no Unity.

### 2. Exporte o Projeto

1.  No Unity, vá ao menu **File > Build Settings**.
2.  Selecione a plataforma **Android**.
3.  Marque a caixa de seleção **Export Project**.
4.  Clique no botão **Export**.
5.  Selecione uma **pasta vazia** onde o Unity salvará os arquivos do projeto Android.

### 3. Abra e Compile no Android Studio

1.  Abra o **Android Studio**.
2.  Na tela inicial, selecione **Open** (ou vá em `File > Open`).
3.  Navegue e selecione a pasta que você exportou do Unity.
4.  Aguarde o Android Studio sincronizar o projeto com o Gradle.
5.  Após a sincronização, vá ao menu **Build > Build Bundle(s) / APK(s) > Build APK(s)**.

Quando a compilação terminar, uma notificação aparecerá com um link para localizar (`locate`) o arquivo `.apk` gerado.
