# Repolex Knowledge Graph of allenai/asta-theorizer

RDF knowledge graph data for [allenai/asta-theorizer](https://github.com/allenai/asta-theorizer), parsed by [repolex](https://repolex.ai).

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
rlex download allenai/asta-theorizer
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── c4802aa947128f1e49621d9a52891f612864716c
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── c4802aa947128f1e49621d9a52891f612864716c
│           └── chunk-001.nq.gz
├── blob
│   ├── 007fef05da150419686695548a72b4ccd7f21e1f.nq.gz
│   ├── 054d231bbd04a7423595947642e71951c1f4a731.nq.gz
│   ├── 05516a8f971aa9ef9eea28a9764222a64d5697ce.nq.gz
│   ├── 08a95acc20932e42cfd9b08f1a76b3b382b5a2eb.nq.gz
│   ├── 0d242e6ad660f36c79fc903a0ddd6185b552286c.nq.gz
│   ├── 1471d053e9acc25af83d0d6f1cdea708e8654931.nq.gz
│   ├── 170e97e8b43b7d2ea20e25d3e12d3cdd3424c36e.nq.gz
│   ├── 194ed1a22efc79aa5354becf721ad4b4ace39465.nq.gz
│   ├── 1a5d90c6b18d25bcd3018686f917c6b6735116e1.nq.gz
│   ├── 2604e01c71fd320a6199831ec72a5a275822bd54.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 3d38d8491dcd45b58d601d8b05235efeed829c53.nq.gz
│   ├── 3d92004cd45a03ea23aae33f0ae79b0f98c6de60.nq.gz
│   ├── 410a01b4c126a7b212bce37c9022f8e2fe7ca7bc.nq.gz
│   ├── 53fac159f281b271f3856ae04ab9a2e69dc86f71.nq.gz
│   ├── 5457d447f28fe39ec48e73a098c477aa29b11abe.nq.gz
│   ├── 70abb9487f95c9cc89837ea41d67e31e5c4e38e1.nq.gz
│   ├── 71dddc11dd23b36e416600de4fe8bb13b8443a67.nq.gz
│   ├── 72259d7707546d5686f215899018ce8cd5d0d4c6.nq.gz
│   ├── 7640abc2bb29c736a38b295a6a31fa456a92f99e.nq.gz
│   ├── 8086d8f4dd50da46d6338ec83415c7a5c017889c.nq.gz
│   ├── 859b3aee197b161fa3f8a805692fa4d7b738260f.nq.gz
│   ├── 8863c7af5dd0f1f634439f17b06870824f1d04f3.nq.gz
│   ├── 8b219e6397f2416dfa44c89c18ed6557841e1f99.nq.gz
│   ├── 931b63692141eebe8b4b2d0a993b5476ccda0f62.nq.gz
│   ├── 96a03d19dfa910971254b39904952e11abe8b8f8.nq.gz
│   ├── 99b483987305de338a512a0c1a75ecfa675e3d4b.nq.gz
│   ├── 9a80f0f5b780e3f0e7e47e1d95f7da4cadfc8767.nq.gz
│   ├── 9cbcb6eab5d68d8918b549bc361518e018dc7932.nq.gz
│   ├── a17b70c152f541296df9e86c18eccc6528e5a750.nq.gz
│   ├── ab9dac61ce062d2e93328d80093a97b2ac56fd65.nq.gz
│   ├── ba7b9046ce32909f64290d67c6f654b2e67f42be.nq.gz
│   ├── c1b5846d9797b9b641d896748c1c70024c1cd463.nq.gz
│   ├── df1061d787bdf346e2ea1a911e8063f778fdd703.nq.gz
│   ├── f445bc004c37720a8461733a46429a452211d1bd.nq.gz
│   ├── f5d46a5e9f1420e911bee7a9be01d106c750c02e.nq.gz
│   ├── f9fef1937936207ba5fa23954359486001e5eff6.nq.gz
│   └── fc200cc44d7ba2858c107483f07078333f9a1689.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── c4802aa947128f1e49621d9a52891f612864716c.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 46 files
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

[allenai/asta-theorizer](https://github.com/allenai/asta-theorizer)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
