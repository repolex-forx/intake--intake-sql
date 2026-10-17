# Repolex Knowledge Graph of intake/intake-sql

RDF knowledge graph data for [intake/intake-sql](https://github.com/intake/intake-sql), parsed by [repolex](https://repolex.ai).

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
rlex download intake/intake-sql
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 052cde14156fa2077655d0fc6115e11c2e9f4174
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 052cde14156fa2077655d0fc6115e11c2e9f4174
│           └── chunk-001.nq.gz
├── blob
│   ├── 02f0e7baa25ef2410a68479543e96ce0c8b9ebc5.nq.gz
│   ├── 1385d9ba190b0ac82a8e067f99c19c841d6680de.nq.gz
│   ├── 1680bb8c009a3d44724bd5aa912bfc74c3d334b5.nq.gz
│   ├── 17834ea2e83b299aa3143b24462eef4c6cfbf0a5.nq.gz
│   ├── 273216e92a2cb8378e05d2db61fecdb3b2a5539f.nq.gz
│   ├── 291261ba523eceacdefe19f35db74ce297f51a91.nq.gz
│   ├── 2b0afd2bc17e49d771c07d911c46737570aef1f4.nq.gz
│   ├── 3fa96c3b2c5b2590efdd6cc734730c5a7211fdce.nq.gz
│   ├── 411936e186d997a128a6e38de2f5e471f2f05edd.nq.gz
│   ├── 46dd3f6039067b34cc4be5ed319342d6c8f4db70.nq.gz
│   ├── 4c557ed842143e3cd329d09c349b421c52af44ee.nq.gz
│   ├── 5468db1217f5550b54afdb4fa0bf2ba374704aae.nq.gz
│   ├── 64fea1c892723b9db5bda7d302168b6128e14bf5.nq.gz
│   ├── 764bd37be6ccb25e1b8d8bae20538d05d8cea461.nq.gz
│   ├── 7eb25846d9742d01ece93fbc3704eac348ec1ce9.nq.gz
│   ├── 81f543580d2837256b18420699f56e9dde99444d.nq.gz
│   ├── 883cc08b5c6e6446aca5879c0482ca9755cad958.nq.gz
│   ├── 8b57024645bd55fb5dde9bf527a86a5b5d8a119a.nq.gz
│   ├── 9f39777239f0e1ea61b273a869a545963940d3de.nq.gz
│   ├── ad5584078971c96b8f12b9b2ab15a9b1319649b3.nq.gz
│   ├── bbc05033ce37a32947615c9140c483129ad700ac.nq.gz
│   ├── bfa872f08ae43e2dea652d19fda6318e084e7652.nq.gz
│   ├── c654edfeba07e006d2b2042ee8bb6f9cfb25cad9.nq.gz
│   ├── cc817ee74050ed37982ee877f8049fc0210e7b97.nq.gz
│   ├── d8007cc849a30583edd60feda40555adc60a2223.nq.gz
│   ├── e28507017d45405a8288fb80a5c594e06d8e5cce.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── ebbbcf51812a73b5d405e7f5c2f2d9e38ff64dfc.nq.gz
│   ├── f62f3ea463b9c82cb061c7e370f3ecdbfdeccabe.nq.gz
│   ├── f6800904950639077ee238ea1ad7d635d5ae6473.nq.gz
│   └── f8a055c38af43bb18f9455ab5c1813e3b567d80f.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 052cde14156fa2077655d0fc6115e11c2e9f4174.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 39 files
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

[intake/intake-sql](https://github.com/intake/intake-sql)

---
*Parsed on 2026-10-17 by [repolex](https://repolex.ai)*
