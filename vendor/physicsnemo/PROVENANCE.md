# Vendored reference snapshot — NVIDIA PhysicsNeMo

This directory contains a partial, read-only reference snapshot of files from
the official [NVIDIA/physicsnemo](https://github.com/NVIDIA/physicsnemo)
repository, vendored for offline reference during the GeoTransolver /
modal-analysis surrogate investigation carried out with the
`physicsnemo-discover` skill (see `.claude/skills/physicsnemo-discover/`).

- **Source repository:** https://github.com/NVIDIA/physicsnemo
- **Commit:** `426f7552da4b4fa675e404e8a4f437e27681b668`
- **License:** Apache-2.0 (see each file's original SPDX header, preserved as-is)
- **Scope:** Only the files/directories actually read and cited during the
  investigation — not a full mirror of the upstream repository.

## Contents

- `physicsnemo/models/geotransolver/` — GeoTransolver model + context builder
- `physicsnemo/nn/module/gale.py`, `physicsnemo/nn/module/pooling.py` — GALE attention, `AttentionPooling`/`MeanPooling`
- `physicsnemo/experimental/uq/variational_gp_head.py` — scalar-regression GP head (experimental)
- `physicsnemo/models/domino/mlps.py` — `AggregationModel` (per-point MLP, not a spatial pooling head)
- `physicsnemo/models/meshgraphnet/`, `physicsnemo/models/mesh_reduced/`, `physicsnemo/models/transolver/` — alternative model families for unstructured-mesh data
- `physicsnemo/datapipes/cae/`, `physicsnemo/datapipes/readers/base.py`, `physicsnemo/datapipes/datapipe.py`, `physicsnemo/datapipes/gnn/utils.py` — datapipe base classes
- `docs/api_models.rst`, `docs/api/models/geotransolver.rst`, `docs/api/models/transolver.rst` — API doc index pages
- `examples/structural_mechanics/crash/`, `examples/structural_mechanics/drop_test/`, `examples/structural_mechanics/deforming_plate/` — closest existing structural-mechanics reference examples
- `examples/cfd/external_aerodynamics/transformer_models/` — existing GeoTransolver → pooling → scalar-head (drag coefficient) pipeline, the closest live precedent for a global-scalar output head

To refresh or extend this snapshot, re-run the `physicsnemo-discover` skill
against a fresh clone of the upstream repository and copy the newly cited
paths here.
