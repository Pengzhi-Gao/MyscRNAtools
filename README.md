# MyscRNAtools

This repository distributes **MetaNetAssoc 0.4.0**, an R package for linking
differential metabolites to enriched biological terms through
metabolite--protein interaction (MPI) and protein--protein interaction (PPI)
networks.

## Install

Download the source package from [`dist/MetaNetAssoc_0.4.0.tar.gz`](dist/MetaNetAssoc_0.4.0.tar.gz), then run in R/RStudio:

```r
install.packages(
  "MetaNetAssoc_0.4.0.tar.gz",
  repos = NULL,
  type = "source"
)

library(MetaNetAssoc)
packageVersion("MetaNetAssoc")
```

Alternatively, install directly from this repository with `remotes`:

```r
install.packages("remotes")
remotes::install_github("Pengzhi-Gao/MyscRNAtools", subdir = "MetaNetAssoc")
```

## Contents

- [`MetaNetAssoc/`](MetaNetAssoc/) — full standard R package source, function
  reference, vignettes, tests, and synthetic demonstration data.
- [`dist/`](dist/) — installable versioned `.tar.gz` source package.

## Highlights in version 0.4.0

- Builds a STRING PPI network from differential genes for human or mouse;
  supports direct STRING API retrieval and an offline STRING edge table.
- Builds MPI from differential genes, HMDB identifiers, and an auditable
  metabolite--gene evidence table.
- Supports `clusterProfiler` enrichment and raw enrichment-table export.
- Includes bundled human MPI evidence and an Ensembl-Compara-projected mouse
  MPI reference.
- Includes MPI matching diagnostics and ggplot-based ranking, heatmap, and
  association-network plots.

See the package tutorial after installation:

```r
vignette("deg-hmdb-workflow", package = "MetaNetAssoc")
```

## Important interpretation note

MPI associations are evidence-backed network links, not proof of direct
binding or causality. The bundled mouse MPI reference is an orthology
projection of human evidence; consult the package metadata before using it for
biological interpretation.
