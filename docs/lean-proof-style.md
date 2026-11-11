# Lean proof style

Finished proofs expose a static proof DAG, not the temporal trace of interactive
proof search. Use ordinary Lean and mathlib naming, formatting, namespace, and
lint conventions, sharpened by the following rules:

- Prefer direct proof terms when their structure is immediately legible.
- Otherwise build the proof from semantically named `have` declarations,
  `calc` chains, explicit constructors, and `refine` applications that expose
  the outer term.
- Write known theorem arguments explicitly. Naked `apply` sequences are
  exploratory residue.
- Preserve hypotheses; derive normalized forms as new named facts instead of
  rewriting or simplifying hypotheses in place.
- Put automation at leaves whose exact proposition is visible. Important
  proofs must expose their logical skeleton.
- Make cases and induction branches explicit and named. Avoid dependence on
  ambient goal ordering.
- Avoid `simp_all`, `at *`, long semicolon pipelines, `all_goals`, `any_goals`,
  goal swapping, and comparable global proof-state mutation unless the final
  proof has an irreducible reason to require them.

For example:

```lean
def compose {A B C : Sort*} (f : A → B) (g : B → C) (x : A) : C :=
  g (f x)

theorem transport {α : Sort*} {P : α → Prop} {x y : α}
    (hxy : x = y) (hx : P x) : P y := by
  have hy : P y := by
    simpa [hxy] using hx
  exact hy

theorem chain {α : Type*} [Preorder α] {a b c d : α}
    (h₁ : a ≤ b) (h₂ : b ≤ c) (h₃ : c ≤ d) : a ≤ d := by
  calc
    a ≤ b := h₁
    _ ≤ c := h₂
    _ ≤ d := h₃
```

After discovery, refactor accepted tactic scripts until their outer logic,
meaningful intermediate propositions, relational chains, and automation
boundaries are visible without mentally executing the proof state.
