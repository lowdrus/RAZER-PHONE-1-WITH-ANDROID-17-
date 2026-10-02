# RAZER PHONE 1 WITH ANDROID 17

Projeto para transformar o Razer Phone 1 (`cheryl`) em uma plataforma moderna focada em jogos, Android 17, Linux/AI e futura integração em gabinete estilo DeX, preservando a identidade visual oficial da Razer.

## Objetivos

- Android 17 no Razer Phone 1, com base em ROM customizada compatível.
- Foco em desempenho, jogos, baixa carga em segundo plano e boa responsividade.
- Avaliar Evolution X e alternativas modernas antes de escolher a base definitiva.
- Preservar/reintegrar a identidade Razer quando tecnicamente e legalmente possível: Launcher Razer original, pacote de ícones Razer, wallpapers/live wallpapers e boot animation oficial.
- Avaliar Linux-AI OS e formas realistas de integração/execução no hardware ARM64.
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
- Para ADB, o telefone está atualmente conectado diretamente ao PC por cabo USB-C; nessa configuração não há teclado/mouse conectado ao telefone.
- ADB atual: `181805V00403723 unauthorized`
- Reiniciar o servidor ADB não alterou o estado; falta aceitar a chave RSA no aparelho.

## Workspace local

Por falta de espaço em `C:`, arquivos, ferramentas, backups, dumps e builds deste projeto devem usar como raiz:

`F:\PROJETO\PROJETO RAZER PHONE 1`

Evitar armazenar imagens Android, ROMs, backups ou árvores de build grandes em `C:` sempre que houver alternativa configurável.

## Estado do projeto

### Fase 0 — Auditoria e recuperação

- [x] Repositório inicializado/documentado
- [x] ADB detecta o aparelho
- [x] Identificada limitação operacional: conexão ADB direta remove temporariamente teclado/mouse do aparelho
- [ ] Resolver autorização RSA sem touch
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

- [ ] Avaliar Linux-AI OS
- [ ] Verificar arquiteturas disponibilizadas pelo projeto
- [ ] Projetar alternativa ARM64/container/chroot/VM quando necessário
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

### 2026-10-02 — Rodada 2

Confirmado que o Knup KP-AD117 não está sendo usado durante ADB. Para o PC detectar o aparelho, o cabo USB-C está ligado diretamente entre Razer Phone 1 e PC. Nessa configuração teclado e mouse não ficam disponíveis no telefone. Após `adb kill-server`, `adb start-server` e `adb devices`, o estado continua `181805V00403723 unauthorized`.

Definido workspace local principal: `F:\PROJETO\PROJETO RAZER PHONE 1`.

Próximo objetivo: resolver a autorização RSA sem depender do touch, preferencialmente sem wipe ou flash destrutivo.
