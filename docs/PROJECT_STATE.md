# Project State

Last updated: 2026-09-15
Current branch: p1/interaction-focus-audit
Last validated commit: 766408ba

## Current Milestone
P1 — Interaction & Focus Foundation

## Current Objective
Auditoria técnica concluída; especificação de arquitetura para a abstração `NiriFocusGrab` estabelecida.

## Known-Good State
O ambiente de desenvolvimento está separado da instalação ativa (`~/.config`). O fork está configurado.

## Working
N/A (Nenhuma mudança de código introduzida ainda).

## Known Issues
- Drawers e detached popouts não fecham ao clicar fora por ausência do protocolo `hyprland_focus_grab_v1` no Niri.
- Painéis usam `Escape` como fallback forçado devido ao uso de `WlrKeyboardFocus.Exclusive` ou ausência de monitor de foco.
- O projeto usa o Control Center legado, que antecede o Nexus v2 moderno.
- A arquitetura ainda não possui a camada `NiriBridge / CompositorBridge`.

## Decisions in Force
- D001 — O fork da Ayush é a base da integração Niri.
- D002 — O Caelestia atual (`caelestia-dots/shell`) é a referência principal de upstream/UX.
- D003 — Alterações upstream devem ser portadas seletivamente, sem merges diretos cegos.
- D004 — O modelo de interação Niri deve emular a semântica do `HyprlandFocusGrab` preservando click-through nativo e sem overlays fullscreen.
## Current Risks
- Divergência arquitetural excessiva se features forem portadas antes da base funcional (interaction/focus) estar estável.

## Next Task
Implementar P1.2 — criar o protótipo do componente `NiriFocusGrab` de forma isolada e aplicá-lo aos detached popouts em `modules/bar/popouts/Wrapper.qml`.

## Validation Status
Auditoria técnica de foco e click-away concluída com sucesso. Verificação no Niri 26.04 e Quickshell 0.3.1 confirmada. Base de código intacta.
