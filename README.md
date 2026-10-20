# Repolex Knowledge Graph of coleifer/dot-theme

RDF knowledge graph data for [coleifer/dot-theme](https://github.com/coleifer/dot-theme), parsed by [repolex](https://repolex.ai).

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
rlex download coleifer/dot-theme
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c8c97090672ccafcb696dd8b2fc8867260969a34
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── c8c97090672ccafcb696dd8b2fc8867260969a34
│           └── chunk-001.nq.gz
├── blob
│   ├── 01c5c612751cc969a3d7b8d4e8544fd6f1c6e944.nq.gz
│   ├── 09a5972c983ba4405c168bbce0d67a369e08dbaf.nq.gz
│   ├── 140b1219aa63befcccf1b1a1043321567f03d21d.nq.gz
│   ├── 3b802215c3d439f97dad2e1f69294e657cbd3afc.nq.gz
│   ├── 68ab6173b3994d4edd0d25a62622b5953534115f.nq.gz
│   ├── 8678cf036ec86b77d01003f26e4ca387b70dbac4.nq.gz
│   ├── 8cbf20cda4e1691516a5d808e1ccd9961cbfb659.nq.gz
│   ├── aa19a577100fba12672f45987a573d518b8b712b.nq.gz
│   ├── b10cbdb8221072ddf78cbbf0f85208bedabeab70.nq.gz
│   ├── c3b213fce76e0c59fe5d9c2f0cdca260e2f97153.nq.gz
│   ├── c752ab3ead2e7be324e5cafb5e1d53135c16af13.nq.gz
│   ├── ebe91a948ba6b5e4e6235ef4ebcf9cfafe3e034c.nq.gz
│   └── f2065e494090d5eda951f6a8a9f7743833292bd7.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c8c97090672ccafcb696dd8b2fc8867260969a34.nq.gz
├── issue
│   └── issue.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 20 files
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

[coleifer/dot-theme](https://github.com/coleifer/dot-theme)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
