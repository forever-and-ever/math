# Lake package sharing

All worktrees share dependency checkouts and dependency build artifacts through manifest-keyed
pools below the primary checkout's `.lake/shared-packages/`. Each worktree's own `.lake/build/`
remains private. `scripts/share-lake-packages.sh` owns this layout; do not replace its links with
copied package directories. A host may place the pool on another filesystem by replacing
`.lake/shared-packages/` with a directory symlink; package links resolve the physical location.

The common `post-checkout` hook links new worktrees automatically. Run
`scripts/share-lake-packages.sh --install` after a fresh clone to install the hook and reconcile
all existing worktrees. The canonical check also repairs the current worktree before invoking
Lake.

Never run `lake update` against a shared package link. Detach exactly one worktree that will own
an intentional `lake update`, perform the update there, then run
`scripts/share-lake-packages.sh` to validate and move the result into its new manifest-keyed
pool. Do not detach worktrees that merely receive an already-locked toolchain or manifest through
checkout, cherry-pick, merge, or restore; reconcile them directly after the lock files change.
Only one detached update may exist at a time. Its staging tree lives beside the shared pool and
uses copy-on-write when the filesystem supports it.
