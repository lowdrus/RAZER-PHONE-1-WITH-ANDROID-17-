# RAZER PHONE 1 WITH ANDROID 17

Projeto para transformar o Razer Phone 1 (`cheryl`) em uma plataforma multiboot moderna com Android gaming, Linux/AI e, futuramente, Windows, preservando uma experiência Razer coerente em toda a plataforma.

## STATUS ATUAL DO PROJETO
- **Rodada atual:** **22B — Master Backup Cryptographic Seal concluída**
- **Fase:** 0 — preservação concluída; preparação de rollback
- **Master Backup:** **80 payloads / 286.393.459 bytes / 273,13 MiB**
- **Verificação final:** **80 OK / 0 FAIL / 0 MISSING**
- **SHA-256 únicos:** **76**
- **Duplicidades:** **4 grupos / 8 entradas**, classificadas como cópias legítimas de preservação
- **Master Seal SHA-256:** `AFE29A48AE295634E863400F823FACEF96E0BD07F876EE311D315A7E5CABFBB9`
- **Estado do backup:** **MASTER BACKUP VERIFIED / CRYPTOGRAPHICALLY SEALED**
- **Segurança até aqui:** nenhum flash, wipe, erase ou root executado
- **Próximo checkpoint:** **Rodada 23 — Original Firmware Rollback Readiness**

## Arquitetura final desejada
1. **Android 17 / Gaming** — armazenamento interno, preservando/recriando a experiência oficial do Razer Phone 1.
2. **Linux-AI OS Star/Allstar ARM64** — microSD, com experiência Razer completa desde o boot até o desktop.
3. **Windows 11 ARM** — posteriormente, com objetivo de SSD externo e identidade baseada no **Razer Blade 18 (2026)** quando tecnicamente e licenciadamente possível.
4. **DeX Case** — somente após sistemas e multiboot concluídos e validados.

> Boot por microSD/SSD e multiboot são objetivos de engenharia e só serão tratados como capacidades confirmadas após testes reais no hardware.

## Identidade Razer confirmada no firmware original
Foram confirmados Nova Launcher/Razer, Game Booster, Theme Store, Razer Services, Camera, Wallpapers, Setup Wizard, fontes RazerF5, boot animation, overlays Razer/Nova, Razer Power HAL, charge-limit, blobs específicos Razer de câmera, componentes Dolby DAX/DSP, RazerPlayAutoInstall, certificados Theme Store e `android.autoinstalls.config.razer`.

## Master Backup — estado selado
A consolidação encontrou **80 payloads**, totalizando **286.393.459 bytes (273,13 MiB)**. Na Rodada 22A, as oito entradas dos quatro grupos duplicados foram individualmente revalidadas e classificadas como cópias legítimas de preservação.

Na Rodada 22B, os 80 payloads foram novamente comparados ao `MASTER-MANIFEST.csv` por tamanho e SHA-256:

- **TOTAL: 80**
- **OK: 80**
- **FAIL: 0**
- **MISSING: 0**

O `MASTER-BACKUP-SEAL.txt` foi então criado e possui SHA-256:

`AFE29A48AE295634E863400F823FACEF96E0BD07F876EE311D315A7E5CABFBB9`

O diretório `FINAL-CONSOLIDATION\MASTER-BACKUP-SEAL` contém `DUPLICATE-CLASSIFICATION.txt`, `PAYLOAD-VERIFICATION.csv`, `MASTER-BACKUP-SEAL.txt` e `MASTER-BACKUP-SEAL.sha256`.

**O Master Backup está formalmente verificado e selado.** Isso não significa que já seja seguro iniciar o Android 17: primeiro será documentada e validada a rota de rollback do firmware original.

## Windows 11 ARM — requisito separado
O Windows não deve simplesmente copiar a aparência do Razer Phone. Sua referência oficial é o **Razer Blade 18 (2026)**. Na fase Windows serão pesquisados os ativos/software oficiais apropriados, distinguindo recursos visuais, software compatível com ARM e funções dependentes de hardware/EC específico do notebook.

## Ordem de execução
Preservação ✓ → consolidação ✓ → classificação de duplicidades ✓ → selo criptográfico ✓ → **rollback original** → Android 17 → Razer Experience Android → gaming/validação → Linux-AI ARM64 no microSD → Razer Experience Linux → multiboot validado → Windows 11 ARM em SSD externo + experiência Razer Blade 18 (2026) → DeX Case.

## Segurança e distribuição
Não executar wipe, erase, novo unlock, root ou flash destrutivo antes da validação do plano de rollback. Ativos/binários proprietários oficiais não serão automaticamente redistribuídos; quando necessário serão preservados localmente e o GitHub receberá manifestos, hashes, scripts e documentação compatíveis com a licença aplicável.

## Diário
O histórico cronológico completo fica em [`DIARIO/`](DIARIO/README.md). README e diário devem permanecer sincronizados.