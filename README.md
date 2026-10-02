# RAZER PHONE 1 WITH ANDROID 17

Projeto para transformar o Razer Phone 1 (`cheryl`) em uma plataforma multiboot moderna com Android gaming, Linux/AI e, futuramente, Windows, preservando a identidade Razer.

## STATUS ATUAL DO PROJETO
- **Rodada atual:** 10 — inventário Razer analisado e arquitetura multiboot definida
- **Fase:** 0 — auditoria, preservação e recuperação
- **Próximo checkpoint:** extrair/preservar os componentes Razer originais e preparar rollback
- **ADB:** OK (`device`)
- **Android original:** 9 / API 28 / `P-MR2-RC001-RZR-N.7083`
- **Bootloader:** desbloqueado
- **Slot:** `_a`
- **Treble:** ativo
- **Flash/wipe/erase no projeto:** não executados

## Arquitetura final desejada
1. **Android 17 / Gaming** — sistema principal no armazenamento interno.
2. **Linux-AI OS Star/Allstar ARM64** — sistema Linux no cartão microSD; não usar a memória interna como armazenamento principal do Linux.
3. **Windows 11 ARM** — etapa posterior ao Linux-AI, com objetivo de execução em SSD externo; depende de pesquisa/port e validação real do hardware.
4. **DeX Case** — somente após os sistemas e o multiboot estarem concluídos e validados.

> O multiboot e os boots por microSD/SSD são objetivos de engenharia. Não serão descritos como funcionais até serem comprovados no Razer Phone 1 real.

## Linux-AI + Razer Experience
A versão oficial Linux-AI OS 1.0 Star disponível atualmente é amd64/x64 UEFI, enquanto `cheryl` usa AArch64/MSM8998. Portanto será necessário criar/portar uma edição ARM64 compatível, em vez de simplesmente gravar a ISO oficial no microSD.

Objetivo visual no Linux: experiência Razer completa desde o boot, incluindo splash/boot, tema, fontes, wallpapers, ícones, botões/controles e demais elementos compatíveis.

## Razer Experience preservada no Android original
O inventário confirmou Game Booster, Razer Services, Setup Wizard, Theme Store, Camera, Nova Launcher, Nova overlay, Razer Wallpapers, fontes RazerF5, `bootanimation.zip`, sons, biblioteca/serviço de power Razer e overlays Cheryl/Common para Framework, Settings, SystemUI, Bluetooth, Telephony e Telecom.

## Ordem de execução
Preservação/rollback → Android 17 → Razer Experience Android → gaming/validação → Linux-AI ARM64 no microSD → Razer Experience Linux → multiboot validado → Windows 11 ARM em SSD externo (pesquisa/port) → DeX Case.

## Segurança
Não executar wipes, erase, novo unlock ou flash destrutivo antes da preservação e do plano de rollback. Dados brutos e blobs proprietários permanecem locais; o GitHub recebe scripts e documentação reproduzíveis.

## Diário
O histórico cronológico completo fica em [`DIARIO/`](DIARIO/README.md). README e diário devem permanecer sincronizados.