# RAZER PHONE 1 WITH ANDROID 17

Projeto para transformar o Razer Phone 1 (`cheryl`) em uma plataforma multiboot moderna com Android gaming, Linux/AI e, futuramente, Windows, preservando uma experiência Razer coerente em toda a plataforma.

## STATUS ATUAL DO PROJETO
- **Rodada atual:** **22A — Duplicate Classification concluída**
- **Fase:** 0 — auditoria, preservação, consolidação, selo e preparação de rollback
- **Master Backup consolidado:** **80 payloads / 286.393.459 bytes / 273,13 MiB**
- **SHA-256 únicos:** **76**
- **Duplicidades:** **4 grupos / 8 entradas**, todas revalidadas e classificadas como cópias legítimas de preservação
- **Validação 22A:** **8/8 arquivos existem; 8/8 `VERIFY: OK`; nenhuma divergência**
- **Overlays:** 13/13 recuperados e validados
- **Extração adicional #19:** 23/23 componentes OK
- **Autoinstall #20:** preservado e validado
- **Chroma RGB:** ainda não confirmado como recurso nativo do Razer Phone 1
- **Segurança:** nenhum flash, wipe, erase, root ou reboot executado
- **Próximo checkpoint:** **Rodada 22B — Master Backup Cryptographic Seal**; depois, preparação/validação do rollback

## Arquitetura final desejada
1. **Android 17 / Gaming** — armazenamento interno, preservando/recriando a experiência oficial do Razer Phone 1.
2. **Linux-AI OS Star/Allstar ARM64** — microSD, com experiência Razer completa desde o boot até o desktop.
3. **Windows 11 ARM** — depois do Linux-AI, com objetivo de SSD externo e identidade baseada no **Razer Blade 18 (2026)**, incluindo boot/visual/software Razer quando tecnicamente e licenciadamente possível.
4. **DeX Case** — somente após sistemas e multiboot concluídos e validados.

> Boot por microSD/SSD e multiboot são objetivos de engenharia, não capacidades declaradas como prontas antes de teste no hardware.

## Identidade Razer confirmada no firmware original
Foram confirmados Nova Launcher/Razer, Game Booster, Theme Store, Razer Services, Camera, Wallpapers, Setup Wizard, fontes RazerF5, boot animation, overlays Razer/Nova, Razer Power HAL, charge-limit, blobs específicos Razer de câmera, componentes Dolby DAX/DSP, RazerPlayAutoInstall, certificados Theme Store e `android.autoinstalls.config.razer`.

## Rodada 22A — classificação das duplicidades
As quatro duplicidades da consolidação são quatro arquivos Razer `.rc` preservados em dois locais durante etapas diferentes do backup: `init.razer.chargelimit.rc`, `init.razer.theme.rc`, `vendor.razer.power@1.0-service.rc` e `init.razer.common.rc`.

As oito cópias existem e seus hashes SHA-256 foram recalculados: **8/8 `VERIFY: OK`**. Portanto, são tratadas como **duplicidades legítimas de preservação**, não como corrupção. Nenhuma cópia foi ou será automaticamente removida.

Hashes dos relatórios centrais atualmente registrados:
- `MASTER-MANIFEST.csv`: `E002EC0165097BB21EDAC5597D229618174A22FB297A1F42FA38EF1CC2AFB761`
- `SHA256SUMS.txt`: `67E82495E8D4FB103C643996C5327751F4550FCA7A587B45121ACF68D2CDBC5B`
- `DUPLICATES-BY-SHA256.csv`: `42B12B370C87DEF969DCF64B9A4351D697D4436ED91FED9A2B9ABEF05F25581C`

O próximo passo é criar o selo criptográfico formal do backup e revalidar os 80 payloads contra o manifesto mestre. **Ainda não iniciar flash do Android 17.**

## Windows 11 ARM — requisito separado
O Windows não deve simplesmente copiar a aparência do Razer Phone. Sua referência oficial é o **Razer Blade 18 (2026)**. Na fase Windows serão pesquisados os ativos/software oficiais apropriados, distinguindo recursos visuais, software compatível com ARM e funções dependentes de hardware/EC específico do notebook. A meta é uma experiência coerente de inicialização e desktop Razer Blade 18, sem declarar como nativas funções de hardware inexistentes no Razer Phone.

## Ordem de execução
Preservação → consolidação → classificação de duplicidades → selo criptográfico → rollback → Android 17 → Razer Experience Android → gaming/validação → Linux-AI ARM64 no microSD → Razer Experience Linux → multiboot validado → Windows 11 ARM em SSD externo + experiência Razer Blade 18 (2026) → DeX Case.

## Segurança e distribuição
Não executar wipes, erase, novo unlock, root ou flash destrutivo antes da preservação e do plano de rollback. Ativos/binários proprietários oficiais não serão automaticamente redistribuídos; quando necessário serão preservados localmente e o GitHub receberá manifestos, hashes, scripts e documentação compatíveis com a licença aplicável.

## Diário
O histórico cronológico completo fica em [`DIARIO/`](DIARIO/README.md). README e diário devem permanecer sincronizados.