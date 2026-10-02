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
- Hub USB-C: Knup KP-AD117
  - 2x USB 3.0
  - leitor SD
  - leitor microSD
  - USB-C aparentemente apenas para alimentação/PD no cenário testado
  - HDMI
- Para ADB, o telefone está conectado diretamente ao PC por cabo USB-C; nessa configuração não há teclado/mouse conectado ao telefone.
- Serial ADB: `181805V00403723`
- Estado ADB: `unauthorized transport_id:1`
- Windows detecta `ADB Interface` em `USB\VID_1532&PID_905F&MI_02...`; VID `1532` corresponde à interface apresentada pelo hardware Razer.
- `adb get-state` e `adb shell` são recusados enquanto a chave RSA não for autorizada.

## Workspace local

Por falta de espaço em `C:`, arquivos, ferramentas, backups, dumps e builds deste projeto devem usar como raiz:

`F:\PROJETO\PROJETO RAZER PHONE 1`

Estrutura criada:

- `ANDROID-17`
- `BACKUP`
- `DEX-CASE`
- `DUMPS`
- `LINUX-AI`
- `LOGS`
- `RAZER-ORIGINAL`
- `ROMS`
- `TOOLS`

Também já existia a pasta `desbloqueio razer phone 1`; seu conteúdo deve ser auditado antes de ser usado.

Evitar armazenar imagens Android, ROMs, backups ou árvores de build grandes em `C:` sempre que houver alternativa configurável.

## Linux-AI OS

Fonte oficial indicada para o projeto: `https://linux-ai-os.com/download.php`.

A distribuição atual é Linux-AI OS 1.0 `Star`, Cinnamon AI Edition, baseada em LMDE 7 / Debian, e o arquivo oficial publicado é `linux-ai-1.0-star-cinnamon-amd64.iso`. Portanto, a ISO publicada é AMD64/x86-64 e não pode ser instalada diretamente como sistema ARM64 nativo no Snapdragon 835. O projeto investigará portar/recriar a experiência Linux-AI para ARM64 ou executar componentes compatíveis por outra camada, sem assumir que a ISO AMD64 possa ser simplesmente flasheada no telefone.

## Estado do projeto

### Fase 0 — Auditoria e recuperação

- [x] Repositório inicializado/documentado
- [x] ADB detecta o aparelho
- [x] Driver/interface ADB detectado corretamente pelo Windows
- [x] Confirmado bloqueio RSA: `unauthorized`
- [x] Identificada limitação operacional: conexão ADB direta remove temporariamente teclado/mouse do aparelho
- [ ] Resolver autorização RSA sem touch
- [ ] Auditar pasta local `desbloqueio razer phone 1`
- [ ] Coletar propriedades do sistema
- [ ] Confirmar codinome, versão Android, build, slot A/B e estado do bootloader
- [ ] Preservar dados e preparar estratégia de backup

### Fase 1 — Pesquisa da base Android 17

- [ ] Verificar disponibilidade real de Android 17 para `cheryl`
- [ ] Avaliar Evolution X 17
- [ ] Avaliar LineageOS/AOSP e device trees disponíveis
- [ ] Escolher base com melhor equilíbrio entre estabilidade, GPU, áudio, Wi-Fi, Bluetooth, câmera, HDMI/DisplayPort e jogos

### Fase 2 — Razer Experience Layer

- [ ] Extrair/preservar ativos originais antes de apagar dados
- [ ] Catalogar launcher, ícones, wallpapers, live wallpapers, sons e boot animation
- [ ] Reintegrar componentes compatíveis com Android 17
- [ ] Criar substitutos fiéis quando algum APK antigo for incompatível

### Fase 3 — Gaming optimization

- [ ] Perfil de desempenho para Snapdragon 835 / Adreno 540
- [ ] Redução de processos e serviços desnecessários
- [ ] Ajustes térmicos seguros
- [ ] Testes 120 Hz
- [ ] Gamepad/teclado/mouse
- [ ] HDMI e modo desktop

### Fase 4 — Linux / AI

- [x] Identificada a distribuição exata: Linux-AI OS 1.0 `Star`, Cinnamon AI Edition
- [x] Confirmado que a ISO oficial atual é `amd64`
- [ ] Investigar código/componentes disponíveis e portabilidade ARM64
- [ ] Projetar alternativa ARM64/container/chroot/emulação quando necessário
- [ ] Integrar IA local compatível com os recursos do Snapdragon 835

### Fase 5 — Razer DeX Case

- [ ] Projeto mecânico/eletrônico para gabinete
- [ ] HDMI + hub USB-C
- [ ] armazenamento removível
- [ ] resfriamento
- [ ] alimentação
- [ ] botão externo de ligar/desligar
- [ ] futuras expansões

## Regra de segurança

Não executar desbloqueio de bootloader, `fastboot flashing unlock`, wipes, formatação ou flash destrutivo antes de confirmar o estado atual, preservar o máximo possível dos dados/ativos Razer e documentar a estratégia de recuperação.

## Diário

### 2026-10-02 — Rodada 3

Workspace `F:\PROJETO\PROJETO RAZER PHONE 1` criado com sucesso. O Windows reconhece `ADB Interface` (`VID_1532`, `PID_905F`, interface `MI_02`). `adb devices -l` retorna `181805V00403723 unauthorized transport_id:1`. `adb get-state` e `adb shell getprop ro.product.model` confirmam que o daemon não permite shell antes da autorização RSA.

Confirmada também a fonte correta do Linux desejado: Linux-AI OS 1.0 `Star`, no site oficial `linux-ai-os.com`. A imagem oficial atual é AMD64, então será necessária uma estratégia específica para ARM64.

Próximo objetivo: recuperar uma forma de entrada para aceitar a janela RSA sem apagar o aparelho e, paralelamente, auditar os arquivos já existentes na pasta local `desbloqueio razer phone 1` antes de usar qualquer ferramenta de desbloqueio.
