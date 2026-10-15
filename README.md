# Repolex Knowledge Graph of jupyter/jupyter_kernel_test

RDF knowledge graph data for [jupyter/jupyter_kernel_test](https://github.com/jupyter/jupyter_kernel_test), parsed by [repolex](https://repolex.ai).

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
rlex download jupyter/jupyter_kernel_test
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5f2c65271b48dc95fc75a9585cb1d6db0bb55557
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 5f2c65271b48dc95fc75a9585cb1d6db0bb55557
│           └── chunk-001.nq.gz
├── blob
│   ├── 00afd2301e0dc852fe0f345fffe3ea58ff422528.nq.gz
│   ├── 12f2bb5fc6f93e52afdd10a6aa195600b59e81de.nq.gz
│   ├── 17d30ae58b16d482701ae9642c26000acae4aabd.nq.gz
│   ├── 2de09ce3f53c64bba1946276e081385e707e42f2.nq.gz
│   ├── 2f3954582a60ff3b34892a922a14b0710386ab46.nq.gz
│   ├── 35b7ff5be8d0e3880f2cc9858403ad283f3c0926.nq.gz
│   ├── 38cf9cb78df30887306409310dc1acabce6740f4.nq.gz
│   ├── 396330bb9729d2ec595617aef79fb28600d86bd7.nq.gz
│   ├── 5295e776b63d7adfab3ddad99962cc6f81968909.nq.gz
│   ├── 578539c418e33c0a9d699fe6b88d9612f4838ad6.nq.gz
│   ├── 5c30c242f6409485b6f60cdde9a44032dea23cda.nq.gz
│   ├── 60af4c5f16741c7c2fe17cdd9718ae5f6d56d8a4.nq.gz
│   ├── 725feab5ce652dc39f3f2c77b9fd3c90bf049c65.nq.gz
│   ├── 753edd7b5059c72cdd6cc37e623bd7c42de4afeb.nq.gz
│   ├── 77a8375b1fafacd5b59167881cab211a0625edbe.nq.gz
│   ├── 865e82d61bf7c843e2f7457a0fcc2542357218b3.nq.gz
│   ├── a4aa2d089a8ddc220dd21d9d5730f15b1b577c7f.nq.gz
│   ├── c46ce866d22c02d565058b96c929c8967ac2c8ed.nq.gz
│   ├── d4ec30eedb95c2649450abb04428c177ac22b727.nq.gz
│   └── fcdd3e88b66ec9b10362685146ef2a36088e54f3.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 5f2c65271b48dc95fc75a9585cb1d6db0bb55557.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 28 files
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

[jupyter/jupyter_kernel_test](https://github.com/jupyter/jupyter_kernel_test)

---
*Parsed on 2026-10-15 by [repolex](https://repolex.ai)*
