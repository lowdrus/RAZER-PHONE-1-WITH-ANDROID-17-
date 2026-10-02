# RAZER PHONE 1 WITH ANDROID 17

Projeto para transformar o Razer Phone 1 (`cheryl`) em uma plataforma multiboot moderna com Android gaming, Linux/AI e, futuramente, Windows, preservando uma experiência Razer coerente em toda a plataforma.

## STATUS ATUAL DO PROJETO
- **Rodada atual:** 18 — Preservation Matrix Discovery concluída e analisada
- **Fase:** 0 — auditoria, preservação e recuperação
- **Master Backup atual conhecido:** 39 payloads / 218.344.844 bytes / 208,23 MiB, antes da extração seletiva adicional
- **Overlays:** 13/13 recuperados e validados
- **Deep Audit #02:** 15 relatórios analisados
- **Preservation Matrix #18:** 8 relatórios; ZIP 6.352 bytes; SHA-256 `E6DAC5A8CEC18A9F2BF2A463DD2BB9C93C4FD572463A9294B35DBDC6CD3ACDA2`
- **Novos candidatos confirmados:** Dolby DAX/DSP, Razer Power, Razer Camera Bokeh/Fusion blobs, certificados Theme Store, RazerPlayAutoInstall e autoinstall config Razer
- **Chroma RGB:** ainda não confirmado como recurso nativo do Razer Phone 1
- **Segurança:** nenhum flash, wipe, erase, root ou reboot executado
- **Próximo checkpoint:** Rodada 19 — extração seletiva e validação dos componentes adicionais

## Arquitetura final desejada
1. **Android 17 / Gaming** — armazenamento interno, preservando/recriando a experiência oficial do Razer Phone 1.
2. **Linux-AI OS Star/Allstar ARM64** — microSD, com experiência Razer completa desde o boot até o desktop.
3. **Windows 11 ARM** — depois do Linux-AI, com objetivo de SSD externo e identidade baseada no **Razer Blade 18 (2026)**, incluindo boot/visual/software Razer quando tecnicamente e licenciadamente possível.
4. **DeX Case** — somente após sistemas e multiboot concluídos e validados.

> Boot por microSD/SSD e multiboot são objetivos de engenharia, não capacidades declaradas como prontas antes de teste no hardware.

## Identidade Razer confirmada no firmware original
Foram confirmados Nova Launcher/Razer, Game Booster, Theme Store, Razer Services, Camera, Wallpapers, Setup Wizard, fontes RazerF5, boot animation, overlays Razer/Nova, Razer Power HAL, charge-limit, blobs específicos Razer de câmera e componentes Dolby DAX/DSP. O projeto preservará os elementos necessários localmente e documentará de forma reproduzível o processo.

## Windows 11 ARM — requisito separado
O Windows não deve simplesmente copiar a aparência do Razer Phone. Sua referência oficial é o **Razer Blade 18 (2026)**. Na fase Windows serão pesquisados os ativos/software oficiais apropriados, distinguindo recursos visuais, software compatível com ARM e funções dependentes de hardware/EC específico do notebook. A meta é uma experiência coerente de inicialização e desktop Razer Blade 18, sem declarar como nativas funções de hardware inexistentes no Razer Phone.

## Rodada 18 — principais descobertas
- HAL ativo `vendor.razer.power@1.0::IRazerPower/default`.
- bibliotecas `vendor.razer.power@1.0.so` 32/64-bit e init Razer Power/charge-limit.
- cinco blobs Razer específicos para Bokeh/Fusion da câmera.
- Dolby: `DaxUI.apk`, `daxService.apk`, `dolby_dax.jar`, XMLs, init e módulos DSP.
- `RazerPlayAutoInstall.apk` e `android.autoinstalls.config.razer` identificados.
- boot visual no filesystem: `bootanimation.zip`, `libbootanimation.so`, `bootanim.rc`; splash anterior ao Android ainda não foi provado.
- nenhuma evidência explícita de pacote/HAL Chroma na matriz; investigação continua.

## Ordem de execução
Preservação/rollback → Android 17 → Razer Experience Android → gaming/validação → Linux-AI ARM64 no microSD → Razer Experience Linux → multiboot validado → Windows 11 ARM em SSD externo + experiência Razer Blade 18 (2026) → DeX Case.

## Segurança e distribuição
Não executar wipes, erase, novo unlock, root ou flash destrutivo antes da preservação e do plano de rollback. Ativos/binários proprietários oficiais não serão automaticamente redistribuídos; quando necessário serão preservados localmente e o GitHub receberá manifestos, hashes, scripts e documentação compatíveis com a licença aplicável.

## Diário
O histórico cronológico completo fica em [`DIARIO/`](DIARIO/README.md). README e diário devem permanecer sincronizados.