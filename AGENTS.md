# Project Constitution

## Project Mission
O objetivo inicial é modernizar o antigo port da Caelestia para Niri.
Utilizamos o fork da Ayush (`AyushKr2003/niri-caelestia-shell`) como base da integração existente e o Caelestia atual (`caelestia-dots/shell`) como referência principal de arquitetura e UX.
Não estamos tentando fazer merges cegos entre ambos; a abordagem é de ports seletivos.

## Source of Truth
- **Comportamento e UI moderna:** `caelestia-dots/shell` é a referência.
- **Integração Niri existente:** `AyushKr2003/niri-caelestia-shell` é a referência inicial.
- **APIs:**
  - Qt -> documentação oficial Qt / Qt MCP
  - Niri -> documentação upstream / Context7
  - Quickshell -> documentação/repositório upstream
  - Nunca inventar API QML baseada apenas em memória quando puder ser verificada.

## Core Engineering Principles
- Entender antes de modificar.
- Preferir ports seletivos a merges gigantes.
- Não copiar código `Quickshell.Hyprland` cegamente; identificar a SEMÂNTICA da implementação Hyprland antes de criar o equivalente Niri.
- Preservar recursos Niri existentes até que haja uma substituição validada.
- Realizar mudanças pequenas e verificáveis.
- Manter uma preocupação arquitetural por tarefa quando possível.
- Não misturar um refactor enorme com uma nova feature.
- Não corrigir problemas não relacionados sem necessidade.
- Nunca esconder regressões.

## Model/Agent Behaviour
1. Ler `AGENTS.md`.
2. Ler `docs/PROJECT_STATE.md`.
3. Consultar `docs/ROADMAP.md` se a tarefa envolver planejamento ou um milestone.
4. NÃO ler automaticamente todos os logs de history.
5. Pesquisar no history somente quando precisar descobrir uma decisão ou regressão específica.
6. Verificar o Git antes de alterar arquivos.
7. Verificar o `git diff` depois de alterar.
8. Executar as validações aplicáveis.
9. Atualizar a documentação somente depois que o estado real estiver conhecido.

## Documentation Policy
- **`AGENTS.md`:** Somente regras duráveis.
- **`docs/PROJECT_STATE.md`:** Somente o estado atual.
- **`docs/ROADMAP.md`:** Direção futura, milestones e decisões arquiteturais vigentes.
- **`docs/history/...`:** Registro cronológico append-only.
- PROIBIDA a criação espontânea de novos arquivos `.md`.

## Git Policy
- A branch `main` deve permanecer utilizável.
- Desenvolvimento ocorre em branches.
- Realizar commits pequenos e semanticamente coerentes (Conventional Commits: `feat:`, `fix:`, `refactor:`, `docs:`, `chore:` etc.).
- Não fazer `force push` ou reescrever a história compartilhada.
- Não misturar arquivos gerados ou de runtime com source.
- Revisar `git diff` antes de todo commit.
- Cada milestone deve terminar em estado validável.

## Validation Policy
- Mudanças QML devem considerar `qmllint` e `qmlformat` quando compatíveis.
- Mudanças Niri devem considerar `niri validate`.
- Mudanças de build usarão o build real do projeto.
- Registre apenas comandos verificados no ambiente; não invente comandos de teste sem confirmação.

## Safety
- NUNCA modificar automaticamente a configuração live do usuário em `~/.config` como consequência de uma alteração de source.
- Código de desenvolvimento e runtime instalado devem ser estritamente separados.
