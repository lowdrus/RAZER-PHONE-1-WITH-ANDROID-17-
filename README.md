# RAZER PHONE 1 WITH ANDROID 17

Projeto para transformar o Razer Phone 1 (`cheryl`) em uma plataforma multiboot moderna com Android gaming, Linux/AI e, futuramente, Windows, preservando uma experiência Razer coerente em toda a plataforma.

## STATUS ATUAL DO PROJETO
- **Rodada atual:** 16 — Razer Experience Deep Audit #02 concluída
- **Fase:** 0 — auditoria, preservação e recuperação
- **Master Backup preservado:** 39 arquivos de payload / 218.344.844 bytes / 208,23 MiB antes da classificação dos novos candidatos
- **Overlays:** 13/13 recuperados e validados, 0 falhas
- **Deep Audit #02:** 15 relatórios gerados com sucesso
- **Escopo auditado:** propriedades, Razer/Cheryl/Nova, visuais, áudio, fontes, bibliotecas, configurações, serviços, pacotes, features e hardware config
- **Segurança:** nenhum flash, wipe, erase, root ou reboot executado
- **Próximo checkpoint:** analisar o conteúdo dos 15 relatórios e classificar ativos adicionais antes de qualquer instalação do Android 17

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

## Rodada 16 — Deep Audit #02
A auditoria somente leitura gerou 15 relatórios em `RAZER-ORIGINAL\MASTER-BACKUP\AUDIT-RAZER-EXPERIENCE-02`. O console confirma a conclusão normal da coleta e a existência dos relatórios. Como o log de execução contém os nomes/tamanhos, mas não o conteúdo interno dos relatórios, a próxima etapa é coletar/analisar esses arquivos para decidir exatamente o que ainda deve ser preservado. Não avançaremos para Android 17 com essa classificação pendente.

## Ordem de execução
Preservação/rollback → Android 17 → Razer Experience Android → gaming/validação → Linux-AI ARM64 no microSD → Razer Experience Linux → multiboot validado → Windows 11 ARM em SSD externo + experiência Razer Blade 18 (2026) → DeX Case.

## Segurança
Não executar wipes, erase, novo unlock, root ou flash destrutivo antes da preservação e do plano de rollback.

## Diário
O histórico cronológico completo fica em [`DIARIO/`](DIARIO/README.md). README e diário devem permanecer sincronizados.