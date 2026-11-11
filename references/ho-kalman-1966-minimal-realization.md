# Ho and Kalman (1966): minimal realization from a Hankel matrix

**Citation.** B. L. Ho and R. E. Kalman, “Effective construction of linear state-variable models
from input/output functions,” *Regelungstechnik* **14**(12) (1966): 545–548.
DOI: 10.1524/auto.1966.14.112.545.

- Work identity: https://doi.org/10.1524/auto.1966.14.112.545
- Canonical source: publisher record at the DOI (Walter de Gruyter, now *at – Automatisierungstechnik*)
- Local artifact: none; no lawfully redistributable full text was located
- Version and status: peer-reviewed journal article
- Retrieved: 2026-09-30 (bibliographic metadata only)
- SHA-256: not applicable
- Access and retention: metadata-only record
- Synopsis basis: the standard statement of the Ho–Kalman realization theorem; the article's full
  text was not inspected

## Result used

A sequence of matrices `Γₙ` has a finite-dimensional realization `Γₙ = O Aⁿ U` exactly when its
block Hankel matrix `[Γ_{i+j}]` has finite rank, and the least dimension of a realization equals
that rank. The article gives an algorithm that constructs a minimal realization from the Hankel
matrix.

The matrix-mortality series cites this for context only. The lower bound it uses, that the
Hankel rank bounds every realization dimension from below, is proved on the page from the
factorization `Γ_{i+j} = (O Aⁱ)(Aʲ U)`; the realizations it uses are constructed explicitly and
checked in Lean.

## Source Assessment

No correction or retraction is known. Because the full text was not inspected, page and theorem
numbers are not cited.
