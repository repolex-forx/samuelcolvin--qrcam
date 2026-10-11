# Repolex Knowledge Graph of samuelcolvin/qrcam

RDF knowledge graph data for [samuelcolvin/qrcam](https://github.com/samuelcolvin/qrcam), parsed by [repolex](https://repolex.ai).

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
rlex download samuelcolvin/qrcam
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ed1fffdd9dc1ce27d44555c6c83e1098aff38a14
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ed1fffdd9dc1ce27d44555c6c83e1098aff38a14
│           └── chunk-001.nq.gz
├── blob
│   ├── 6a96f3ff0106080693159861e0df4177e638c77f.nq.gz
│   ├── 75306517965a54731b94dca8bace640e856af115.nq.gz
│   ├── 809f74b5ec7703d0d1c5082cf5cad2080f75a892.nq.gz
│   ├── 966221d097b0f51c4543418b1cb2fe8299e4ef11.nq.gz
│   ├── bacfe4bcba88af3bdbe02058666069976a0dd93f.nq.gz
│   ├── d7f8519e11158598d0c0eedde3617cff4be0f0ad.nq.gz
│   ├── db2324c79ccd470733ed7126ab9317426778be01.nq.gz
│   └── e10481f59afa75a6e122a8bd32b7749547412eaf.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ed1fffdd9dc1ce27d44555c6c83e1098aff38a14.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 14 files
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

[samuelcolvin/qrcam](https://github.com/samuelcolvin/qrcam)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
