# Session Progress — 2026-09-16

## Project
CumulusCI study project — re-enfocado: entender el package development model y los patrones de orquestación de CCI (transferibles), más DevOps Center nativo + sf CLI + DX MCP (org development model, lo que un TA enterprise ve en campo).

## Architectural Context
- Repo forked de SFDO-Tooling/CumulusCI, clon local en Developer/. **Clon atrasado (abril 2026); upstream en v4.10.1 (sep 2026)** — hacer `git fetch upstream` antes de trabajar sobre el código.
- Python 3.11–3.13, `pyproject.toml` + `uv.lock`. CLI: `cci`.
- `cumulusci.yml` = cerebro; 210 tasks nativos; flows composables.
- ClickUp: List 901713972680 (flujo SIGNAL), Doc 8cqty5g-9277. Fases 1–6; Phase 6 nueva.
- OKF TA relacionado: `SkillsandOKFs/SalesforceOKFProject/output/salesforce-ta-okf/lifecycle-deployment/scm-ci-cd-release-automation-strategy.md` — sección "Tool landscape (validated 2026-09-16)" agregada. Repo OKF pendiente de commit/push.
- ADR-001 (Doc ClickUp, Architecture & Decisions): CCI = nicho, no metodología dominante.

## Key Findings This Session
- CCI mantenido por Salesforce (v4.10.1, 2026-09-07; push a main 2026-09-16; API v67; commits `@W-…`). No archivado.
- Centro de gravedad 2026: DevOps Center nativo (managed package sin nuevas instalaciones desde abril 2026), DX Inspector, DevOps Testing, DX MCP server.
- OKF TA no menciona CCI ni DevOps Center nativo → hueco tool-level cerrado parcialmente con la sección; la tabla de equivalencias (Phase 6) cierra el resto.

## Files Created/Modified This Session
- docs/why.md — reescrito con re-enfoque y fuera de alcance
- docs/lessons-learned.md — sesión 2 agregada
- session-progress.md — este archivo
- (OKF) salesforce-ta-okf/lifecycle-deployment/scm-ci-cd-release-automation-strategy.md — sección Tool landscape + tags
