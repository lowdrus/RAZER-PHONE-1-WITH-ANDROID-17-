# RAZER PHONE 1 WITH ANDROID 17

Projeto para transformar o Razer Phone 1 (`cheryl`) em uma plataforma moderna focada em jogos, Android 17, Linux/AI e preservação da identidade visual oficial da Razer. O DeX Case permanece no roadmap e só será iniciado depois da conclusão e validação do Razer Phone 1.

## STATUS ATUAL DO PROJETO

- **Rodada atual:** 9 — inventário da Razer Experience concluído; preservação em andamento
- **Próximo checkpoint:** analisar os 5 inventários e gerar manifesto preciso de extração
- **Fase:** 0 — auditoria, preservação e recuperação
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

> Regra de sincronização: a rodada mostrada nesta página acompanha o `DIARIO/`. Nenhuma rodada deve ser omitida até a conclusão do projeto.

## Objetivos
- Android 17 no `cheryl` com base tecnicamente adequada.
- Desempenho gaming, estabilidade, baixa carga em segundo plano, 120 Hz e recursos Razer.
- Avaliar Evolution X, LineageOS/AOSP e alternativas antes da escolha definitiva.
- Preservar/reintegrar launcher/overlays, ícones, wallpapers/live wallpapers, boot animation, sons e componentes Razer compatíveis.
- Estudar Linux-AI OS Star/Allstar em ARM64/Snapdragon 835.
- Desenvolver DeX Case somente depois do telefone concluído.

## Fase 0 — progresso
- [x] ADB/driver funcionando
- [x] Autorização RSA resolvida
- [x] Platform Tools auditadas
- [x] Dispositivo/build/slot/bootloader identificados
- [x] `AUDIT-01` concluída
- [x] Inventário inicial da Razer Experience concluído
- [ ] Analisar inventários e gerar manifesto de preservação
- [ ] Extrair componentes Razer necessários
- [ ] Preparar backup/rollback antes de qualquer flash

## Inventário Razer Experience — Rodada 9
Gerados localmente em `RAZER-ORIGINAL\INVENTORY`:

- `01-razer-nova-packages.txt` — 1.981 B
- `02-razer-files.txt` — 2.630 B
- `03-visual-audio-assets.txt` — 7.354 B
- `04-system-apks.txt` — 8.307 B
- `05-overlay-state.txt` — 1.468 B

Os dados brutos permanecem locais. O repositório recebe documentação sanitizada e scripts reproduzíveis, não dumps privados nem blobs proprietários redistribuídos indevidamente.

## Próximas fases
1. Android 17 / Gaming
2. Razer Experience Layer
3. Gaming optimization
4. Linux / AI
5. DeX Case — bloqueado até a conclusão das fases anteriores

## Segurança
Não executar wipes, erase, novo unlock ou flash destrutivo antes da preservação e do plano de rollback.

## Diário
O histórico cronológico completo fica em [`DIARIO/`](DIARIO/README.md).