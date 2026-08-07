# DECISION-0001: Regras canônicas em um arquivo por área

| Field | Value |
| --- | --- |
| Status | Accepted |
| Date | 2026-08-07 |
| Deciders | PM |

## Context

O inventário de regras (GAP-002) precisa de um padrão de organização antes de haver conteúdo. O PM pediu estrutura sem fatos canônicos fechados; regras podem variar por área e referenciar umas às outras.

## Options considered

1. **Documento único (overview monolítico)** — simples no bootstrap; piora quando áreas divergem e se cruzam.
2. **Um arquivo por área + referências cruzadas** — escala melhor; exige template e auditoria de índice/links.
3. **Só esqueleto de headings sem padrão de arquivo** — barato, mas frágil para agentes e inventário.

## Decision

**Um markdown por área** em `documentation/rules/`, a partir de `_template.md`, com tabela de **Referências a outras regras**. Inventário obrigatório no `documentation/rules/README.md`. O **doc-auditor** (e `audit-alignment`) deve verificar conformidade do template, inventário e grafo de links. Conteúdo de regras só com fato do PM; caso contrário `INFORMAÇÃO AUSENTE`.

## Consequences

- Agentes não criam áreas “de exemplo” com regras inventadas.
- Novas áreas = copiar template + atualizar inventário/Children.
- Decisões futuras podem subdividir ou fundir áreas via supersede + atualização dos arquivos.

## Supersedes

None
