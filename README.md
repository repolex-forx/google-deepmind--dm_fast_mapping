# Repolex Knowledge Graph of google-deepmind/dm_fast_mapping

RDF knowledge graph data for [google-deepmind/dm_fast_mapping](https://github.com/google-deepmind/dm_fast_mapping), parsed by [repolex](https://repolex.ai).

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
rlex download google-deepmind/dm_fast_mapping
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 6045a1d450e8f93e60b427f7b0b5b0485ba7919d
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 6045a1d450e8f93e60b427f7b0b5b0485ba7919d
│           └── chunk-001.nq.gz
├── blob
│   ├── 1b57aa0e08265c0ac0ba9347eca1523d92075c42.nq.gz
│   ├── 45dbf26790a711045b0b695159fc3dc256b284e8.nq.gz
│   ├── 59edce7885bb041f7998f92bad1b5620a73d5c45.nq.gz
│   ├── 9a86ba025d83dfc39db62d84ee7cac0a9da1ac08.nq.gz
│   ├── 9e56f96d841bfad2cfc5fde609eb7557d6bbd81a.nq.gz
│   ├── a5c6f77fdd56fddbbf478b74bb4cc0342f0cee37.nq.gz
│   ├── ae2dab5dd9b01208564803cfb4fa49e316145060.nq.gz
│   ├── b4989cbb2a07fb8e9c304c362e09371d7dd8ccd0.nq.gz
│   ├── bc4036187f8bb41bae5bec0f1fa8a2686d503db6.nq.gz
│   ├── cc734b2ee01232e5e9fd1e80caa725c5a6722a63.nq.gz
│   ├── d645695673349e3947e8e5ae42332d0ac3164cd7.nq.gz
│   ├── f9fdc62960d5c67eef0590a70b14e7e112fc421b.nq.gz
│   └── fc0206b2a6965a905fe942771c65d3e7836f8808.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 6045a1d450e8f93e60b427f7b0b5b0485ba7919d.nq.gz
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

[google-deepmind/dm_fast_mapping](https://github.com/google-deepmind/dm_fast_mapping)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
