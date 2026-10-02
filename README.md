# RAZER PHONE 1 WITH ANDROID 17

Projeto para transformar o Razer Phone 1 (`cheryl`) em uma plataforma multiboot moderna com Android gaming, Linux/AI e, futuramente, Windows, preservando uma experiência Razer coerente em toda a plataforma.

## STATUS ATUAL DO PROJETO
- **Rodada atual:** **23A — Original Firmware Rollback Readiness / Preflight concluída**
- **Fase:** 0 — preservação concluída; rollback em validação
- **Master Backup:** **80 payloads / 286.393.459 bytes / 273,13 MiB**
- **Master Backup verification:** **80 OK / 0 FAIL / 0 MISSING**
- **Master Seal SHA-256:** `AFE29A48AE295634E863400F823FACEF96E0BD07F876EE311D315A7E5CABFBB9`
- **Dispositivo:** Razer Phone 1 / `cheryl` / Qualcomm MSM8998
- **Firmware atual:** Android 9, `P-MR2-RC001-RZR-N.7083`, API 28, patch 2019-11-05
- **Slot ativo observado:** `_a`
- **Bootloader:** `flash.locked=0`; Verified Boot `orange`
- **Particionamento:** esquema A/B confirmado pelo mapa real de partições
- **Segurança até aqui:** nenhum flash, wipe, erase ou root executado
- **Próximo checkpoint:** **Rodada 23B — Rollback Metadata + Fastboot Read-only Discovery**

## Arquitetura final desejada
1. **Android 17 / Gaming** — armazenamento interno, preservando/recriando a experiência oficial do Razer Phone 1.
2. **Linux-AI OS Star/Allstar ARM64** — microSD, com experiência Razer completa desde o boot até o desktop.
3. **Windows 11 ARM** — posteriormente, com objetivo de SSD externo e identidade baseada no **Razer Blade 18 (2026)** quando tecnicamente e licenciadamente possível.
4. **DeX Case** — somente após sistemas e multiboot concluídos e validados.

> Boot por microSD/SSD e multiboot são objetivos de engenharia e só serão tratados como capacidades confirmadas após testes reais no hardware.

## Identidade Razer confirmada no firmware original
Foram confirmados Nova Launcher/Razer, Game Booster, Theme Store, Razer Services, Camera, Wallpapers, Setup Wizard, fontes RazerF5, boot animation, overlays Razer/Nova, Razer Power HAL, charge-limit, blobs específicos Razer de câmera, componentes Dolby DAX/DSP, RazerPlayAutoInstall, certificados Theme Store e `android.autoinstalls.config.razer`.

## Master Backup — estado selado
O backup contém 80 payloads, totalizando 286.393.459 bytes (273,13 MiB), e foi revalidado por tamanho e SHA-256: **80 OK / 0 FAIL / 0 MISSING**. O selo criptográfico possui SHA-256 `AFE29A48AE295634E863400F823FACEF96E0BD07F876EE311D315A7E5CABFBB9`.

## Rollback — descoberta 23A
O preflight confirmou `cheryl`, plataforma `msm8998`, build original `P-MR2-RC001-RZR-N.7083`, Android 9/API 28 e fingerprint `razer/cheryl/cheryl:9/P-MR2-RC001-RZR-N/7083:user/release-keys`.

O aparelho reporta slot `_a`, `ro.boot.flash.locked=0`, Verified Boot `orange` e verity `enforcing`. O mapa real contém pares A/B para `boot`, `system`, `vendor`, `xbl`, `abl`, `modem`, `dsp`, `tz`, `rpm`, `hyp`, `pmic`, `keymaster` e outros componentes. Também existem partições não-slotadas sensíveis (`persist`, `modemst1/2`, `fsg`, `fsc`, `rf_nv`, `deviceinfo`, `storsec`, `keystore` etc.), que não serão sobrescritas indiscriminadamente.

Foram encontrados `/vendor/etc/fstab.qcom` e `/system/etc/vold.fstab`. A coleta de `/proc/partitions` não gerou o relatório esperado `06-PROC-PARTITIONS.txt`, portanto essa lacuna será fechada na 23B.

**Rollback ainda não está marcado como pronto.** A próxima etapa fará consultas somente leitura no fastboot e completará metadados antes de pesquisarmos/validarmos o pacote exato de firmware original.

## Windows 11 ARM — requisito separado
O Windows não deve simplesmente copiar a aparência do Razer Phone. Sua referência oficial é o **Razer Blade 18 (2026)**. Na fase Windows serão pesquisados os ativos/software oficiais apropriados, distinguindo recursos visuais, software compatível com ARM e funções dependentes de hardware/EC específico do notebook.

## Ordem de execução
Preservação ✓ → consolidação ✓ → classificação de duplicidades ✓ → selo criptográfico ✓ → **rollback original (23A ✓ / 23B próxima)** → Android 17 → Razer Experience Android → gaming/validação → Linux-AI ARM64 no microSD → Razer Experience Linux → multiboot validado → Windows 11 ARM em SSD externo + experiência Razer Blade 18 (2026) → DeX Case.

## Segurança e distribuição
Não executar wipe, erase, novo unlock, root ou flash destrutivo antes da validação do plano de rollback. Ativos/binários proprietários oficiais não serão automaticamente redistribuídos; quando necessário serão preservados localmente e o GitHub receberá manifestos, hashes, scripts e documentação compatíveis com a licença aplicável.

## Diário
O histórico cronológico completo fica em [`DIARIO/`](DIARIO/README.md). README e diário devem permanecer sincronizados.