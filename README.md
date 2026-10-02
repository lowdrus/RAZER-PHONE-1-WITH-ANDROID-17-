# RAZER PHONE 1 WITH ANDROID 17

Projeto para transformar o Razer Phone 1 (`cheryl`) em uma plataforma multiboot moderna com Android gaming, Linux/AI e, futuramente, Windows, preservando uma experiência Razer coerente em toda a plataforma.

## STATUS ATUAL DO PROJETO
- **Rodada atual:** 21 — Master Backup Final Consolidation concluída
- **Fase:** 0 — auditoria, preservação, consolidação e preparação de rollback
- **Master Backup consolidado:** **80 payloads / 286.393.459 bytes / 273,13 MiB**
- **SHA-256 únicos:** **76**
- **Duplicidades:** **4 grupos / 8 entradas** — detectadas, nenhuma removida
- **Extração adicional #19:** 23/23 componentes OK; 67.941.484 bytes; 0 FAIL; 0 ausentes
- **Autoinstall #20:** `android.autoinstalls.config.razer.apk` preservado e validado
- **Overlays:** 13/13 recuperados e validados
- **Deep Audit #02:** 15 relatórios
- **Chroma RGB:** ainda não confirmado como recurso nativo do Razer Phone 1
- **Segurança:** nenhum flash, wipe, erase, root ou reboot executado
- **Próximo checkpoint:** Rodada 22 — Master Backup Seal & Duplicate Classification + preparação do rollback

## Arquitetura final desejada
1. **Android 17 / Gaming** — armazenamento interno, preservando/recriando a experiência oficial do Razer Phone 1.
2. **Linux-AI OS Star/Allstar ARM64** — microSD, com experiência Razer completa desde o boot até o desktop.
3. **Windows 11 ARM** — depois do Linux-AI, com objetivo de SSD externo e identidade baseada no **Razer Blade 18 (2026)**, incluindo boot/visual/software Razer quando tecnicamente e licenciadamente possível.
4. **DeX Case** — somente após sistemas e multiboot concluídos e validados.

> Boot por microSD/SSD e multiboot são objetivos de engenharia, não capacidades declaradas como prontas antes de teste no hardware.

## Identidade Razer confirmada no firmware original
Foram confirmados Nova Launcher/Razer, Game Booster, Theme Store, Razer Services, Camera, Wallpapers, Setup Wizard, fontes RazerF5, boot animation, overlays Razer/Nova, Razer Power HAL, charge-limit, blobs específicos Razer de câmera, componentes Dolby DAX/DSP, RazerPlayAutoInstall, certificados Theme Store e `android.autoinstalls.config.razer`.

## Rodada 21 — consolidação do Master Backup
A auditoria local encontrou **80 payloads**, somando **286.393.459 bytes (273,13 MiB)**. Foram encontrados **76 SHA-256 únicos**, com **4 grupos de duplicidade e 8 entradas**. Nenhuma duplicata foi apagada: a Rodada 22 fará a classificação antes do selo formal.

Foram produzidos `MASTER-MANIFEST.csv`, `SHA256SUMS.txt`, `DUPLICATES-BY-SHA256.csv`, `MASTER-BACKUP-STATS.txt`, `CONSOLIDATION-HASHES.csv` e `README-CONSOLIDATION.txt`. Os diretórios de relatórios/manifestos foram excluídos da contagem de payloads para evitar autorreferência.

**Nenhum payload foi apagado, movido ou modificado.** O backup ainda não é declarado formalmente selado até a Rodada 22 validar/classificar as duplicidades e estabelecer o checkpoint de integridade.

## Windows 11 ARM — requisito separado
O Windows não deve simplesmente copiar a aparência do Razer Phone. Sua referência oficial é o **Razer Blade 18 (2026)**. Na fase Windows serão pesquisados os ativos/software oficiais apropriados, distinguindo recursos visuais, software compatível com ARM e funções dependentes de hardware/EC específico do notebook. A meta é uma experiência coerente de inicialização e desktop Razer Blade 18, sem declarar como nativas funções de hardware inexistentes no Razer Phone.

## Ordem de execução
Preservação → consolidação → selo/rollback → Android 17 → Razer Experience Android → gaming/validação → Linux-AI ARM64 no microSD → Razer Experience Linux → multiboot validado → Windows 11 ARM em SSD externo + experiência Razer Blade 18 (2026) → DeX Case.

## Segurança e distribuição
Não executar wipes, erase, novo unlock, root ou flash destrutivo antes da preservação e do plano de rollback. Ativos/binários proprietários oficiais não serão automaticamente redistribuídos; quando necessário serão preservados localmente e o GitHub receberá manifestos, hashes, scripts e documentação compatíveis com a licença aplicável.

## Diário
O histórico cronológico completo fica em [`DIARIO/`](DIARIO/README.md). README e diário devem permanecer sincronizados.