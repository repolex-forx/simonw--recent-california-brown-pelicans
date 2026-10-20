# Repolex Knowledge Graph of simonw/recent-california-brown-pelicans

RDF knowledge graph data for [simonw/recent-california-brown-pelicans](https://github.com/simonw/recent-california-brown-pelicans), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/recent-california-brown-pelicans
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ebb3164a05c2042b504ce88c409ba3b563d27882
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ebb3164a05c2042b504ce88c409ba3b563d27882
│           └── chunk-001.nq.gz
├── blob
│   ├── 0b95aa5532815c947ab0b341a4a3c446094cbbbb.nq.gz
│   ├── 11d37d26f24fe1d7021245b4a4ef6ce668cb69b8.nq.gz
│   ├── 7343c14baaf731941097644b7814a4132c7f4934.nq.gz
│   ├── c276f31368b1ee85509be187512d8217726f5c7d.nq.gz
│   ├── c4329a0d9a507b702beda031b24aa207d140f4b8.nq.gz
│   ├── cf5c9029e01143dcd57a89057a34f5f8451d0e83.nq.gz
│   └── e29e8101ff69971f2eab46eab5df9e03195a312c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ebb3164a05c2042b504ce88c409ba3b563d27882.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 15 files
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

[simonw/recent-california-brown-pelicans](https://github.com/simonw/recent-california-brown-pelicans)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
