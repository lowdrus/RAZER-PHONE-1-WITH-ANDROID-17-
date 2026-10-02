# RAZER PHONE 1 WITH ANDROID 17

Projeto para transformar o Razer Phone 1 (`cheryl`) em uma plataforma multiboot moderna com Android gaming, Linux/AI e, futuramente, Windows, preservando uma experiência Razer coerente em toda a plataforma.

## STATUS ATUAL DO PROJETO
- **Rodada atual:** 14 — recuperação experimental de overlay validada
- **Fase:** 0 — auditoria, preservação e recuperação
- **Backup base:** 26 arquivos / 218.102.260 bytes / 208 MiB, mais o primeiro overlay recuperado (a contagem final será regenerada após os 13 overlays)
- **Overlay de prova:** `RazerCherylSystemUIRes.apk`, 8542 bytes remoto/local
- **SHA-256 local da prova:** `C357657F09CC9903A55B46688FBA012D875D991E66A296BEB50F055FEB1D5B51`
- **Método comprovado:** `adb exec-out cat` consegue recuperar o overlay sem root ou alteração de SELinux
- **Pendência:** recuperar/validar os demais overlays e regenerar manifestos
- **ADB:** OK (`device`), shell uid 2000
- **SELinux:** Enforcing
- **Build:** produção (`ro.debuggable=0`, `ro.secure=1`, `ro.adb.secure=1`)
- **Flash/wipe/erase/root no projeto:** não executados

## Arquitetura final desejada
1. **Android 17 / Gaming** — armazenamento interno, com Razer Experience.
2. **Linux-AI OS Star/Allstar ARM64** — microSD, com experiência Razer completa desde o boot até o desktop.
3. **Windows 11 ARM** — depois do Linux-AI, com objetivo de SSD externo e experiência visual baseada no Razer Blade 18 (2026); depende de pesquisa/port e validação real.
4. **DeX Case** — somente após sistemas e multiboot concluídos e validados.

> Boot por microSD/SSD e multiboot são objetivos de engenharia, não capacidades declaradas como prontas antes de teste no hardware.

## Identidade Razer
- **Android 17:** preservar/recriar a identidade oficial do Razer Phone 1 compatível com o novo Android.
- **Linux-AI:** Razer desde os estágios de boot controláveis, splash/login, desktop, fontes, wallpapers, ícones, botões, controles e temas.
- **Windows 11 ARM:** referência visual/nativa oficial desejada do **Razer Blade 18 (2026)**, incluindo inicialização e experiência Windows/Razer na medida tecnicamente e licenciadamente possível.
- **Boot manager:** experiência Razer coerente na seleção dos sistemas.

Ativos proprietários oficiais devem ser obtidos legitimamente e mantidos localmente quando a redistribuição não for permitida; o repositório prioriza scripts, manifestos e documentação reproduzível.

## Descoberta da Rodada 14
O `adb pull` direto de `/vendor/overlay` é bloqueado, porém `adb exec-out cat` recuperou `RazerCherylSystemUIRes.apk` com exatamente **8542 bytes**, igual ao tamanho remoto. Os primeiros bytes locais foram `50 4B 03 04`, assinatura ZIP/APK esperada. A cópia local recebeu SHA-256 `C357657F09CC9903A55B46688FBA012D875D991E66A296BEB50F055FEB1D5B51`. O próximo checkpoint é automatizar o mesmo método para os 13 overlays, comparar tamanho remoto/local, tentar SHA-256 remoto quando disponível e regenerar os manifestos.

## Ordem de execução
Preservação/rollback → Android 17 → Razer Experience Android → gaming/validação → Linux-AI ARM64 no microSD → Razer Experience Linux → multiboot validado → Windows 11 ARM em SSD externo + experiência Razer Blade 18 (2026) → DeX Case.

## Segurança
Não executar wipes, erase, novo unlock, root ou flash destrutivo antes da preservação e do plano de rollback.

## Diário
O histórico cronológico completo fica em [`DIARIO/`](DIARIO/README.md). README e diário devem permanecer sincronizados.