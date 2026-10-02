# RAZER PHONE 1 WITH ANDROID 17

Projeto para transformar o Razer Phone 1 (`cheryl`) em uma plataforma multiboot moderna com Android gaming, Linux/AI e, futuramente, Windows, preservando a identidade Razer desde o boot até cada ambiente.

## STATUS ATUAL DO PROJETO
- **Rodada atual:** 12 — Razer Master Backup primeira passagem concluída
- **Fase:** 0 — auditoria, preservação e recuperação
- **Backup preservado:** 26 arquivos / 218.102.260 bytes / 208 MiB
- **Pendência:** 13 overlays de `/vendor/overlay` retornaram `Permission denied` e ainda precisam ser preservados
- **Manifestos:** `FILES.csv` e `SHA256.csv` gerados
- **Próximo checkpoint:** diagnóstico somente leitura das permissões dos overlays e conclusão do Master Backup
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
A identidade visual padrão Razer deverá existir desde o primeiro estágio visual tecnicamente controlável da inicialização e continuar no futuro seletor/boot manager e em cada sistema: Android 17, Linux-AI e, futuramente, Windows 11 ARM.

## Razer Master Backup — Rodada 12
Preservados com sucesso nesta passagem:
- 7 APKs principais Razer/Nova;
- `bootanimation.zip` original;
- 10 fontes RazerF5;
- 8 arquivos XML/RC de configuração;
- hashes SHA-256 e inventário local.

Os 13 overlays Razer/Nova foram encontrados, mas o `adb pull` direto de `/vendor/overlay` foi bloqueado por permissão. Eles continuam pendentes e não serão ignorados.

## Ordem de execução
Preservação/rollback → Android 17 → Razer Experience Android → gaming/validação → Linux-AI ARM64 no microSD → Razer Experience Linux → multiboot validado → Windows 11 ARM em SSD externo (pesquisa/port) → DeX Case.

## Segurança
Não executar wipes, erase, novo unlock ou flash destrutivo antes da preservação e do plano de rollback. Dados brutos e blobs proprietários permanecem locais; o GitHub recebe scripts e documentação reproduzíveis.

## Diário
O histórico cronológico completo fica em [`DIARIO/`](DIARIO/README.md). README e diário devem permanecer sincronizados.