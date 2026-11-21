# Repolex Knowledge Graph of Kimundi/scoped-threadpool-rs

RDF knowledge graph data for [Kimundi/scoped-threadpool-rs](https://github.com/Kimundi/scoped-threadpool-rs), parsed by [repolex](https://repolex.ai).

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
rlex download Kimundi/scoped-threadpool-rs
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── d997df877268c254a49013f5c7ed005d04756a40
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── d997df877268c254a49013f5c7ed005d04756a40.nq.gz
│   └── repolex
│       └── d997df877268c254a49013f5c7ed005d04756a40
│           └── chunk-001.nq.gz
├── blob
│   ├── 1e9cfe782873eac61fdeab49414a6ee76daead24.nq.gz
│   ├── 3146fc82ba73966668ef7fba094c1e0430a320a8.nq.gz
│   ├── 9ac8f2a848c012744f820955538bda676cdb6906.nq.gz
│   ├── a9d37c560c6ab8d4afbf47eda643e8c42e857716.nq.gz
│   ├── b71b630dd9319fd878cf3e9c1177c313e28dc515.nq.gz
│   └── dff72d1e43251989d52b6bec53c8588f7f4df47b.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── d997df877268c254a49013f5c7ed005d04756a40.nq.gz
├── filetree
│   └── d997df877268c254a49013f5c7ed005d04756a40.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 16 files
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

[Kimundi/scoped-threadpool-rs](https://github.com/Kimundi/scoped-threadpool-rs)

---
*Parsed on 2026-11-21 by [repolex](https://repolex.ai)*
