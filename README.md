# RAZER PHONE 1 WITH ANDROID 17

Projeto para transformar o Razer Phone 1 (`cheryl`) em uma plataforma multiboot moderna com Android gaming, Linux/AI e, futuramente, Windows, preservando uma experiência Razer coerente em toda a plataforma.

## STATUS ATUAL DO PROJETO
- **Rodada atual:** 19 — Selective Preservation concluída
- **Fase:** 0 — auditoria, preservação e recuperação
- **Master Backup base:** 39 payloads / 218.344.844 bytes antes da extração adicional
- **Extração adicional #19:** 23/23 componentes OK; 67.941.484 bytes; 0 FAIL; 0 ausentes
- **Validação #19:** tamanho remoto/local e SHA-256 remoto/local coincidentes para todos os 23 itens
- **Overlays:** 13/13 recuperados e validados
- **Deep Audit #02:** 15 relatórios analisados
- **Preservation Matrix #18:** analisada
- **Chroma RGB:** ainda não confirmado como recurso nativo do Razer Phone 1
- **Segurança:** nenhum flash, wipe, erase, root ou reboot executado
- **Próximo checkpoint:** Rodada 20 — localizar/preservar dinamicamente `android.autoinstalls.config.razer`, depois consolidar o Master Backup e rollback

## Arquitetura final desejada
1. **Android 17 / Gaming** — armazenamento interno, preservando/recriando a experiência oficial do Razer Phone 1.
2. **Linux-AI OS Star/Allstar ARM64** — microSD, com experiência Razer completa desde o boot até o desktop.
3. **Windows 11 ARM** — depois do Linux-AI, com objetivo de SSD externo e identidade baseada no **Razer Blade 18 (2026)**, incluindo boot/visual/software Razer quando tecnicamente e licenciadamente possível.
4. **DeX Case** — somente após sistemas e multiboot concluídos e validados.

> Boot por microSD/SSD e multiboot são objetivos de engenharia, não capacidades declaradas como prontas antes de teste no hardware.

## Identidade Razer confirmada no firmware original
Foram confirmados Nova Launcher/Razer, Game Booster, Theme Store, Razer Services, Camera, Wallpapers, Setup Wizard, fontes RazerF5, boot animation, overlays Razer/Nova, Razer Power HAL, charge-limit, blobs específicos Razer de câmera e componentes Dolby DAX/DSP. O projeto preservará os elementos necessários localmente e documentará de forma reproduzível o processo.

## Rodada 19 — preservação adicional
Foram preservados e validados 23 componentes adicionais: `RazerPlayAutoInstall.apk`, dois certificados Theme Store, Razer Power 32/64-bit, quatro arquivos init Razer, cinco blobs Razer Camera Bokeh/Fusion e a pilha selecionada Dolby DAX/DSP (`DaxUI`, `daxService`, JAR, XMLs, init e módulos DSP). O manifesto local é `MASTER-BACKUP\MANIFEST\ADDITIONAL-RAZER-COMPONENTS.csv`.

O resultado foi **23 OK / 0 FAIL / 0 ausentes**, totalizando **67.941.484 bytes** nesta extração. `android.autoinstalls.config.razer` permanece como pendência deliberada porque reside em `/data/app` com caminho de instalação variável; será localizado pelo Package Manager em vez de assumir um diretório aleatório.

## Windows 11 ARM — requisito separado
O Windows não deve simplesmente copiar a aparência do Razer Phone. Sua referência oficial é o **Razer Blade 18 (2026)**. Na fase Windows serão pesquisados os ativos/software oficiais apropriados, distinguindo recursos visuais, software compatível com ARM e funções dependentes de hardware/EC específico do notebook. A meta é uma experiência coerente de inicialização e desktop Razer Blade 18, sem declarar como nativas funções de hardware inexistentes no Razer Phone.

## Ordem de execução
Preservação/rollback → Android 17 → Razer Experience Android → gaming/validação → Linux-AI ARM64 no microSD → Razer Experience Linux → multiboot validado → Windows 11 ARM em SSD externo + experiência Razer Blade 18 (2026) → DeX Case.

## Segurança e distribuição
Não executar wipes, erase, novo unlock, root ou flash destrutivo antes da preservação e do plano de rollback. Ativos/binários proprietários oficiais não serão automaticamente redistribuídos; quando necessário serão preservados localmente e o GitHub receberá manifestos, hashes, scripts e documentação compatíveis com a licença aplicável.

## Diário
O histórico cronológico completo fica em [`DIARIO/`](DIARIO/README.md). README e diário devem permanecer sincronizados.