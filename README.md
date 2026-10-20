# Repolex Knowledge Graph of klen/asgi-babel

RDF knowledge graph data for [klen/asgi-babel](https://github.com/klen/asgi-babel), parsed by [repolex](https://repolex.ai).

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
rlex download klen/asgi-babel
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c29ba605f829343641d96ef8f845660450bb4e38
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── c29ba605f829343641d96ef8f845660450bb4e38
│           └── chunk-001.nq.gz
├── blob
│   ├── 0d7db2e70341d714b105c6f518ededec1b6c0b2b.nq.gz
│   ├── 113009e8005ca80ec8558f82a337973d7ac35125.nq.gz
│   ├── 20c850c6a393ec7d20a769f5602ead5f785d716d.nq.gz
│   ├── 20e34b982c688730ab96b66c1cd33c49efcc9b93.nq.gz
│   ├── 2247d5f95a7193c7221b9464debe167763b4fae3.nq.gz
│   ├── 4c757da01d64b80cf9eb3e17696293efe370506a.nq.gz
│   ├── 4f918468371e898e949aeeba02cfe0e5203b0785.nq.gz
│   ├── 6436e25e59172b8918ba371e183a645ffe83f970.nq.gz
│   ├── 846582128c3933eeaa285c4a63e09d83370ffd15.nq.gz
│   ├── 853a7f90f355624a0c1cc193ed3d4af40c419e7b.nq.gz
│   ├── 967aa78ed530223bc98769d7317039f71738f022.nq.gz
│   ├── 9c21dc16fb3ef322c0c43aa86f9657bf418b7c74.nq.gz
│   ├── aef93db86501b4e8d302a8a756dbc08bfdb47e84.nq.gz
│   ├── b0bf2667c42a10e7308544666b36b55f57228584.nq.gz
│   ├── c7c0487f310b30bf4f5b80284d8bb070c145dd12.nq.gz
│   ├── e294cb49fe4b9c079010fda4203dd922ba8c4bd8.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── f79169654dc278001319482d8ad88526a981c626.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c29ba605f829343641d96ef8f845660450bb4e38.nq.gz
├── issue
│   └── issue.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 25 files
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

[klen/asgi-babel](https://github.com/klen/asgi-babel)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
