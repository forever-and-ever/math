# Publication seam

`publications.json` is the canonical map from presentation-free semantic sources to routes below
`/math/` on `../eternalist.moe`. Its single `index` entry owns `/math/`; a `collection` owns a
subject landing page; a `reference` owns a reusable expository aid below a collection; every
reusable established construction, definition, lemma, or reduction is a `module`; and every
research-result exposition is a `result`. Reference, module, and result routes sit below a
collection. Adding one requires its source, its manifest entry, and its listing by its immediate
parent, but no Eternalist content patch.

Each optional `graphs` entry binds a collection to one typed JSON proof graph. Public graph nodes
contain established mathematics only. `requires` edges state logical dependency and must be
acyclic; lateral relations may record specialization, instantiation, strengthening, transport, or
dispute without changing the proof order. Open cuts, attack status, probabilities, and roadmaps
remain in repository ledgers and never enter the public graph.

An optional `redirects` entry keeps a retired route resolvable: its `route` sits directly below a
collection and names no publication, its `target` names a non-index publication, and its optional
`fragment` names an `id` in the target source. Eternalist emits a static meta-refresh document at
the route and omits it from the sitemap; `scripts/publish.sh` verifies it with the publication
routes.

Every listed source must contain no `<style>` element, inline `style` attribute, or stylesheet
link. Eternalist owns typography, color, layout, responsive behavior, and print presentation
through its central house styles. Use only the semantic class hooks defined by Eternalist's
dense-publication profile; change that shared contract at its owner rather than creating
page-local presentation.

Eyebrows are forbidden unless explicitly requested. Do not add kickers, supertitles, numbered
pre-headings, category copy above titles, or other small text whose function is to occupy visual
space. Every surviving label must change the interpretation of the object it labels.

Long-form module and result expositions use the exact top-level partition **Known Stuff** /
**New Stuff** / **Bookkeeping**. The informality of “Stuff” is intentional. Definitions,
inherited results, and prior art belong under Known Stuff; New Stuff begins at the first claim
proved by the present work and contains its proof and consequences. Bookkeeping owns validation,
provenance, artifact links, priority qualifications, and references.

Each canonical top-level section is a native `<details>` disclosure, closed by default, with its
real `h2` inside the `summary`. Do not replace this with JavaScript, synthetic buttons, or
presentational concealment. Subsection fragment links must remain capable of revealing their
closed ancestor, and print must expose all section contents.

Every long-form module or result begins its `.shell` with one visible
`<section class="abstract" aria-label="Abstract">` before the contents. State the searchable
problem name, parameters, conclusion, restrictions, consequences, and unresolved boundary with
the density of the existing verdict blocks. This prose is the sole abstract source; Eternalist
derives description metadata from it. Do not maintain a hidden or separately authored abstract.

The standalone HTML owns its mathematics directly. Author every structurally mathematical
expression as native MathML; matrices use `mtable`. Do not introduce MathJax, KaTeX, TeX
preprocessing, generated equation images, CSS-drawn notation, or a second mathematical source.
Unicode remains lawful for isolated symbols in prose, titles, metadata, and literal words. A
`.formula` is presentation around one direct `<math display="block">` child, never a substitute
for mathematical markup.

The contents list must mirror the document hierarchy through `h4`: `h2`, `h3`, and `h4` links
occupy successive nested list levels. Every `h2`, `h3`, and `h4` owns a stable fragment `id` and
ends with exactly one semantic self-link of the form
`<a class="fragment-link" href="#section-id" aria-label="Link to this section">#</a>`.
Within a `.major-section`, every `h3` and `h4` outside a `summary` directly heads a
`<section class="fragment-section">` containing the full subsection. A heading inside a
`summary` uses the enclosing `details`; a collection heading uses its existing `section`. This
ownership lets Eternalist frame the complete destination when a fragment link is followed. The
source owns this fragment contract; Eternalist owns its presentation. `h5` is a local heading
inside a bounded proof component and does not enter the page-level contents.

After changing a listed source, the manifest, or any artifact a source describes, publication is
incomplete until `scripts/publish.sh` succeeds. This repository owns that release transaction
autonomously; Eternalist supplies the import, presentation, and deployment contracts. A normal
GitHub push does not update the live site.
