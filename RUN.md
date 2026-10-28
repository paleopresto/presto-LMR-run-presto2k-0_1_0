# PReSto LMR run on PReSto2k 0_1_0

This repository runs the PReSto LMR reconstruction on the [PReSto2k 0_1_0](https://lipdverse.org/PReSto2k/0_1_0/) compilation: 1101 records.

- Membership comes only from the published compilation, read from the
  LiPDverse whole-database export
  [2026-10-27](https://lipdverse.org/dev/export/database-2026-10-27/)
  (`compilations` table) by presto-recipes `pools/compilation_pool.R`.
- `query_params.json` (`mode: bundle`) pins the bundle by URL and sha256:
  presto-recipes release
  [pools-2026-10-27-r1](https://github.com/paleopresto/presto-recipes/releases/tag/pools-2026-10-27-r1).
  Its files are the compilation's LiPD files, checked against the export's
  md5 values and trimmed to the member records.
- The code and algorithm config are those of
  [presto-LMR-run-presto2k-0_0_1](https://github.com/paleopresto/presto-LMR-run-presto2k-0_0_1)
  at d30cd22, unchanged, so this run differs from that one only in its data:
  PReSto2k 0_1_0 instead of 0_0_1. The records added and removed are listed in
  [changes_from_0_0_1.csv](https://github.com/paleopresto/presto-recipes/blob/pools-2026-10-27-r1/pools/compilations/PReSto2k/0_1_0/changes_from_0_0_1.csv).

Committing `query_params.json` triggers the reconstruction workflow.
