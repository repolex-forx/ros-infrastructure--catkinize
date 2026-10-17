# Repolex Knowledge Graph of ros-infrastructure/catkinize

RDF knowledge graph data for [ros-infrastructure/catkinize](https://github.com/ros-infrastructure/catkinize), parsed by [repolex](https://repolex.ai).

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
rlex download ros-infrastructure/catkinize
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 11d660c52f6a4b42483904d93a6d7326aa564b7a
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 11d660c52f6a4b42483904d93a6d7326aa564b7a
│           └── chunk-001.nq.gz
├── blob
│   ├── 0447782357d8817e7b91447d277e4ce024808cf1.nq.gz
│   ├── 091d84ce65dde7db95e2eaab1282503008e910ee.nq.gz
│   ├── 0d16e53e5301986893aee7a7fcfd4d6c32eeb452.nq.gz
│   ├── 1f837a3860e3d55a68066661298f52f71de4c46d.nq.gz
│   ├── 2aaccad9c4d19ed663499119d76efaa8f3b826aa.nq.gz
│   ├── 2be15a28c240e4005030453f5109d6d62d569d7d.nq.gz
│   ├── 44209e82b542fe5ae9d40d89134ccb2049223a29.nq.gz
│   ├── 5dbb437045b87eab43c5b544fb9878f495761eaa.nq.gz
│   ├── 64d3a44e81d8489ac562323cb6b4178922fcd71b.nq.gz
│   ├── 6f383e0dece2014d63755d6be086fe0c660f2c0b.nq.gz
│   ├── 7337daabf82969253aff327cf710f4b40114b71c.nq.gz
│   ├── 84dacb43c71963e4de6d9b184f22d304769a7fcf.nq.gz
│   ├── 9f1525256f5784b376656d0fa659e2de9b2f8799.nq.gz
│   ├── a83e370f328ed81dab3858504d74264917ae733e.nq.gz
│   ├── bd2006fff762a9e517deb6b94de3b7f49d91779b.nq.gz
│   ├── c2b1f391a7b9c0716f38bbe570456d71d5d17db7.nq.gz
│   ├── d6868573f4f6b7ad4d5bb121eabc8e201a695bdd.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── f52e80ba78ee699552d87f2af9a614c80ea3e757.nq.gz
│   └── f87a7b6da640ec0fcc60a229e5c0434c02aaa1b4.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 11d660c52f6a4b42483904d93a6d7326aa564b7a.nq.gz
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

[ros-infrastructure/catkinize](https://github.com/ros-infrastructure/catkinize)

---
*Parsed on 2026-10-17 by [repolex](https://repolex.ai)*
