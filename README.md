# Repolex Knowledge Graph of canonical/mimir-k8s-operator

RDF knowledge graph data for [canonical/mimir-k8s-operator](https://github.com/canonical/mimir-k8s-operator), parsed by [repolex](https://repolex.ai).

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
rlex download canonical/mimir-k8s-operator
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 4b433bb56fd4e1d29b9792617ad36f65c8c5711e
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 4b433bb56fd4e1d29b9792617ad36f65c8c5711e
│           └── chunk-001.nq.gz
├── blob
│   ├── 0163e01691f15c27629619651e8c63ea4991bda8.nq.gz
│   ├── 05e6a486e9dc870f0d5b8456be6d70c92b603ba7.nq.gz
│   ├── 09d7df9bc0581e77652b189699745ef308533aa0.nq.gz
│   ├── 0a99d40e656c12163b39f4d161664e97b83d451b.nq.gz
│   ├── 1080b5fdd1f576db4591a0491fde308ecdc0a212.nq.gz
│   ├── 1147b2dafd48229b4334cb473ddd02aa0ab1a1d9.nq.gz
│   ├── 17f478ac61fac561659203f04e9a4e0a815d5c4c.nq.gz
│   ├── 193192fe136241511631c1f5e4223822deeda24f.nq.gz
│   ├── 1e6e2de4406e23105a5361a27e49b9cf4c2c7bc4.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 2c32de336bf198c61b85f4f25bd12abbf103cca9.nq.gz
│   ├── 3d8f7803b31dc2ad051e172041b74a5137ddf473.nq.gz
│   ├── 46b56bcdfbd1316f2876bcd98ac7ba7aa6939932.nq.gz
│   ├── 5308222f200624889dd9ebf15ddff667654534a2.nq.gz
│   ├── 64dd13ce19d54b1fc22edb667c02d4f9f80427a5.nq.gz
│   ├── 6bce6a4485c2019639df5cdea0db7dffab21e426.nq.gz
│   ├── 77314e3e0274c5557db521e31cb57e1308852bfd.nq.gz
│   ├── 7b49138748deec1d89900002b11da27304d36c34.nq.gz
│   ├── 7d53740cfc50ed71fa596c04561fbaf7ae26596b.nq.gz
│   ├── 7e088d46e8e6898dd2fff4007e22c1c299c35adc.nq.gz
│   ├── 84079bab5e49494d850515d5a2ce692681d2a93d.nq.gz
│   ├── 9f27e2a89e84cd46798e9b0344715554c23442a2.nq.gz
│   ├── a79e5d4343e09bc07819c1a444ef89d509067388.nq.gz
│   ├── a9c6f4fea73034146ec566dad61c36313dc91692.nq.gz
│   ├── ae2389def4a2ec2427e2a02d9c5df075ac686617.nq.gz
│   ├── afb45b73f2f044c8c3a1158f7ca35f6038210d82.nq.gz
│   ├── bc5701da1ac32f76244e6a946061c54b3f9f72e8.nq.gz
│   ├── bc84e5b786b0c000c724eb468ac51c8450407871.nq.gz
│   ├── bd1dd6fae8283897ca91ec87fec743d5ce7da62c.nq.gz
│   ├── c27b7193938162795d7e965a4cb7b78e266bf2bc.nq.gz
│   ├── c35c64abc2c16f0747a861a2bd1fb59bc1ffdf26.nq.gz
│   ├── ce534727372c95528ae693946f4d9f11be343914.nq.gz
│   ├── cf7c2e22a3f06bc9db4db556d5ae924b296a22aa.nq.gz
│   ├── d125d88ca0572d7ccce197494a624986448f5478.nq.gz
│   ├── d16e8785cc940bf7b4581baf37ad53302caedd87.nq.gz
│   ├── dda14d51c1991dd6751852b15f631a48f54fea07.nq.gz
│   └── edc4e82f5dc82b6e13ee02401d3ebfd8d85295d5.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 4b433bb56fd4e1d29b9792617ad36f65c8c5711e.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 44 files
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

[canonical/mimir-k8s-operator](https://github.com/canonical/mimir-k8s-operator)

---
*Parsed on 2026-11-08 by [repolex](https://repolex.ai)*
