# RAZER PHONE 1 WITH ANDROID 17

Projeto para transformar o Razer Phone 1 (`cheryl`) em uma plataforma multiboot moderna com Android gaming, Linux/AI e, futuramente, Windows, preservando uma experiência Razer coerente em toda a plataforma.

## STATUS ATUAL DO PROJETO
- **Rodada atual:** 20 — Autoinstall Razer Preservation concluída
- **Fase:** 0 — auditoria, preservação e recuperação
- **Master Backup base:** 39 payloads / 218.344.844 bytes antes das extrações adicionais
- **Extração adicional #19:** 23/23 componentes OK; 67.941.484 bytes; 0 FAIL; 0 ausentes
- **Autoinstall #20:** `android.autoinstalls.config.razer.apk` preservado; 12.418 bytes; tamanho e SHA-256 remoto/local idênticos
- **SHA-256 Autoinstall:** `584C517168FD93F5BA6B58296A716A9BAE0BC59DBC50530FA613B71862FE88DD`
- **Overlays:** 13/13 recuperados e validados
- **Deep Audit #02:** 15 relatórios analisados
- **Preservation Matrix #18:** componentes Razer/Dolby explicitamente pendentes agora preservados
- **Chroma RGB:** ainda não confirmado como recurso nativo do Razer Phone 1
- **Segurança:** nenhum flash, wipe, erase, root ou reboot executado
- **Próximo checkpoint:** Rodada 21 — consolidação final do Master Backup + manifesto/hash mestre + duplicidades; depois plano de rollback

## Arquitetura final desejada
1. **Android 17 / Gaming** — armazenamento interno, preservando/recriando a experiência oficial do Razer Phone 1.
2. **Linux-AI OS Star/Allstar ARM64** — microSD, com experiência Razer completa desde o boot até o desktop.
3. **Windows 11 ARM** — depois do Linux-AI, com objetivo de SSD externo e identidade baseada no **Razer Blade 18 (2026)**, incluindo boot/visual/software Razer quando tecnicamente e licenciadamente possível.
4. **DeX Case** — somente após sistemas e multiboot concluídos e validados.

> Boot por microSD/SSD e multiboot são objetivos de engenharia, não capacidades declaradas como prontas antes de teste no hardware.

## Identidade Razer confirmada no firmware original
Foram confirmados Nova Launcher/Razer, Game Booster, Theme Store, Razer Services, Camera, Wallpapers, Setup Wizard, fontes RazerF5, boot animation, overlays Razer/Nova, Razer Power HAL, charge-limit, blobs específicos Razer de câmera, componentes Dolby DAX/DSP, RazerPlayAutoInstall, certificados Theme Store e `android.autoinstalls.config.razer`.

## Rodadas 19–20 — fechamento dos componentes adicionais
A Rodada 19 preservou e validou 23 componentes adicionais, totalizando 67.941.484 bytes. A Rodada 20 localizou dinamicamente pelo Package Manager e preservou `android.autoinstalls.config.razer` a partir de `/data/app`, sem assumir o diretório aleatório de instalação.

O APK possui 12.418 bytes e SHA-256 `584C517168FD93F5BA6B58296A716A9BAE0BC59DBC50530FA613B71862FE88DD`, idêntico no aparelho e na cópia local. Manifesto: `MASTER-BACKUP\MANIFEST\AUTOINSTALL-RAZER.csv`.

O backup ainda não é considerado formalmente selado: a próxima etapa consolidará todos os arquivos, hashes e duplicidades em um manifesto mestre antes da criação/validação do procedimento de rollback.

## Windows 11 ARM — requisito separado
O Windows não deve simplesmente copiar a aparência do Razer Phone. Sua referência oficial é o **Razer Blade 18 (2026)**. Na fase Windows serão pesquisados os ativos/software oficiais apropriados, distinguindo recursos visuais, software compatível com ARM e funções dependentes de hardware/EC específico do notebook. A meta é uma experiência coerente de inicialização e desktop Razer Blade 18, sem declarar como nativas funções de hardware inexistentes no Razer Phone.

## Ordem de execução
Preservação/rollback → Android 17 → Razer Experience Android → gaming/validação → Linux-AI ARM64 no microSD → Razer Experience Linux → multiboot validado → Windows 11 ARM em SSD externo + experiência Razer Blade 18 (2026) → DeX Case.

## Segurança e distribuição
Não executar wipes, erase, novo unlock, root ou flash destrutivo antes da preservação e do plano de rollback. Ativos/binários proprietários oficiais não serão automaticamente redistribuídos; quando necessário serão preservados localmente e o GitHub receberá manifestos, hashes, scripts e documentação compatíveis com a licença aplicável.

## Diário
O histórico cronológico completo fica em [`DIARIO/`](DIARIO/README.md). README e diário devem permanecer sincronizados.