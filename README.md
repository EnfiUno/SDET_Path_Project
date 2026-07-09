# SDET_Path_Project

Personal SDET learning path deliverables. Each module was developed on its own branch and merged into `main` — new modules should follow the same pattern: branch off `main`, build the deliverable, push, merge back.

## Module index

| # | Module | Folder | Deliverable |
|---|---|---|---|
| 00 | Foundations & Mindset | [`00_FoundationandMindset`](./00_FoundationandMindset) | 1-page Automation Strategy memo: pyramid shape, test types, non-functional risks, what NOT to automate |
| 01 | Front-end Automation | repo root ([`pages/`](./pages), [`tests/01_FrontEndAutomation.spec.js`](./tests/01_FrontEndAutomation.spec.js)) | 5-test Playwright POM suite against SauceDemo, auto-waits, screenshots + trace on failure |
| 02 | Programming | repo root ([`tests/02_Programming_Class.spec.js`](./tests/02_Programming_Class.spec.js), [`tests/02_Programming_Test.spec.js`](./tests/02_Programming_Test.spec.js)) | Code challenge — clean OOP, classes/methods, error handling |
| 03 | API Automation | [`03_API-Automation`](./03_API-Automation) | API suite: 5+ tests, OAuth token retrieval, schema validation, parametrised from CSV/JSON (Restful Booker) |
| 04 | SQL | [`04_SQL`](./04_SQL) | 10+ SQL queries on a seeded sample DB covering JOINs, GROUP BY/HAVING, subqueries, window functions, one CTE |
| 05 | Code Versioning (Git) | [`05_CodeVersioning_Delivery`](./05_CodeVersioning_Delivery) | One clean PR in a sandbox repo: feature branch, conventional commits, one rebase, one resolved merge conflict, one squashed history |

Modules 01 and 02 both drive the same app (SauceDemo) with Playwright, so they share the root-level Playwright project (`package.json`, `playwright.config.js`, `pages/`, `tests/`) — mirroring how the reference project (github.com/UnoMauro/saucedemo) keeps its main UI project at repo root. Module 03 targets a different service (Restful Booker over plain HTTP) and stays a self-contained sibling project with its own `package.json`/config, the same way `apitesting/` sits alongside that reference repo's root project.

## Adding a new module

1. `git checkout main && git pull`
2. `git checkout -b <NN>_<ModuleName>`
3. Add the module's folder and its deliverable
4. `git push -u origin <NN>_<ModuleName>`
5. `git checkout main && git merge <NN>_<ModuleName> && git push origin main`
