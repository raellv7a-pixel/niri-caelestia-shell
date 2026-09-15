# Project State

Last updated: 2026-09-15
Current branch: bootstrap/project-foundation
Last validated commit: 41c53a27

## Current Milestone
P1 — Interaction & Focus Foundation

## Current Objective
Realizar auditoria técnica de focus/click-away e fechamento de drawers e popouts no Niri.

## Known-Good State
O ambiente de desenvolvimento está separado da instalação ativa (`~/.config`). O fork está configurado.

## Working
N/A (Nenhuma mudança de código introduzida ainda).

## Known Issues
- O fork da Ayush possui a implementação Niri drawer focus grab inacabada.
- Alguns painéis exigem a tecla Escape em vez de fecharem quando o foco é perdido (click-away não funciona).
- O projeto usa o Control Center legado, que antecede o Nexus v2 moderno.
- A arquitetura ainda não possui a camada `NiriBridge / CompositorBridge`.

## Decisions in Force
- D001 — O fork da Ayush é a base da integração Niri.
- D002 — O Caelestia atual (`caelestia-dots/shell`) é a referência principal de upstream/UX.
- D003 — Alterações upstream devem ser portadas seletivamente, sem merges diretos cegos.

## Current Risks
- Divergência arquitetural excessiva se features forem portadas antes da base funcional (interaction/focus) estar estável.

## Next Task
Executar a investigação técnica das primitivas de focus no Niri e comportamento do HyprlandFocusGrab no Caelestia.

## Validation Status
P0 concluído e validado (remotes, governança e documentação canônica ativos). Auditoria técnica P1 em andamento.
