# GitHub Actions — compilador APK do emulador Mophun

Este pequeno repositório faz o GitHub Actions compilar o projeto de código aberto AbyssME, que inclui suporte experimental a jogos Mophun `.mpn`, e disponibiliza o APK como artefato para baixar.

O workflow usa o código oficial de `EriArk/JavaEmulator` e não inclui jogos comerciais. A compatibilidade Mophun é experimental; compilar o APK não garante que todo jogo funcione.

## Como usar pelo celular Android

1. No GitHub, crie um repositório novo, por exemplo `mophun-apk-builder`.
2. Adicione os arquivos deste ZIP à raiz do repositório, preservando exatamente a pasta `.github/workflows/`.
   - O arquivo de workflow precisa ficar em `.github/workflows/build-mophun-emulator.yml`.
   - Inclua também este `README.md`.
3. Faça commit dos arquivos na branch `main`.
4. Abra a aba **Actions** do seu repositório.
5. Selecione **Build AbyssME Android APK (Mophun)**.
6. Toque em **Run workflow** e confirme.
7. Aguarde a execução terminar com um sinal verde.
8. Abra a execução concluída e, na seção **Artifacts**, baixe `AbyssME-Mophun-Android-APK`.
9. Extraia o ZIP do artefato e instale o APK no Android.

## Como abrir o jogo `.mpn`

1. Copie o arquivo `.mpn` para o celular.
2. Abra AbyssME.
3. Escolha **Add game** e selecione diretamente o arquivo `.mpn`.
4. Inicie o jogo.

Não renomeie `.mpn` para `.jar`: são formatos de plataformas diferentes.

## Observações

- Este workflow compila `:app:assembleFdroidDebug`, a variante de desenvolvimento documentada pelo projeto.
- O APK de debug é assinado com a chave de depuração padrão e serve para testes pessoais.
- O workflow baixa o código `main` mais recente do projeto upstream em cada execução.
- Se a compilação falhar, abra o job e copie o primeiro erro real da etapa vermelha. Não envie tokens ou segredos.
- O projeto upstream informa que GitHub Actions não faz parte do fluxo oficial de lançamento; este workflow é uma automação independente para seu teste.
- Consulte o README, CONTRIBUTING e licença do projeto oficial antes de redistribuir alterações.

Fonte oficial: https://github.com/EriArk/JavaEmulator
