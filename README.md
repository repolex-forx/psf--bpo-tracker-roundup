# Repolex Knowledge Graph of psf/bpo-tracker-roundup

RDF knowledge graph data for [psf/bpo-tracker-roundup](https://github.com/psf/bpo-tracker-roundup), parsed by [repolex](https://repolex.ai).

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
rlex download psf/bpo-tracker-roundup
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 88ef50697aa1a4e7dbf670046f012524921d994d
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 88ef50697aa1a4e7dbf670046f012524921d994d
│           └── chunk-001.nq.gz
├── blob
│   ├── 07b258078fd283a8bde590205ea4c218f886eca5.nq.gz
│   ├── 0b1dce0a1b4807cef675118d7f2a5dd947202d88.nq.gz
│   ├── 22f41223a47e0824ecdd48101c2727a8ea92956b.nq.gz
│   ├── 32b647a535fb0970d2bb285d5327521d56e4aa3c.nq.gz
│   ├── 51e1ca1ce73013c03544c6c30d1bc127df9b17b1.nq.gz
│   ├── 56428d7f05ebaeccc1c89c52834c3c40827ec30c.nq.gz
│   ├── 69c0a1bf0c64882700492eb54cbbe96f9bcaec15.nq.gz
│   ├── 6a13a0ea0be4aecc03d5f62ab83ab8621ccbb8f6.nq.gz
│   ├── 7b2946d263cf7c2a0913ed74d7af758f989992d3.nq.gz
│   ├── 82bfa35af115f28c27c03f4d829be94cde90f1e0.nq.gz
│   ├── 9230d4636f65d17ad713c1a7fccdeca6f4658fad.nq.gz
│   ├── 97ca50a1bc3f91e21dfa5f200698098e05c67eb1.nq.gz
│   ├── 9d43eecf152013dee2e5b27c4dc16e071fbccd3f.nq.gz
│   ├── abf62271e007eda4f95f924e226b447526775371.nq.gz
│   ├── c33d4a1d2690f7681ef1dd37e414f48f521e2acd.nq.gz
│   ├── c41ddd333068122d22bbb11ea2d9318a13be6873.nq.gz
│   ├── c9efc5844a2627a8474949724a2aefe4ab2baee4.nq.gz
│   ├── cc7a5553f96a21c95083cf5e6b8598c9ca79669b.nq.gz
│   ├── e167e5016a3921efe7b0e7725fc61c2884ab430b.nq.gz
│   ├── e49fc18082299fabc41a4ea87c2c630de9c8a35a.nq.gz
│   ├── fc8b3b296acc57f6a405f722512a9e518aeab250.nq.gz
│   └── fdc1382faf1cc06ef8f801941d71c9c0f9b33d54.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 88ef50697aa1a4e7dbf670046f012524921d994d.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 29 files
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

[psf/bpo-tracker-roundup](https://github.com/psf/bpo-tracker-roundup)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
