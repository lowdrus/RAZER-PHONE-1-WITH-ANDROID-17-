# RAZER PHONE 1 WITH ANDROID 17

Projeto para transformar o Razer Phone 1 (`cheryl`) em uma plataforma multiboot moderna com Android gaming, Linux/AI e, futuramente, Windows, preservando uma experiência Razer coerente em toda a plataforma.

## STATUS ATUAL DO PROJETO
- **Rodada atual:** 13 — diagnóstico de acesso aos overlays concluído
- **Fase:** 0 — auditoria, preservação e recuperação
- **Backup preservado:** 26 arquivos / 218.102.260 bytes / 208 MiB
- **Pendência:** 13 overlays de `/vendor/overlay`; `adb pull` é negado, mas leitura pelo shell foi comprovada
- **Manifestos:** `FILES.csv` e `SHA256.csv` gerados
- **Próximo checkpoint:** extração binária experimental de 1 overlay via shell/exec-out + validação de integridade
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

## Descoberta da Rodada 13
`/vendor/overlay` e os APKs possuem permissões Unix aparentemente legíveis, mas SELinux está Enforcing e `adb pull` é negado. O shell ADB conseguiu ler os primeiros bytes de `RazerCherylSystemUIRes.apk`, revelando `PK`, assinatura esperada de ZIP/APK. A próxima tentativa será streaming binário somente leitura pelo shell, seguido de comparação de tamanho/hash antes de copiar os demais overlays.

## Ordem de execução
Preservação/rollback → Android 17 → Razer Experience Android → gaming/validação → Linux-AI ARM64 no microSD → Razer Experience Linux → multiboot validado → Windows 11 ARM em SSD externo + experiência Razer Blade 18 (2026) → DeX Case.

## Segurança
Não executar wipes, erase, novo unlock, root ou flash destrutivo antes da preservação e do plano de rollback.

## Diário
O histórico cronológico completo fica em [`DIARIO/`](DIARIO/README.md). README e diário devem permanecer sincronizados.