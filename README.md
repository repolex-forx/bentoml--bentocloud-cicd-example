# Repolex Knowledge Graph of bentoml/bentocloud-cicd-example

RDF knowledge graph data for [bentoml/bentocloud-cicd-example](https://github.com/bentoml/bentocloud-cicd-example), parsed by [repolex](https://repolex.ai).

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
rlex download bentoml/bentocloud-cicd-example
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── fc2f6060188e71fc2b89caf20e37ce735d5a486e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── fc2f6060188e71fc2b89caf20e37ce735d5a486e
│           └── chunk-001.nq.gz
├── blob
│   ├── 39ed765ae6deb07c606c21698cedcb766be9a7a7.nq.gz
│   ├── 6769e21d99a63338394e47bc4c7d0aba1e88d5a5.nq.gz
│   ├── 75e00de4e35b816d36d72c174d8d29e275b8b446.nq.gz
│   ├── 7b29e5d7bf03b750970e8772e1827154a894fbd8.nq.gz
│   ├── 9a1d7936fa25cbeff11ef64ef45b20ef2672d563.nq.gz
│   ├── b94f695f2e8df8c4ab323952a264971921c41ec6.nq.gz
│   └── d89a50ec12c89cd7076cfd0ae5c9b29bba8f89d6.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── fc2f6060188e71fc2b89caf20e37ce735d5a486e.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 14 files
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

[bentoml/bentocloud-cicd-example](https://github.com/bentoml/bentocloud-cicd-example)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
