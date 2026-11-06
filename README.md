# Repolex Knowledge Graph of sphinx-contrib/feed

RDF knowledge graph data for [sphinx-contrib/feed](https://github.com/sphinx-contrib/feed), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/feed
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e6668841bc91dd2f093fb8feece14805aa371397
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e6668841bc91dd2f093fb8feece14805aa371397
│           └── chunk-001.nq.gz
├── blob
│   ├── 04c9b843f5963b1b5f235cf8488869a351412b97.nq.gz
│   ├── 15050046f63f9c6b93e75fcbb24af4ce590d0d77.nq.gz
│   ├── 22262446d0aa9b328cf99d5cec599a1c51b02836.nq.gz
│   ├── 2a0bb7828573382e963fed034dfa466cf4bce144.nq.gz
│   ├── 2b8d42f96e01cd7117a9bd4abfcb74cac8ada662.nq.gz
│   ├── 2d74c58f248790e34e482eb07e20ec6c753c9d2d.nq.gz
│   ├── 3652963542f53a08fe9e38cc2741ea1522334c1d.nq.gz
│   ├── 45dd5f5b51e10661a6b6699e050c4ab23d721804.nq.gz
│   ├── 4d1876e0e93a5fb0f685e9d1632e3a44c6ea5d0e.nq.gz
│   ├── 4e070cac38c39ef08e60368e7f834f82086e3000.nq.gz
│   ├── 5323b6e654440871a66a12bff67483dd4e45f844.nq.gz
│   ├── 6461dddb2f01bddda5b7ae59cbb02813123f27b5.nq.gz
│   ├── 725da38de0747a26dc9820e5b2b523d59ffde89b.nq.gz
│   ├── 77d2a8ae9426b368a8e8a8a07c35ef2d5c4e4664.nq.gz
│   ├── 801c026de1c4a31af0b74b1e24ae59c55e6b7a6f.nq.gz
│   ├── 949d81994db666615c7dd385e304f07316d55b1d.nq.gz
│   ├── 9c5de4e7085c9bb3b79e24cddb24f9826737dc0c.nq.gz
│   ├── a30a287b235f262cfb1f825318109f36869a86c9.nq.gz
│   ├── ae366770ed24b2ef7accaf50d1b2f35187c50d4c.nq.gz
│   ├── b5a7dc29ef0f7f3593b1c61cfc5dfe8a17d3918c.nq.gz
│   ├── c8f7c53c089bf89e2c2c58f124ea16f5e5603a2d.nq.gz
│   ├── de14b62ccb6ab3150e3d8ca612ce68600c677422.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── e8929095afa86281eef1802310f88792d4df65fe.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e6668841bc91dd2f093fb8feece14805aa371397.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 30 files
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

[sphinx-contrib/feed](https://github.com/sphinx-contrib/feed)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
