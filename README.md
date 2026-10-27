# Voice Studio na placa AMD (Vulkan)

Motor de voz **OmniVoice (GGUF)** compilado com **Vulkan** para o [Voice Studio](https://github.com/debpalash/VoiceStudio) rodar na GPU AMD no Windows, em vez de cair na CPU.

No PC do autor (Radeon RX 6600M 8 GB), gerar 12 s de fala levava ~270 s na CPU e passou para ~41 s. Um áudio de 13 min que levava cerca de 9 h caiu para cerca de 1 h. O tempo varia com a placa, o texto e a qualidade escolhida.

## Baixar
Na aba **Releases** (à direita), baixe:
- `VoiceStudio-Vulkan-AMD.zip` — o motor e as bibliotecas
- `GUIA_INSTALACAO_VoiceStudio_Vulkan_AMD.pdf` — passo a passo de instalação (3 páginas)

## Resumo da instalação
1. Instale o Voice Studio pela [página oficial de versões](https://github.com/debpalash/VoiceStudio/releases/latest), abra uma vez e feche.
2. Extraia o zip e copie os **6 arquivos** (o `.exe`, as 4 `.dll` e o `checksums.sha256`) para as **duas** pastas:
   - `%LOCALAPPDATA%\Programs\VoiceStudio\resources\bin`
   - `%APPDATA%\VoiceStudio\runtime\project\bin`
3. Abra o Voice Studio, procure **OmniVoice (GGUF)** no gerenciador de modelos e ative.

O guia em PDF tem os detalhes, a conferência do arquivo (SHA-256) e a tabela de problemas comuns.

## Instalar com o Claude Code (opcional)
Se você já usa o [Claude Code](https://claude.com/claude-code), ele pode fazer a cópia dos arquivos por você. Cole o texto abaixo nele:

```
Instale o motor Vulkan do Voice Studio pra minha placa AMD (Windows).
Repositório: github.com/wallkrr777/VoiceStudio-Vulkan-AMD (aba Releases, v1.0).

1. Baixe VoiceStudio-Vulkan-AMD.zip e o GUIA_INSTALACAO_VoiceStudio_Vulkan_AMD.pdf do repositório e leia o guia.
2. Confira o SHA-256 do omnivoice-tts-windows-x86_64.exe contra o checksums.sha256 do zip. Se não bater, pare e me avise.
3. Confirme que o Voice Studio já está instalado e foi aberto uma vez. Se não, me diga.
4. Copie os 6 arquivos do zip (exe, 4 dlls e checksums.sha256) pras DUAS pastas:
   %LOCALAPPDATA%\Programs\VoiceStudio\resources\bin
   %APPDATA%\VoiceStudio\runtime\project\bin
   Antes de copiar, feche o Voice Studio e me mostre o que vai fazer.
5. Me diga como ativar o OmniVoice (GGUF) no app, que eu faço esse passo.
```

**Antes de aprovar qualquer comando:**
- Leia o que o Claude Code vai rodar. Ele vai baixar e copiar um `.exe` na sua máquina; não deixe em modo automático sem conferir.
- Peça sempre a conferência do SHA-256 (passo 2). Se o hash não bater com o da seção "Conferir o arquivo" abaixo, não instale.
- O último passo (ativar o **OmniVoice (GGUF)** dentro do app) é pela interface do Voice Studio e você faz sozinho.

Sem o Claude Code, siga o guia em PDF.

## Requisitos
- Windows 10/11 64 bits
- Placa AMD com driver atualizado (Vulkan)
- Microsoft Visual C++ Redistributable 2015–2022 (x64)

## Testado em
Radeon RX 6600M, Windows 10, Voice Studio v0.5.6, omnivoice.cpp commit `48b2d00` (14/10/2026). Em outras placas pode funcionar, mas não foi testado.

## Conferir o arquivo
`omnivoice-tts-windows-x86_64.exe` — SHA-256:
`eb5a92c1180c9d9beeb386071f283c55770e6bf472a344cf367bfa07cafbbf4c`

## Licenças e créditos
- [omnivoice.cpp](https://github.com/ServeurpersoCom/omnivoice.cpp) (ServeurpersoCom) e ggml: **MIT**. Os binários aqui foram compilados a partir desse código; os textos das licenças estão em `licencas/` dentro do zip.
- Voice Studio: **AGPL-3.0**, **não incluído** aqui.
- Modelos: baixados por você pelo app, cada um com a sua licença.
- Compilação independente, sem vínculo com os autores do Voice Studio ou do omnivoice.cpp, sem garantia.
- Clone apenas vozes que você tem direito de usar ou com consentimento.
