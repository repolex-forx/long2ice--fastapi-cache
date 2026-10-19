# Repolex Knowledge Graph of long2ice/fastapi-cache

RDF knowledge graph data for [long2ice/fastapi-cache](https://github.com/long2ice/fastapi-cache), parsed by [repolex](https://repolex.ai).

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
rlex download long2ice/fastapi-cache
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b2143ef85e2868dace363e432a0683675577bf81
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── b2143ef85e2868dace363e432a0683675577bf81
│           └── chunk-001.nq.gz
├── blob
│   ├── 156a3e6346973e97437e7a42bb41869e1ee53422.nq.gz
│   ├── 179cd2144add2603bf2195569e828580770d5817.nq.gz
│   ├── 1a4ea71d997e1aa1d48feb8b0955a55c56843468.nq.gz
│   ├── 1c85203b02e7204fafdb28f11bc2427f69120bbc.nq.gz
│   ├── 23bd0a547b8e1fa014e33b985e7fb6c74d4951f8.nq.gz
│   ├── 2d606a05443db812e32f89e2cfa4683524641750.nq.gz
│   ├── 3bbd29ac64c99749d05ff4c470eb3700baeda63e.nq.gz
│   ├── 49b4c049dc4363e867a8a239a0122e09f39cc2c9.nq.gz
│   ├── 4f6a4dc5df1ec8ecb93bd74fca59f6e61de3b49b.nq.gz
│   ├── 52949d68fdbb93b309e92735f4550dd3dd692851.nq.gz
│   ├── 551746ea864d40f6d8fa11daa305ccae20ddad64.nq.gz
│   ├── 5eef48f4835f21d2495c47a721e60c07d838d72e.nq.gz
│   ├── 5ef101b863695e9b02cebdec52024a1866fab9b1.nq.gz
│   ├── 6352077236fddc201f7a315cba4a7eff0285f179.nq.gz
│   ├── 644c182173e36b9560d1d6b0eeb0b24d88789d18.nq.gz
│   ├── 6634c4f67fdd431e460d8ba2be2a88928a64e35d.nq.gz
│   ├── 79aab8689aca5fbd3375930eeb0d7e7fd8a44aba.nq.gz
│   ├── 7df09e88fd4c69a90ced413d0c75f50595e4a0f3.nq.gz
│   ├── 8075b17976af1206b959a5abdbbf48053bd33e78.nq.gz
│   ├── 88d19a80b684e53b71d9b21872a04b51a758d2c5.nq.gz
│   ├── 9d8f36f94ff039dbde6b72cb22d786044ec13f7d.nq.gz
│   ├── a12484907accc66a30197c30c1aff91a27124431.nq.gz
│   ├── abd6390f23f9a424b3b56098e90a11fee999599c.nq.gz
│   ├── bd21407c223dd4d7b92b81333b8db05ab12cddbb.nq.gz
│   ├── ca8e54ae8a1678cb24dc6ee8dac90fdcdd6f5bcd.nq.gz
│   ├── d49f4fdfdc5d60d01ac83166cb54bab189875639.nq.gz
│   ├── d7b6b6bd6f3e07eba27d555c8698f8f850c7c135.nq.gz
│   ├── db79b1aa6684a9693068d1b5c0b263a6928b7e4f.nq.gz
│   ├── df1640f23b6cd46cef193f37f2eb7b11b2b46675.nq.gz
│   ├── dfe735156860f13ef3ebac9b6335a630f661b6b1.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ec639d1a064f835b04650524e4afb6d3c79d43c9.nq.gz
│   ├── f4de1a0ba11eda6d0150e5875347c4b6176db93c.nq.gz
│   ├── f551bc3aa629ce1dd24d42602c2021383f5535ec.nq.gz
│   └── feee3a63512b6d1c4a0008af334638d5ac42c03c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── b2143ef85e2868dace363e432a0683675577bf81.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 43 files
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

[long2ice/fastapi-cache](https://github.com/long2ice/fastapi-cache)

---
*Parsed on 2026-10-19 by [repolex](https://repolex.ai)*
