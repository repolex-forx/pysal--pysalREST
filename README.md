# Repolex Knowledge Graph of pysal/pysalREST

RDF knowledge graph data for [pysal/pysalREST](https://github.com/pysal/pysalREST), parsed by [repolex](https://repolex.ai).

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
rlex download pysal/pysalREST
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 6ef0e96151475018ac60953bba85822f7dbb33a8
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 6ef0e96151475018ac60953bba85822f7dbb33a8
│           └── chunk-001.nq.gz
├── blob
│   ├── 1f86a12ac79f504bc64760895384afc4c6d45516.nq.gz
│   ├── 24da5d5dcb0c3e23c2c675d36a584c229c1878de.nq.gz
│   ├── 3fee16c295549e7098e71c4c1da5be7db57680ad.nq.gz
│   ├── 4368cab14b8dd0a73f5639ed6a1c9ef3a5f4c07f.nq.gz
│   ├── 4897e1beab2a4fa23fc51600054f03a4a6ef873d.nq.gz
│   ├── 4b3cc8b04f408439427ece3c61d67e379fe056fa.nq.gz
│   ├── 53caa56705fd8240aad983b3921f76b5d28de5da.nq.gz
│   ├── 54b187694c7920814803e946d25a4f303a46d1ec.nq.gz
│   ├── 5cd697ee7155e47a295479f7ea351d2a054b1d2f.nq.gz
│   ├── 729c84ff4795563c6d9a39fa5e51710c9dc28829.nq.gz
│   ├── 7623bf26aecd9c25901909885bb6a59232c65491.nq.gz
│   ├── 8b915e4a8d2964847a91b016fd5fb242826c4a45.nq.gz
│   ├── 8e554f1e634f9b8260b131f6512769528a26babf.nq.gz
│   ├── 8ef9a84601513d8179f7cce72ad05d2fa1e9538a.nq.gz
│   ├── 928c93b5ac73d2ad9fdafac85998293c355b5108.nq.gz
│   ├── 95cfe0742bbc8b5fa8e8b4c355b0b2b95dcae036.nq.gz
│   ├── 9649e6138f7ae35577dddd3a2e122f2c97e925f5.nq.gz
│   ├── a54b5d84b74e0be5ba056e28228e175e8714429c.nq.gz
│   ├── a9465880fd6b7f6be96b19859c789fd2991a4a1a.nq.gz
│   ├── aa5e0fd70652404abe366ca78f178dc46d56d04b.nq.gz
│   ├── b7440876f0bda14ae16dfab474127ab7e0d8d252.nq.gz
│   ├── bc1851dc1970e26f7ed893fbed4c5e8e16484307.nq.gz
│   ├── bc3510f322149460a8ba05b35d714fc5cd3fda85.nq.gz
│   ├── c0254e0b6d24e7aace16e8e09b9f0733a851f0c0.nq.gz
│   ├── cce81805f557370ace1f9f835d239b2e5a41abc0.nq.gz
│   ├── d96667d03e24b427f30c062c6387da5655e85b99.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e9cb0cf6e9fc880cb6c0569bd7862821d7309bb2.nq.gz
│   ├── ed1b07a725de49e2efb2e7142bca484b3ec49c3b.nq.gz
│   ├── f11724a06f66d452c34230c55c888f3e0509dac0.nq.gz
│   ├── f98ac5d4de8e71e849c4bd707866e2a07c7f0aee.nq.gz
│   └── f9af8aeee8be7669008edfd9140e01c300be4ee4.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 6ef0e96151475018ac60953bba85822f7dbb33a8.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 40 files
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

[pysal/pysalREST](https://github.com/pysal/pysalREST)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
