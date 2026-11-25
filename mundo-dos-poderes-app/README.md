# Mundo dos Poderes — pacote multiplataforma

Este pacote mantém o jogo HTML original e adiciona uma base para instalação como PWA, Android/iOS com Capacitor e Windows com Electron.

## 1. Testar no navegador / instalar como PWA

Publique o conteúdo da pasta `public/` em um endereço HTTPS (por exemplo, GitHub Pages). Abra o endereço no navegador e use **Instalar aplicativo** ou **Adicionar à tela inicial**. O service worker guarda os arquivos principais para abrir offline depois da primeira visita.

## 2. Android (APK)

Requisitos: Node.js LTS, Android Studio e Android SDK.

```bash
npm install
npx cap add android
npm run cap:sync
npm run android:open
```

No Android Studio, use **Build > Build Bundle(s) / APK(s) > Build APK(s)**. O APK de teste ficará na pasta `android/app/build/outputs/apk/`.

## 3. iPhone / iPad

Requisitos: Mac com Xcode e as ferramentas de desenvolvimento da Apple.

```bash
npm install
npx cap add ios
npm run cap:sync
npm run ios:open
```

No Xcode, configure assinatura e equipe de desenvolvimento antes de instalar em aparelhos. Distribuir para amigos em iOS normalmente exige TestFlight ou outro método autorizado pela Apple.

## 4. Windows (instalador .exe)

Requisitos: Node.js LTS. Para compilar o instalador Windows, execute em Windows (ou use uma máquina/CI Windows):

```bash
npm install
npm run dist:win
```

O instalador será criado em `dist/`.

## Observações importantes

- O salvamento atual do jogo usa `localStorage`, então o progresso fica no dispositivo/navegador onde foi criado. Não existe sincronização automática entre amigos ou aparelhos nesta primeira versão.
- Para amigos jogarem com o mesmo link, publique `public/` em HTTPS. Para distribuir APK/EXE, gere os pacotes nas ferramentas indicadas acima.
- O código do jogo foi mantido; esta etapa acrescenta apenas arquivos de empacotamento e suporte PWA.
