# Repolex Knowledge Graph of sphinx-contrib/vimbuilder

RDF knowledge graph data for [sphinx-contrib/vimbuilder](https://github.com/sphinx-contrib/vimbuilder), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/vimbuilder
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c2c1e17206c2c72d0319de503680732dbdc50b89
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── c2c1e17206c2c72d0319de503680732dbdc50b89
│           └── chunk-001.nq.gz
├── blob
│   ├── 031fdfa48e507a739ca119708505494ea8b25a09.nq.gz
│   ├── 07525f6e9205b8853bb3962e87ec453cd2b88d9c.nq.gz
│   ├── 2f2cf9862a629e8e093e8a4183df4ebd05a53023.nq.gz
│   ├── 42243715c2d93bf1cab7203df145e1a07251739f.nq.gz
│   ├── 4f220e8a098979ae369417a074ee9f8f4538aaee.nq.gz
│   ├── 5014b1d837a3da77817eafe2f12400effb3bf6dd.nq.gz
│   ├── 509c63686f5a7fd7b8cfcbb2222307c19ef77b15.nq.gz
│   ├── 5232642a153ba4137d4621bb01460191af389bf6.nq.gz
│   ├── 7b09ea1e73b3ccc0996cc33b12304a7658058293.nq.gz
│   ├── 81b15fb6dc590c7a8669ddf496dd6b7bf6e3f715.nq.gz
│   ├── 9ab67c219753944aa1ec1306c9b1a573a6666a9b.nq.gz
│   ├── ada5f0bc5e3280df8a14187c4a36b89f1dd5d52f.nq.gz
│   ├── b0f9d22d74f0e3111f3632504394772f404f0ce4.nq.gz
│   ├── b779e981c68997d156440e039911d18e2a020b33.nq.gz
│   ├── c19c48301f58487fdc0e1a9c8eb93347b2db2b52.nq.gz
│   ├── c6a1f76d665164f42546010dee0d7b539142f881.nq.gz
│   ├── ce262d32c413e67843d3d599c9221a290be5e6f1.nq.gz
│   ├── ce73547ac981ef32efef89514d0e881595dbe14d.nq.gz
│   ├── ce9dd46eee43c7f07f3fd602120e2934363eb449.nq.gz
│   ├── d227e7e71571d18ed1706a1627070720bf2d4e5e.nq.gz
│   ├── f0dbfeb20a46ad25c2d3b880a057ba7e6a3857c1.nq.gz
│   ├── f2fe5d9ddcd771128f891388e288e7dd671e0097.nq.gz
│   └── f78e9a71351a9015e808b0c7bb6275159ec6310b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c2c1e17206c2c72d0319de503680732dbdc50b89.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 29 files
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

[sphinx-contrib/vimbuilder](https://github.com/sphinx-contrib/vimbuilder)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
