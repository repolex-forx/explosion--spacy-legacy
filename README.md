# Repolex Knowledge Graph of explosion/spacy-legacy

RDF knowledge graph data for [explosion/spacy-legacy](https://github.com/explosion/spacy-legacy), parsed by [repolex](https://repolex.ai).

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
rlex download explosion/spacy-legacy
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4ccfdb78d417ea14ae3653bef643d53ee0953928
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 4ccfdb78d417ea14ae3653bef643d53ee0953928
│           └── chunk-001.nq.gz
├── blob
│   ├── 0506b4d29cd0330612c44be3a8cd8b9852680b62.nq.gz
│   ├── 053018553b636e5c030236b0415dd40936e57db4.nq.gz
│   ├── 08aa3cec792274887ce4ecc610282958d28ad428.nq.gz
│   ├── 1386499172bd7595e583edf9e375cb98c9471b81.nq.gz
│   ├── 300bc9bee7f4f4635e956af657481b7473ebb1f2.nq.gz
│   ├── 3af8060dba870aac31bba2badb5c2ad1f3847bbc.nq.gz
│   ├── 3e672ec9c7018aebe8fcdbfc539d90fe06a9f416.nq.gz
│   ├── 40a4b3353cfeb839971959b8fbd722712f826678.nq.gz
│   ├── 4350174cf9f66ebf628b484903b6fe34d73ff69b.nq.gz
│   ├── 457b95db09b8929d7f427653dac5ad97a01ff5cd.nq.gz
│   ├── 4731aa6d8a44cf2e8200a797ec3673ea4ec32032.nq.gz
│   ├── 6d35f6860fe49503e3f58bf030e292e39afd50db.nq.gz
│   ├── 6f20c75384f66ad02f282c2d9aef25610ed80814.nq.gz
│   ├── 6fe2cd952d2371a44bcd755af25c8ddeb706012a.nq.gz
│   ├── 72629b910ace9c9f9bab1b90d39dbc5e043409b7.nq.gz
│   ├── 8d4f0ae6632919a823fb9f3b7cb8955f25951619.nq.gz
│   ├── 956474cb31b7b0d927a8f4ae0afc4902d7241a93.nq.gz
│   ├── 9a10ebcc0b6b530ba93f08b8d1d5a5160ef870da.nq.gz
│   ├── 9f8cdad91a3a03feb5a826c81a72b451fb94973e.nq.gz
│   ├── ae421f026f43fcfa265ed85b9c1b54c1538aced0.nq.gz
│   ├── cc9e0151c67a62399e56b8088610ccfce6090084.nq.gz
│   ├── d1205b2f37536a3cd3d2907d3b0e6a003cc4f079.nq.gz
│   ├── d2ef6bc1e71b6a5700981d281a4db86a983333ba.nq.gz
│   ├── d87d0829f942d6bfabb48cb6e5141b0847d079d6.nq.gz
│   ├── d9663da179d2ae8c16f41c0d1742535229dadafe.nq.gz
│   ├── de1de1b73335ea481348efa88ec6fa1ba08ac8b6.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── f3fae66dd089ec8926a9726a745d47bf63a5d0b5.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4ccfdb78d417ea14ae3653bef643d53ee0953928.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 35 files
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

[explosion/spacy-legacy](https://github.com/explosion/spacy-legacy)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
