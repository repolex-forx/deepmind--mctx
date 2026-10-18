# Repolex Knowledge Graph of deepmind/mctx

RDF knowledge graph data for [deepmind/mctx](https://github.com/deepmind/mctx), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download deepmind/mctx
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 428bfb7e1c931715cd3d74f9c65e9991afd86df8
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 428bfb7e1c931715cd3d74f9c65e9991afd86df8
│           └── chunk-001.nq.gz
├── blob
│   ├── 0bb4e823a0b584bb3fe958e3114a96126aee3092.nq.gz
│   ├── 1280ab5edc62403d3ad910207866ce91dd67e78f.nq.gz
│   ├── 140a876ec0c5279b510121f80f6a589ad39702a9.nq.gz
│   ├── 1f4a1f0a60cd93d4b8bd56ab42c1529a6f07a3ba.nq.gz
│   ├── 223947ccd836a1b351333eea914c5c6b6dae78c8.nq.gz
│   ├── 31c7986ce4b325eeaedd6327dbb133f7be3b26b2.nq.gz
│   ├── 4992e2abc581b1a98d8db2e080e99672209659da.nq.gz
│   ├── 4aab31578955d1c839ed4dfd85d7bdc5991806c0.nq.gz
│   ├── 549dca9b69faf21fcf6a992e27de0aada30d4a3c.nq.gz
│   ├── 58ca0fcd99b064702e27c71f0d7034b637dddcb9.nq.gz
│   ├── 5b492c1f72cc0daee488db5cf148d641c7a328b2.nq.gz
│   ├── 78fd7b7bc7bca0a5e40b16923e534093f105632c.nq.gz
│   ├── 892667749538fa809d3d6eb963ce07c105811f67.nq.gz
│   ├── 908eb866c250145551b862bdd2e319b3af2de677.nq.gz
│   ├── 977cd355868d8a1938fcde7e989a8fedcbcc1f58.nq.gz
│   ├── 9e66d0017ff6662ee9bd1271a61ce6cb021552f2.nq.gz
│   ├── abd3481aba9af55f9d5404efe40d00cc984efc4e.nq.gz
│   ├── af9b0431c81f65e745ff52ed1d5c80e937480af9.nq.gz
│   ├── b3ca14a5e841c42037cd7e59d16b55dbbdcf7535.nq.gz
│   ├── c2baea52e1c7546de1a3d4d4a853cd9014fadf91.nq.gz
│   ├── c60265b98a95aca5510470234f7722dccb9c6f18.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── dd9eb84cf3c88c4260f9eee3fbe427920a9ed4c6.nq.gz
│   ├── e4832d24aff7f9ab0bc5f27ced4d4fd03796c543.nq.gz
│   ├── e844c73870fe381b0a2571f03644dd3906162238.nq.gz
│   ├── f6f6ad309c3a150d6533da00a1117e306f2c9df0.nq.gz
│   ├── fbb26774ef81fc0503acf62e64728981adcf8e68.nq.gz
│   ├── fc9391b278a4df36b3b08f5440bf9384f377a1c9.nq.gz
│   └── ff13ba14df6135ddef8ab86181619b861e12cd6c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 428bfb7e1c931715cd3d74f9c65e9991afd86df8.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 37 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[deepmind/mctx](https://github.com/deepmind/mctx)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
