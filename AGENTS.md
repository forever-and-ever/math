math: agentic contributions to mathematics as coherent bricks, verified to academic standard or beyond; formal verification preferred

## gate
- Lean: every compiler and enabled syntax-linter warning is an error; automatic implicit variables off; all default mathlib env linters pass project-wide
- Publication-facing theorems: complete transitive axiom set compared byte-for-byte with reviewed snapshot
- After changing a listed publication source, manifest, or described artifact: `scripts/publish.sh` must succeed; plain push never updates live site

## invariants
- Forbidden: `sorry`, `admit`, project `axiom`s, `unsafe`, `partial`, `native_decide`, `implemented_by`, `run_tac`, external declarations, equivalent apertures
- Linter suppressions and local relaxations forbidden unless nearby comment states irreducible mathematical reason and audit permits it
- Strictness exposes debt → repair declaration, proof, interface, docs; never weaken the check; skip opt-in linters that only compel ceremonial prose
- Kernel acceptance is the floor: audit definitions for vacuity, quantifier drift, multiplication order, empty-witness loopholes, coercion loss, claim mismatch
- `scripts/share-lake-packages.sh` owns shared Lake pools; never replace its links with copied packages; never `lake update` through a shared link
- Credit agentic work to GPT-5.6 Sol as first author, human role "elicited by @eternalism_4eva", unless countermanded per work
- Never replace agent credit with Anonymous, collapse elicitation into coauthorship, or demote agent to acknowledgements
- Keep every materially relevant, lawfully distributable paper in `references/` as `author-year-short-title.pdf`; never silently replace a stored version
- Each PDF: same-stem Markdown sidecar with citation, source, DOI, retrieval date, SHA-256, results relied on, defects, open audit duties
- `references/README.md`: local bibliography separating peer-reviewed, preprints, superseded, withdrawn or erroneous claims
- Prompts for Pro or other external models: transient, under `/tmp`; never committed or filed unless ordered; keep only results surviving audit
- Public GitHub issues: durable ledger for material, coherent, genuinely deferred work; record boundary, open obligations, deps, acceptance test
- No ceremonial tickets for work finishable now; no private auxiliary tracker
- `SALVAGE.md`: canonical index of reusable math from attacks that missed their target; distill or reject; never store raw external reports instead
- Salvage record: kind, evidence, disposition, scope, use, next promotion step; never promote `reported` or `computational` evidence to theorem
- Ownership: `FRONTIER.md` strategy citing record ids; `FORMALIZATION.md` Lean-checked claims; `audits/` review evidence; issues scheduled hardening

## routes
- Lake update, fresh clone, or worktree package sharing → `docs/lake-sharing.md`
- Changing publication sources, `publications.json`, routes, redirects, or exposition markup → `docs/publication.md`
- Writing or refactoring finished Lean proofs → `docs/lean-proof-style.md`
