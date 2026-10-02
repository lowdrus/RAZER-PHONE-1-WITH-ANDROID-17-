# RAZER PHONE 1 WITH ANDROID 17

Projeto para transformar o Razer Phone 1 (`cheryl`) em uma plataforma moderna focada em jogos, Android 17, Linux/AI e futura integração em gabinete estilo DeX, preservando a identidade visual oficial da Razer.

## Objetivos

- Android 17 no Razer Phone 1, com base em ROM customizada compatível.
- Foco em desempenho, jogos, baixa carga em segundo plano e boa responsividade.
- Avaliar Evolution X e alternativas modernas antes de escolher a base definitiva.
- Preservar/reintegrar a identidade Razer quando tecnicamente e legalmente possível: Launcher Razer original, pacote de ícones Razer, wallpapers/live wallpapers e boot animation oficial.
- Avaliar Linux-AI OS 1.0 `Star` (https://linux-ai-os.com/download.php) e estudar uma adaptação/integração adequada ao ARM64 do Razer Phone 1.
- Preparar o aparelho para gabinete estilo DeX, com HDMI, teclado, mouse, armazenamento externo e futuras modificações de hardware.

## Hardware / cenário atual

- Dispositivo: Razer Phone 1
- Codinome esperado: `cheryl`
- Tela: trincada
- Touch: não funcional
- Controle local: teclado + mouse quando o hub está conectado
- Hub USB-C: Knup KP-AD117 (2x USB 3.0, SD, microSD, USB-C aparentemente PD/alimentação, HDMI)
- Para ADB, o telefone está conectado diretamente ao PC; nessa configuração não há teclado/mouse no telefone.
- Serial ADB: `181805V00403723`
- Estado ADB: `unauthorized transport_id:1`
- Windows detecta `ADB Interface` em `USB\VID_1532&PID_905F&MI_02...`.
- `adb get-state` e `adb shell` são recusados enquanto a chave RSA não for autorizada.

## Workspace local

Raiz: `F:\PROJETO\PROJETO RAZER PHONE 1`

Estrutura: `ANDROID-17`, `BACKUP`, `DEX-CASE`, `DUMPS`, `LINUX-AI`, `LOGS`, `RAZER-ORIGINAL`, `ROMS`, `TOOLS` e a pasta preexistente `desbloqueio razer phone 1`.

Evitar armazenar ROMs, backups, imagens ou árvores de build grandes em `C:`.

## Ferramentas locais auditadas

A pasta `desbloqueio razer phone 1\platform-tools` contém um conjunto Android Platform Tools com:

- `adb.exe`
- `fastboot.exe`
- DLLs ADB para Windows
- utilitários `etc1tool`, `hprof-conv`, `make_f2fs`, `mke2fs`, `sqlite3`
- driver Google/Android WinUSB em `usb_driver`, com arquivos amd64/i386

Não foram encontrados no inventário fornecido arquivos de ROM, recovery, boot image, APK, ISO, ZIP/RAR/7z, scripts BAT/PowerShell ou outros payloads de flash. Portanto, essa pasta é tratada por enquanto apenas como ferramentas ADB/Fastboot + driver, não como pacote de desbloqueio/ROM.

Antes de usar os binários para operações de escrita, registrar versões e hashes.

## Linux-AI OS

Fonte oficial indicada: `https://linux-ai-os.com/download.php`.

Linux-AI OS 1.0 `Star`, Cinnamon AI Edition. A imagem oficial indicada é AMD64/x86-64; o projeto investigará portar/recriar a experiência para ARM64 ou executar componentes compatíveis por outra camada, sem tratar a ISO AMD64 como flashável diretamente no Snapdragon 835.

## Estado do projeto

### Fase 0 — Auditoria e recuperação

- [x] Repositório inicializado/documentado
- [x] ADB detecta o aparelho
- [x] Driver/interface ADB detectado corretamente pelo Windows
- [x] Confirmado bloqueio RSA: `unauthorized`
- [x] Identificada limitação: ADB direto remove temporariamente teclado/mouse do aparelho
- [x] Auditada pasta local `desbloqueio razer phone 1`
- [x] Confirmado que a pasta contém Platform Tools + driver, sem imagens/payloads de flash no inventário atual
- [ ] Registrar versão e hashes das Platform Tools
- [ ] Resolver autorização RSA sem touch
- [ ] Coletar propriedades do sistema
- [ ] Confirmar codinome, Android, build, slot A/B e bootloader
- [ ] Preservar dados e preparar estratégia de backup

### Fase 1 — Android 17 / Gaming

- [ ] Verificar disponibilidade real de Android 17 para `cheryl`
- [ ] Avaliar Evolution X 17
- [ ] Avaliar LineageOS/AOSP e device trees disponíveis
- [ ] Escolher base pelo equilíbrio entre estabilidade, GPU, áudio, Wi-Fi, Bluetooth, câmera, HDMI/DisplayPort, 120 Hz e jogos

### Fase 2 — Razer Experience Layer

- [ ] Extrair/preservar ativos originais antes de apagar dados
- [ ] Catalogar launcher, ícones, wallpapers, live wallpapers, sons e boot animation
- [ ] Reintegrar componentes compatíveis com Android 17

### Fase 3 — Gaming optimization

- [ ] Perfil seguro para Snapdragon 835 / Adreno 540
- [ ] Redução de serviços desnecessários
- [ ] Ajustes térmicos seguros
- [ ] 120 Hz
- [ ] Gamepad/teclado/mouse
- [ ] HDMI e modo desktop

### Fase 4 — Linux / AI

- [x] Identificada a distribuição desejada: Linux-AI OS 1.0 `Star`
- [x] Identificada imagem oficial AMD64
- [ ] Investigar portabilidade ARM64
- [ ] Projetar alternativa ARM64/container/chroot/emulação
- [ ] IA local compatível com Snapdragon 835

### Fase 5 — Razer DeX Case

- [ ] Projeto mecânico/eletrônico
- [ ] HDMI + hub USB-C
- [ ] armazenamento removível
- [ ] resfriamento
- [ ] alimentação
- [ ] botão externo de ligar/desligar
- [ ] futuras expansões

## Regra de segurança

Não executar desbloqueio de bootloader, `fastboot flashing unlock`, wipes, formatação ou flash destrutivo antes de confirmar o estado atual, preservar o máximo possível dos dados/ativos Razer e documentar a recuperação.

## Diário

### 2026-10-02 — Rodada 4

Concluída a auditoria da pasta local preexistente. Ela contém Android Platform Tools (`adb.exe`, `fastboot.exe` e utilitários associados) e pacote de driver WinUSB/Android para Windows. O inventário não mostrou ROMs, recoveries, imagens `.img`, APKs, ISOs, arquivos compactados ou scripts de flash. Próximos passos: registrar versão/hashes dessas ferramentas e resolver a autorização RSA sem touch antes de qualquer operação destrutiva.
