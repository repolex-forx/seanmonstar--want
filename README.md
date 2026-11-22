# Repolex Knowledge Graph of seanmonstar/want

RDF knowledge graph data for [seanmonstar/want](https://github.com/seanmonstar/want), parsed by [repolex](https://repolex.ai).

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
rlex download seanmonstar/want
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 6e65401c71fa55c75b6fb52f595a692ef3643939
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 6e65401c71fa55c75b6fb52f595a692ef3643939.nq.gz
│   └── repolex
│       └── 6e65401c71fa55c75b6fb52f595a692ef3643939
│           └── chunk-001.nq.gz
├── blob
│   ├── 0e33387345198547db2e7197b6a3ac3d31813a31.nq.gz
│   ├── 5acca6b1acfd7a827fd01eeb1ba2ec0ddb0b8fbc.nq.gz
│   ├── 96b29203940d9f055138cc76ad902f96474e92bc.nq.gz
│   ├── a821aa99219c8f82c6020ae2ff58bcf9ec6eac7b.nq.gz
│   ├── bd71b52b6977cabc9a72e9d69dca5831c95b53fd.nq.gz
│   └── e0f0f8ac7689d49f7c67f7c36e92e401bc0e55e6.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 6e65401c71fa55c75b6fb52f595a692ef3643939.nq.gz
├── filetree
│   └── 6e65401c71fa55c75b6fb52f595a692ef3643939.nq.gz
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

[seanmonstar/want](https://github.com/seanmonstar/want)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
