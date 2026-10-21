# Repolex Knowledge Graph of networkx/networkx.github.io

RDF knowledge graph data for [networkx/networkx.github.io](https://github.com/networkx/networkx.github.io), parsed by [repolex](https://repolex.ai).

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
rlex download networkx/networkx.github.io
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 61e6b94222e7d2ee3faa04552a79eb9b1cc1b7c2
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 61e6b94222e7d2ee3faa04552a79eb9b1cc1b7c2
│           └── chunk-001.nq.gz
├── blob
│   ├── 01192852b5c92c13a1cb27c0d2f84aee037691bc.nq.gz
│   ├── 210ec41998188ecd12366934372c4469106017cd.nq.gz
│   ├── 2fa8c97fe42aebc1d50251eca054fdc6b40ed084.nq.gz
│   ├── 35906b9293f7ae55f14a94d7d97d5d5df195550d.nq.gz
│   ├── 4e5626a2db8c34d7ff8c6ce95b669727cbbf4df9.nq.gz
│   ├── 5389d1225e80dc85683a8612a23bf74affc27399.nq.gz
│   ├── 5b3ebc5789c22327c45ef6906c7ee3394a774702.nq.gz
│   ├── 7223acc59557bc5e0d52522f99fc2769cd29c47b.nq.gz
│   ├── 76f75f986e9151cbb2a5a134368a94ec94ad5102.nq.gz
│   ├── a858a410e4faa62ce324d814e4b816fff83a6fb3.nq.gz
│   ├── bae50ba2a8d614394b328d3f594e813976f87751.nq.gz
│   ├── df99fd399c65f10fa72d12c98890030d1b439ac9.nq.gz
│   ├── e15812051ede887d5638b08472ec4660a78fc27a.nq.gz
│   ├── e6128ab2feecddf286db30dd4c9e9c198c796b9f.nq.gz
│   ├── e64dc8ebaf82c2edc21d1582dac41285f54fddda.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── f9f609622826ca055977013224b11a0508904f93.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 61e6b94222e7d2ee3faa04552a79eb9b1cc1b7c2.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 23 files
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

[networkx/networkx.github.io](https://github.com/networkx/networkx.github.io)

---
*Parsed on 2026-10-21 by [repolex](https://repolex.ai)*
