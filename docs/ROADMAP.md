# Project Roadmap

Este documento define a direção futura, milestones e as decisões arquiteturais vigentes do projeto.

## Milestones

### P0 — Project Foundation (Current)
- Git e remotes configurados corretamente.
- Governança e regras estabelecidas (`AGENTS.md`).
- Documentação canônica criada.
- Ambiente de desenvolvimento separado da instalação ativa.

### P1 — Interaction & Focus Foundation
- Estabelecer o comportamento funcional base após o bootstrap.
- Implementar click-away e focus handling.
- Tratar input regions.
- Garantir fechamento consistente de painéis sem engolir o clique destinado à janela abaixo.

### P2 — Niri/Compositor Abstraction
- Planejar e criar a camada `NiriBridge / CompositorBridge` para isolar a integração do compositor das camadas de UI.

### P3 — Modern Drawer Architecture
- Portar e adaptar a arquitetura moderna de drawer do upstream, ajustando-a para Niri.

### P4 — Nexus v2 Port
- Substituir o legacy Control Center pela implementação do Nexus v2.

### P5 — Services & Configuration Parity
- Atingir paridade de serviços e arquivos de configuração com a base moderna.

### P6 — Modern Panels
- Portar e adaptar os painéis modernos da interface atual do Caelestia.

### P7 — Legacy Cleanup
- Remover módulos obsoletos, arquivos antigos de configuração e resíduos técnicos do port original.

### P8 — Original Features
- Iniciar a adição de recursos próprios inspirados em projetos como MiDnight, Magnus ou ideias originais (SOMENTE após razoável paridade com upstream).

---

## Architecture Decisions in Force

- **D001 — Ayush fork is the Niri base.**
  *Reason:* O fork contém a base funcional de integração do Niri e serviços já estabelecidos, servindo como o ponto de partida ideal para o ecossistema Niri.

- **D002 — Current Caelestia is the UX/upstream reference.**
  *Reason:* A base do `caelestia-dots/shell` possui a arquitetura mais atual, incluindo Nexus v2 e melhor gerenciamento de UI, e será o padrão-ouro de comportamento.

- **D003 — Upstream changes are ported selectively, not merged blindly.**
  *Reason:* As diferenças entre Hyprland (upstream) e Niri exigem validação semântica; merges cegos quebram a integração existente e introduzem bugs difíceis de rastrear.
