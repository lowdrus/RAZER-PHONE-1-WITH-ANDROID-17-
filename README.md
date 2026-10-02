# RAZER PHONE 1 WITH ANDROID 17

Projeto para transformar o Razer Phone 1 (`cheryl`) em uma plataforma moderna focada em jogos, Android 17, Linux/AI e preservação da identidade visual oficial da Razer. O DeX Case permanece no roadmap e só será iniciado depois da conclusão e validação do Razer Phone 1.

## STATUS ATUAL DO PROJETO

- **Rodada atual:** 8 — concluída
- **Próxima rodada:** 9 — preservação da Razer Experience original
- **Fase:** 0 — auditoria, preservação e recuperação
- **Última etapa concluída:** `AUDIT-01`
- **ADB:** autorizado e operacional (`device`)
- **Dispositivo:** Razer Phone 1 / `cheryl`
- **Android original:** 9 / API 28
- **Build:** `P-MR2-RC001-RZR-N.7083`
- **Slot ativo:** `_a`
- **Bootloader:** já desbloqueado (`ro.boot.flash.locked=0`, Verified Boot `orange`)
- **Treble:** ativo
- **Criptografia:** ativa
- **Workspace:** `F:\PROJETO\PROJETO RAZER PHONE 1`
- **Controle local durante ADB:** mouse Knup KP-TE144 e teclado Knup KP-TE127 via Bluetooth
- **DeX Case:** aguardando conclusão do software/validação do telefone

> Regra de sincronização: a rodada mostrada nesta página deve acompanhar o `DIARIO/`. Nenhuma rodada deve ser omitida até a conclusão do projeto.

## Objetivos

- Levar Android 17 ao `cheryl` com uma base tecnicamente adequada.
- Priorizar desempenho, jogos, estabilidade, baixa carga em segundo plano, 120 Hz e recursos do hardware Razer.
- Avaliar Evolution X, LineageOS/AOSP e alternativas antes de escolher a base definitiva.
- Preservar/reintegrar a experiência Razer: launcher/overlays, ícones, wallpapers/live wallpapers, boot animation, sons e componentes compatíveis.
- Estudar integração do Linux-AI OS Star/Allstar com ARM64/Snapdragon 835.
- Somente depois do telefone concluído: desenvolver o DeX Case/gabinete e expansões físicas.

## Hardware e cenário confirmado

- Razer Phone 1, codinome `cheryl`
- Qualcomm MSM8998 / Snapdragon 835, AArch64
- Tela trincada; touch inoperante
- Mouse e teclado Bluetooth permitem controle local enquanto USB-C permanece conectado ao PC
- Hub Knup KP-AD117 disponível para HDMI/USB/SD quando necessário
- Esquema A/B confirmado; slot atual `_a`
- Kernel original `4.4.153-perf+`
- Platform Tools `37.0.1-15733141`

## Workspace local

`F:\PROJETO\PROJETO RAZER PHONE 1`

Pastas principais: `ANDROID-17`, `BACKUP`, `DEX-CASE`, `DUMPS`, `LINUX-AI`, `LOGS`, `RAZER-ORIGINAL`, `ROMS`, `TOOLS`.

## AUDIT-01

A auditoria profunda somente leitura foi concluída e empacotada localmente como `RAZER-PHONE-1-AUDIT-01.zip`. Ela cobre propriedades, armazenamento, memória, CPU, mounts, partições, bateria, display, resolução/densidade, SurfaceFlinger, features, pacotes, componentes Razer, Treble, criptografia, kernel e estado de boot.

Componentes Razer identificados incluem Game Booster, Razer Services, Wallpapers, Theme Store, Camera, Setup Wizard e overlays específicos do `cheryl`. Os dados brutos do aparelho permanecem locais; o GitHub deve receber documentação sanitizada e scripts reproduzíveis, não dados pessoais ou dumps privados.

## Fases

### Fase 0 — Auditoria, preservação e recuperação
- [x] ADB/driver funcionando
- [x] Autorização RSA resolvida
- [x] Platform Tools auditadas
- [x] Dispositivo/build/slot/bootloader identificados
- [x] `AUDIT-01` concluída
- [ ] Preservar Razer Experience original
- [ ] Preparar backup/rollback antes de qualquer flash

### Fase 1 — Android 17 / Gaming
- [ ] Auditar bases Android 17 disponíveis para `cheryl`
- [ ] Avaliar Evolution X
- [ ] Avaliar LineageOS/AOSP/device trees
- [ ] Escolher e construir/testar a base

### Fase 2 — Razer Experience Layer
- [ ] Reintegrar componentes compatíveis
- [ ] Preservar aparência e comportamento Razer

### Fase 3 — Gaming optimization
- [ ] GPU/120 Hz/áudio/USB/Bluetooth/HDMI
- [ ] Perfis de desempenho e térmica seguros
- [ ] Testes de jogos e periféricos

### Fase 4 — Linux / AI
- [ ] Projetar solução ARM64 para a experiência Linux-AI OS
- [ ] Integrar IA local compatível com o Snapdragon 835

### Fase 5 — DeX Case
**Bloqueada até a conclusão das fases anteriores.**

## Segurança

Não executar wipes, erase, novo unlock ou flash destrutivo antes da preservação e do plano de rollback. Não publicar chaves, identificadores desnecessários, dados pessoais ou dumps privados.

## Diário

O histórico completo e cronológico fica em [`DIARIO/`](DIARIO/README.md). A página principal mostra apenas o checkpoint atual; o diário preserva todas as rodadas.