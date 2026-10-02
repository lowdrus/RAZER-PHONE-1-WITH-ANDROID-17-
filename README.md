# RAZER PHONE 1 WITH ANDROID 17

Projeto para transformar o Razer Phone 1 (`cheryl`) em uma plataforma moderna focada em jogos, Android 17, Linux/AI e futura integração em gabinete estilo DeX, preservando a identidade visual oficial da Razer.

## Objetivos

- Android 17 no Razer Phone 1, com base em ROM customizada compatível.
- Foco em desempenho, jogos, baixa carga em segundo plano e boa responsividade.
- Avaliar Evolution X e alternativas modernas antes de escolher a base definitiva.
- Preservar/reintegrar a identidade Razer quando tecnicamente e legalmente possível:
  - Launcher Razer original
  - pacote de ícones Razer
  - wallpapers e live wallpapers oficiais
  - boot animation oficial
- Avaliar Linux-AI OS 1.0 "Star" e formas realistas de integração/execução no hardware ARM64 do aparelho.
- Preparar o aparelho para uso em gabinete estilo DeX, com HDMI, teclado, mouse, armazenamento externo e futuras modificações de hardware, incluindo botão de energia.

## Hardware / cenário atual

- Dispositivo: Razer Phone 1
- Codinome esperado: `cheryl`
- Tela: trincada
- Touch: não funcional
- Controle atual: teclado + mouse
- Hub USB-C: Knup KP-AD117
  - 2x USB 3.0
  - leitor SD
  - leitor microSD
  - USB-C
  - HDMI
- ADB atual: dispositivo detectado, porém `unauthorized`
- Serial ADB observada: `181805V00403723`

## Estado do projeto

### Fase 0 — Auditoria e recuperação

- [x] Repositório inicializado/documentado
- [x] ADB detecta o aparelho
- [ ] Autorizar a chave RSA do computador no Android
- [ ] Coletar propriedades do sistema
- [ ] Confirmar codinome, versão Android, build, slot A/B e estado do bootloader
- [ ] Preservar dados e preparar estratégia de backup

### Fase 1 — Pesquisa da base Android 17

- [ ] Verificar disponibilidade real de Android 17 para `cheryl`
- [ ] Avaliar Evolution X 17
- [ ] Avaliar LineageOS/AOSP e device trees disponíveis
- [ ] Escolher base com melhor equilíbrio entre estabilidade, GPU, áudio, Wi-Fi, Bluetooth, câmera, HDMI/DisplayPort e jogos

### Fase 2 — Razer Experience Layer

- [ ] Extrair/preservar ativos originais do sistema Razer antes de apagar dados
- [ ] Catalogar launcher, ícones, wallpapers, live wallpapers, sons e boot animation
- [ ] Reintegrar apenas componentes compatíveis com Android 17
- [ ] Criar substitutos fiéis quando algum APK antigo for incompatível

### Fase 3 — Gaming optimization

- [ ] Perfil de desempenho para Snapdragon 835 / Adreno 540
- [ ] Redução de processos e serviços desnecessários
- [ ] Ajustes térmicos seguros
- [ ] Testes 120 Hz
- [ ] Gamepad/teclado/mouse
- [ ] HDMI e modo desktop

### Fase 4 — Linux / AI

- [ ] Avaliar Linux-AI OS 1.0 "Star"
- [ ] Verificar arquitetura disponibilizada pelo projeto
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

Não executar desbloqueio de bootloader, `fastboot flashing unlock`, wipes, formatação ou flash destrutivo antes de:

1. confirmar o estado atual do aparelho;
2. salvar o máximo possível dos dados e ativos Razer originais;
3. documentar a estratégia de recuperação.

## Diário

### 2026-10-02

Primeira auditoria: `adb devices` retornou o aparelho como `unauthorized`. Próximo passo: autorizar a chave RSA usando teclado/mouse e coletar diagnóstico somente leitura.
