# Lessons Learned — CumulusCI

_Updated after each session. Captures what broke, how it was fixed, and what not to forget._

---

### 2026-05-22 — Sesión 1: Overview y Bootstrap

**Qué pasó:**
Primera sesión. Fork + clone del repo, bootstrap del proyecto en ClickUp, overview completo de CumulusCI, plan de 5 fases creado.

**Lecciones:**

1. **CumulusCI no reemplaza SFDX — lo orquesta.** SFDX son los comandos de bajo nivel; CumulusCI los llama por debajo y les da orden y portabilidad.
2. **El cumulusci.yml es el cerebro.** Toda customización vive ahí y se commitea a Git → automatización reproducible en cualquier entorno.
3. **Los Flows son composables.** Un flow puede llamar a otro flow como paso. Permite pipelines complejos desde piezas simples.
4. **El repo de CumulusCI usa CumulusCI.** Su propio cumulusci.yml es un ejemplo de uso avanzado real — buena referencia.
5. **Bootstrap ClickUp: usar List ID (tipo "6") como parent del Doc.** Usar Folder ID crea el doc pero no aparece en navegación.

### 2026-09-16 — Sesión 2: Validación de vigencia y re-scope

**Qué pasó:**
Antes de seguir con las 29 tasks, se validó si CumulusCI sigue vigente como metodología CI/CD Salesforce. Respuesta: vigente como herramienta de nicho (ISV / paquetes 2GP / NPSP), no como metodología dominante. Se re-enfocó el proyecto (ADR-001 en el Doc de ClickUp), se descopearon 2 tasks, se agregaron 2 a Phase 3 y se creó Phase 6 (DevOps Center nativo + sf CLI + DX MCP). Se agregó "Tool landscape 2026" al OKF de TA.

**Lecciones:**

1. **Validar vigencia ANTES de planear el estudio completo.** El plan de mayo asumió "dominante"; un check de 15 min (releases, commits, mercado) cambió el enfoque. Todo bootstrap de estudio de herramienta lleva una task "Validar vigencia y posicionamiento" en Phase 1.
2. **"Mantenido" ≠ "estándar de mercado".** CCI tiene releases cada 1-3 meses y equipo de Salesforce detrás (commits `@W-…`). Eso prueba que no está muerto, no que un cliente enterprise lo use. Preguntar siempre: ¿quién lo mantiene? vs ¿quién lo usa y para qué modelo (org vs package development)?
3. **El OKF de TA es estratégico; el hueco tool-level es real.** `lifecycle-deployment/` no mencionaba CCI ni DevOps Center nativo.
4. **El clon local se desactualiza.** Fork en abril, upstream en septiembre. Antes de evaluar vigencia: `git fetch upstream` o `gh api repos/...`.
5. **El fork tenía remote HTTPS sin credencial → `git push` falla con "could not read Username".** Cambiado a SSH (`git@github.com:fernand-zuili/CumulusCI.git`). Los demás repos ya usan SSH; verificar `git remote -v` en cada proyecto nuevo.
