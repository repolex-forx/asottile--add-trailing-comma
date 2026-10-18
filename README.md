# Repolex Knowledge Graph of asottile/add-trailing-comma

RDF knowledge graph data for [asottile/add-trailing-comma](https://github.com/asottile/add-trailing-comma), parsed by [repolex](https://repolex.ai).

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
rlex download asottile/add-trailing-comma
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4aa21034cf9e0aef19376abd3922943400b16ee1
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 4aa21034cf9e0aef19376abd3922943400b16ee1
│           └── chunk-001.nq.gz
├── blob
│   ├── 0f4f1708847c3280040a8d84634cd833fa362212.nq.gz
│   ├── 11af89c03049d234016aebaec104a01db4852c24.nq.gz
│   ├── 20799c76eed95e09eb52065600d2665f7586af19.nq.gz
│   ├── 2362c32a9171531b06634a611280cf27a327e160.nq.gz
│   ├── 264db608586ce8d5ccc18bf9ea08c56675030386.nq.gz
│   ├── 2bbf4c013632b2fb6462f323d78000454ca85602.nq.gz
│   ├── 2dced5f8fd2c0b0943e9044ad01e5de7cb49b967.nq.gz
│   ├── 2e4af744edcac7d433847a74f81658ecae185828.nq.gz
│   ├── 3d93aefb2da505dba9c0114404cfaaeee5ad0d3f.nq.gz
│   ├── 3f91b5a81edcf7adc03b8765b3b5d8ddef52d9fd.nq.gz
│   ├── 3f97109be3a512da33163a0cc97533ba4a0f895f.nq.gz
│   ├── 4c0682117a051c4d8af6b98e83d88a0c906459e6.nq.gz
│   ├── 4d2378db58d5be5aa7d1b248c327c72714077321.nq.gz
│   ├── 522fbe20b89911bb8d68b4a684a51225dd571764.nq.gz
│   ├── 5370c9485451439199ab7ab9ba30c95d9a046275.nq.gz
│   ├── 554b6cf913277ea0f832d0877ff6c30f35eeba20.nq.gz
│   ├── 5f07885b4d296b154beec03480cbe7566c33fc0c.nq.gz
│   ├── 632bcdf7ce994408aa751bd4b303cbf4c35e8a13.nq.gz
│   ├── 71b490fcdd9908d8d6025ef074b1934581c1d56e.nq.gz
│   ├── 7536c1f1d1ce3649e6d2be3ad153ea29596f4b50.nq.gz
│   ├── 86e33fe3a2ff17bde13064cfeeca838588220dd9.nq.gz
│   ├── 8b79cbd67474490732b065753890ca4160f25e15.nq.gz
│   ├── 8c38c3fa07daab3596dae959bfec1e3571868cb0.nq.gz
│   ├── 942803e7f366f779d99517ee93dd99d938c773db.nq.gz
│   ├── 9d0bec0157e71393ec6b38aba06198c3cbf69aba.nq.gz
│   ├── b1447c3015af9511f2dee402ca4b5ad62adf5dce.nq.gz
│   ├── b402feaae6a770d044a9839884c5ed81c36843a1.nq.gz
│   ├── b6be3981a9e68b238931c69cdf9ec1ee4e3d529b.nq.gz
│   ├── bfb22a9988330519f2e155b293ee14380b20c90a.nq.gz
│   ├── c7d496365acf24ae207b680861c6db5c55e3413c.nq.gz
│   ├── ca1d90ea180858ae143c0e62d920e350d3acc62d.nq.gz
│   ├── db6380c0fc92a8b6efa2cc384b2e107583b720cd.nq.gz
│   ├── df7c0e23babce2f5b771531102fe0a90043dc472.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ecfa69a1e3c086d55bee0f5cf98f7574228b85c8.nq.gz
│   └── f673d736463fed2c41f54bc042edbc9db5f07417.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4aa21034cf9e0aef19376abd3922943400b16ee1.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 44 files
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

[asottile/add-trailing-comma](https://github.com/asottile/add-trailing-comma)

---
*Parsed on 2026-10-18 by [repolex](https://repolex.ai)*
