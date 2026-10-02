# RAZER PHONE 1 WITH ANDROID 17

Projeto para transformar o Razer Phone 1 (`cheryl`) em uma plataforma multiboot moderna com Android gaming, Linux/AI e, futuramente, Windows, preservando a identidade Razer desde o boot até cada ambiente.

## STATUS ATUAL DO PROJETO
- **Rodada atual:** 11 — Preservation Preflight concluído
- **Fase:** 0 — auditoria, preservação e recuperação
- **Próximo checkpoint:** extração local dos ativos Razer + SHA-256 + manifesto verificável
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

## Identidade Razer — requisito permanente
A identidade visual padrão Razer deverá existir em toda a sequência de inicialização e em todos os sistemas compatíveis:

- futuro seletor/boot manager com visual Razer;
- Android 17 com Razer Experience;
- Linux-AI com splash/boot, login, desktop, fontes, wallpapers, ícones, botões/controles e temas Razer;
- Windows 11 ARM, na etapa futura, com camada visual Razer compatível.

Ativos proprietários extraídos permanecem no backup local. O GitHub prioriza scripts, manifestos e instruções reproduzíveis.

## Preservation Preflight — Rodada 11
Confirmados e legíveis no firmware original:

- RazerGameBooster, RazerServices, RazerSetupWizard, RazerThemeStore, RazerCamera, NovaLauncher e RazerWallpapers;
- `bootanimation.zip` original com 88.586.968 bytes;
- 10 fontes RazerF5;
- NovaLauncherOverlay e overlays Razer Cheryl/Common;
- XMLs de features/permissões/whitelist;
- scripts init Razer de charge limit, common, theme e power service.

## Ordem de execução
Preservação/rollback → Android 17 → Razer Experience Android → gaming/validação → Linux-AI ARM64 no microSD → Razer Experience Linux → multiboot validado → Windows 11 ARM em SSD externo (pesquisa/port) → DeX Case.

## Segurança
Não executar wipes, erase, novo unlock ou flash destrutivo antes da preservação e do plano de rollback. Dados brutos e blobs proprietários permanecem locais; o GitHub recebe scripts e documentação reproduzíveis.

## Diário
O histórico cronológico completo fica em [`DIARIO/`](DIARIO/README.md). README e diário devem permanecer sincronizados.