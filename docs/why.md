# Why — CumulusCI Study Project

> Re-enfocado 2026-09-16 tras validar vigencia (ver docs/lessons-learned.md, sesión 2).

## What is this project trying to achieve?
Entender el **package development model** de Salesforce y los patrones de orquestación de CI/CD que CumulusCI implementa — flows declarativos, dependencias entre paquetes, metadata ETL, datos sintéticos, release 2GP — porque son transferibles aunque la herramienta del cliente sea otra.

En paralelo, cubrir lo que un TA enterprise sí ve en campo en 2026: **DevOps Center nativo + sf CLI + DX MCP server** (org development model).

## What problem does it solve?
El OKF de TA cubre la capa estratégica (topología de sandboxes, SCM, gobernanza, runbook de deploys) pero no la capa de herramienta: cómo se modela un pipeline, cómo se manejan dependencias entre paquetes, cómo se generan datos de prueba. Este proyecto llena ese hueco.

## Contexto de vigencia (2026-09)
- CumulusCI sigue mantenido por Salesforce (v4.10.1, sep-2026), pero es herramienta de **nicho**: ISVs, paquetes 2GP, productos de Salesforce.org (NPSP/EDA), MetaDeploy.
- **No es "la metodología dominante"** de CI/CD Salesforce. En orgs de cliente el estándar es DevOps Center nativo, Copado/Gearset/Flosum o sf CLI + GitHub Actions.

## How will I know when it is done?
- Puedo explicar flows, tasks, orgs, `cumulusci.yml` y el modelo de dependencias de memoria
- Puedo montar un proyecto CumulusCI desde cero y correr un flow 2GP beta
- Tengo una tabla de equivalencias CCI ↔ DevOps Center ↔ sf CLI en `CumulusCI-FINAL.md`
- Monté un pipeline en DevOps Center nativo y ejecuté un deploy vía DX MCP server
- El OKF de TA tiene sección "Tool landscape 2026"

## Fuera de alcance (descopeado 2026-09-16)
Robot Framework, push upgrades, MetaDeploy, headless mode — nicho ISV puro, desplazados por Playwright directo / DevOps Testing.
