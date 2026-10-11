# Repolex Knowledge Graph of agronholm/aionursery

RDF knowledge graph data for [agronholm/aionursery](https://github.com/agronholm/aionursery), parsed by [repolex](https://repolex.ai).

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
rlex download agronholm/aionursery
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c8f5636c65d5a5f83b98533ff780423857fe28a0
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── c8f5636c65d5a5f83b98533ff780423857fe28a0
│           └── chunk-001.nq.gz
├── blob
│   ├── 07806f8af9dd3253ebdb5710b67e73124aea4941.nq.gz
│   ├── 1b3723ba739093384186bdea50137d3e3d2fb934.nq.gz
│   ├── 1b618aae653e6f702f95c50ba07921ee00ddfc86.nq.gz
│   ├── 779232f9fd593719fad2924decd2381c82850e20.nq.gz
│   ├── 7d9cef394927bed5e1f3f1dc02850ce36aadff38.nq.gz
│   ├── 8bfc343958177339e74d0bc52353322ed3b1f696.nq.gz
│   ├── 95b48accaf6ab7cca1bf1eb6f729f62708e4d0ee.nq.gz
│   ├── b86efb6d45ea70a21e24d66092f236be839696cb.nq.gz
│   ├── bb08fb459cef71c6e9b79913420a0e5a2181d6f6.nq.gz
│   └── e04af1aa6d4f97d2687c047918b1a533a2aa8027.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c8f5636c65d5a5f83b98533ff780423857fe28a0.nq.gz
├── issue
│   └── issue.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 17 files
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

[agronholm/aionursery](https://github.com/agronholm/aionursery)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
