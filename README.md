# Repolex Knowledge Graph of tox-dev/pyproject-fmt

RDF knowledge graph data for [tox-dev/pyproject-fmt](https://github.com/tox-dev/pyproject-fmt), parsed by [repolex](https://repolex.ai).

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
rlex download tox-dev/pyproject-fmt
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 50e0f3aee9dc5747a5f173f79a7417403c18dda6
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 50e0f3aee9dc5747a5f173f79a7417403c18dda6
│           └── chunk-001.nq.gz
├── blob
│   ├── 047972fcdde5db2fc981195c8fae3b4fa980c05a.nq.gz
│   ├── 2eb1baacae6449244c918ef482e3b60c15e49c8d.nq.gz
│   ├── 364982344fbd94d55705e1f27a9a87abaa255333.nq.gz
│   ├── 3b342c935ea92dbdc3878247111a19a037400a69.nq.gz
│   ├── 3f7d6ddd7e1edfe85841e211b6e340a54b95401d.nq.gz
│   ├── 4425c229252139bd2641fda4badd61ca3cf27f6c.nq.gz
│   ├── 5f89818f9e63c2f6829c7706c57f223cdb5bbd38.nq.gz
│   ├── 6672d106fecd2c5fb42c492c6c1c761589a81a02.nq.gz
│   ├── 69d0cfd202c019ca1d5a92d59faf9a1380c61930.nq.gz
│   ├── 75b94899d666ab2d3cfeb69e95c2114765b443d1.nq.gz
│   ├── b2718e6e1bd5b4e76f42ba2008a7ab56bd6a1ae8.nq.gz
│   ├── b6ea0a249c1e0a4eb68615a3feae5824fb9fe1b3.nq.gz
│   └── e88ba89babca6b19cbe5f1582aa52dfc6f2cd6b8.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 50e0f3aee9dc5747a5f173f79a7417403c18dda6.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 21 files
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

[tox-dev/pyproject-fmt](https://github.com/tox-dev/pyproject-fmt)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*
