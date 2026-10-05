# Repolex Knowledge Graph of NousResearch/smc-inference-server

RDF knowledge graph data for [NousResearch/smc-inference-server](https://github.com/NousResearch/smc-inference-server), parsed by [repolex](https://repolex.ai).

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
rlex download NousResearch/smc-inference-server
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4c5fade5ef89965079c5866ff302893227491e3d
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 4c5fade5ef89965079c5866ff302893227491e3d.nq.gz
│   └── repolex
│       └── 4c5fade5ef89965079c5866ff302893227491e3d
│           └── chunk-001.nq.gz
├── blob
│   ├── 0582420b718635426cb4e5d82e2dbd2ca0a8769d.nq.gz
│   ├── 1680faf1de82734e1765c0b34fb41cc03f2051b1.nq.gz
│   ├── 296bb61ae97abad2e512e66b7a271550d259406a.nq.gz
│   ├── 429fb25b7615c923a6e3abe990c342805d84c6f1.nq.gz
│   ├── 4913224fd65fdcb871435376de1d0e706d2c90c9.nq.gz
│   ├── 6be0fbdb888a3b111ff4c58cc305693a1abdacde.nq.gz
│   ├── 6d4b1b2b758b25bc396b486d9e5a99c680160f4f.nq.gz
│   ├── 7d8e8dd8d359876f09fce8a1d664b0974b527926.nq.gz
│   ├── 7f314b78da20ddef791d45ab482a38330a7a61ac.nq.gz
│   ├── 80b122e710d6972c65c709d5028a268bc6abf091.nq.gz
│   ├── 8b37f0728cd29326bff9561a8739d229a89d1beb.nq.gz
│   ├── 8c274fa4e826d85c64768a457228839270219c98.nq.gz
│   ├── 917590770b6d2d93e5743caa477a7c37a11691f4.nq.gz
│   ├── 93c2219b9494fce612a23d3a23428905832e239b.nq.gz
│   ├── cf8af47996013be3ed3ddf2ffb4038f23852e942.nq.gz
│   ├── e40e67168f18f514de869ae213cc90d26b52f0b7.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e8c44df3c8d763febea33d1b8496777f11356d27.nq.gz
│   ├── fb58c4e4c53204625732f2fcc2ab3f29f9a9808e.nq.gz
│   └── ff92257e0fd0cd571c836314cc32e3734bffe97f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 4c5fade5ef89965079c5866ff302893227491e3d.nq.gz
├── filetree
│   └── 4c5fade5ef89965079c5866ff302893227491e3d.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 29 files
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

[NousResearch/smc-inference-server](https://github.com/NousResearch/smc-inference-server)

---
*Parsed on 2026-10-05 by [repolex](https://repolex.ai)*
