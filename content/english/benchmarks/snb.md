---
title: "LDBC Social Network Benchmark (LDBC-SNB)"
aliases: [
    "/benchmark-snb/",
    "/developer/snb"
]
type: generic
---

The Social Network Benchmark suite defines graph workloads targeting database management systems.
The benchmark suite consists of two distinct benchmarks on a common dataset, since there are **two different workloads**:

- **Business Intelligence workload** is focusing on aggregation- and join-heavy complex queries touching a large portion of the graph with microbatches of insert/delete operations. Its data sets are available in [Cloudflare R2](https://github.com/ldbc/ldbc_snb_bi/blob/main/snb-bi-pre-generated-data-sets.md).
- **Interactive workload** captures transactional graph processing scenario with complex read queries that access the neighbourhood of a given node in the graph and update operations that continuously insert new data in the graph. Its data sets are available in the [CWI/SURF data repository](https://hdl.handle.net/11112/e6e00558-a2c3-9214-473e-04a16de09bf8).

Each workload produces scoring metrics for performance at the given scale and price/performance metrics.
The Full Disclosure Report (FDR) further breaks down the composition of the metric into its constituent parts, e.g. single query execution times.

The [LDBC Social Network Benchmark specification](https://arxiv.org/abs/2001.02299) (including the latest and earlier versions) can be found on arXiv. If you are interested in getting audited results, please reach out at info AT ldbcouncil.org.

### SNB Business Intelligence workload – Audited results

| **SF** | **Power @SF** | **Power @SF/$** | **Throughput @SF** | **Throughput @SF/$** | **Cost** | **Software** | **Hardware** | **Test Sponsor** | **Date** | **FDR** |
|-|-|-|-|-|-|-|-|-|-|-|
| 1000 | 30990.08 | 22.90 | 12993.85 | 9.60 | $1,353,315 | [TigerGraph&nbsp;3.7.0](https://docs.tigergraph.com/tigergraph-server/3.7) | Dell&nbsp;PowerEdge&nbsp;6625 with AMD EPYC 9354 | TigerGraph | 2022/11/09 | [FDR](LDBC_SNB_BI_20221109_SF1000_tigergraph.pdf) |

#### Supplementary materials

Supplementary material for the **2022 TigerGraph audit:**

-  [Executive summary](LDBC_SNB_BI_20221109_SF1000_tigergraph-executive_summary.pdf)
-  [Signatures](LDBC_SNB_BI_20221109_SF1000_tigergraph-signatures.pdf)
-  [Attachments](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/audits/LDBC_SNB_BI_20221109_SF1000_tigergraph-attachments.tar.gz)

### SNB Interactive workload – Audited results

**Disclaimer:** Performance results between implementations using the v0.x and the v1.x drivers are not directly comparable due to [improvements in the SNB driver regarding how operations are counted](https://github.com/ldbc/ldbc_snb_interactive_driver/issues/154).

| **SF** | **Throughput (ops/sec)** | **Cost** | **Software** | **Hardware** | **Test Sponsor** | **Date** | **SNB Interactive Version** | **Driver Version** | **FDR** |
|--------|--------------------------|----------|--------------|--------------|------------------|----------|-----------------|--------------------|----------------------------|
| 30  | 12,252.50 | $291,176 | [TuGraph&nbsp;3.2.0](https://tech.antfin.com/products/TuGraph) | AWS r5d.12xlarge instance, 48\*Intel Xeon Platinum 8259CL @ 2.5GHz, 384GiB RAM | [Ant Group](https://www.antgroup.com/en) | 2022/08/16 | [v0.3.6](https://arxiv.org/pdf/2001.02299v3.pdf) | [v1.2.0](https://github.com/ldbc/ldbc_snb_interactive_driver/releases/tag/v1.2.0) | [FDR](LDBC_SNB_I_20220816_SF30-100-300_tugraph.pdf) |
| 100 | 12,934.61 | $291,176 | [TuGraph&nbsp;3.2.0](https://tech.antfin.com/products/TuGraph) | AWS r5d.12xlarge instance, 48\*Intel Xeon Platinum 8259CL @ 2.5GHz, 384GiB RAM | [Ant Group](https://www.antgroup.com/en) | 2022/08/16 | [v0.3.6](https://arxiv.org/pdf/2001.02299v3.pdf) | [v1.2.0](https://github.com/ldbc/ldbc_snb_interactive_driver/releases/tag/v1.2.0) | [FDR](LDBC_SNB_I_20220816_SF30-100-300_tugraph.pdf) |
| 300 | 12,721.24 | $291,176 | [TuGraph&nbsp;3.2.0](https://tech.antfin.com/products/TuGraph) | AWS r5d.12xlarge instance, 48\*Intel Xeon Platinum 8259CL @ 2.5GHz, 384GiB RAM | [Ant Group](https://www.antgroup.com/en) | 2022/08/16 | [v0.3.6](https://arxiv.org/pdf/2001.02299v3.pdf) | [v1.2.0](https://github.com/ldbc/ldbc_snb_interactive_driver/releases/tag/v1.2.0) | [FDR](LDBC_SNB_I_20220816_SF30-100-300_tugraph.pdf) |
| 30  | 9,285.86 | $263,282 | [Galaxybase&nbsp;3.3.0](https://galaxybase.com/) | AWS r5d.12xlarge instance, 48\*Intel Xeon Platinum 8259CL @ 2.5GHz, 372GB RAM | [CreateLink](https://www.galaxybase.com/) | 2022/05/16 | [v0.3.3](https://arxiv.org/pdf/2001.02299v2.pdf) | [v0.3.4](https://github.com/ldbc/ldbc_snb_interactive_driver/releases/tag/0.3.4) | [FDR](LDBC_SNB_I_20220516_SF30-100-300_galaxybase.pdf) |
| 100 | 8,501.21 | $263,282 | [Galaxybase&nbsp;3.3.0](https://galaxybase.com/) | AWS r5d.12xlarge instance, 48\*Intel Xeon Platinum 8259CL @ 2.5GHz, 372GB RAM | [CreateLink](https://www.galaxybase.com/) | 2022/05/16 | [v0.3.3](https://arxiv.org/pdf/2001.02299v2.pdf) | [v0.3.4](https://github.com/ldbc/ldbc_snb_interactive_driver/releases/tag/0.3.4) | [FDR](LDBC_SNB_I_20220516_SF30-100-300_galaxybase.pdf) |
| 300 | 8,370.52 | $263,282 | [Galaxybase&nbsp;3.3.0](https://galaxybase.com/) | AWS r5d.12xlarge instance, 48\*Intel Xeon Platinum 8259CL @ 2.5GHz, 372GB RAM | [CreateLink](https://www.galaxybase.com/) | 2022/05/16 | [v0.3.3](https://arxiv.org/pdf/2001.02299v2.pdf) | [v0.3.4](https://github.com/ldbc/ldbc_snb_interactive_driver/releases/tag/0.3.4) | [FDR](LDBC_SNB_I_20220516_SF30-100-300_galaxybase.pdf) |
| 30  | 5,436.47 | $280,650 | [TuGraph&nbsp;1.10](https://fma-ai.cn/) | AWS r5d.12xlarge instance, 48\*Intel Xeon Platinum 8175M @ 2.5GHz, 374GB RAM | [FMA](https://fma-ai.cn/) | 2020/07/26 | [v0.3.2](https://arxiv.org/pdf/2001.02299v1.pdf) | [v0.3.3](https://github.com/ldbc/ldbc_snb_interactive_driver/releases/tag/0.3.3) | [FDR](LDBC_SNB_I_20200726_SF30-100-300_tugraph.pdf) |
| 100 | 5,010.77 | $280,650 | [TuGraph&nbsp;1.10](https://fma-ai.cn/) | AWS r5d.12xlarge instance, 48\*Intel Xeon Platinum 8175M @ 2.5GHz, 374GB RAM | [FMA](https://fma-ai.cn/) | 2020/07/26 | [v0.3.2](https://arxiv.org/pdf/2001.02299v1.pdf) | [v0.3.3](https://github.com/ldbc/ldbc_snb_interactive_driver/releases/tag/0.3.3) | [FDR](LDBC_SNB_I_20200726_SF30-100-300_tugraph.pdf) |
| 300 | 4,855.52 | $280,650 | [TuGraph&nbsp;1.10](https://fma-ai.cn/) | AWS r5d.12xlarge instance, 48\*Intel Xeon Platinum 8175M @ 2.5GHz, 374GB RAM | [FMA](https://fma-ai.cn/) | 2020/07/26 | [v0.3.2](https://arxiv.org/pdf/2001.02299v1.pdf) | [v0.3.3](https://github.com/ldbc/ldbc_snb_interactive_driver/releases/tag/0.3.3) | [FDR](LDBC_SNB_I_20200726_SF30-100-300_tugraph.pdf) |


#### Supplementary materials

Supplementary material for the **2022 TuGraph audit sponsored by the Ant Group:**

-  [Executive summary](LDBC_SNB_I_20220816_SF30-100-300_tugraph-executive_summary.pdf)
-  [Signatures](LDBC_SNB_I_20220816_SF30-100-300_tugraph-signatures.pdf)
-  [Attachments](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/audits/LDBC_SNB_I_20200726_SF30-100-300_tugraph-attachments.tar.gz)

Supplementary material for the **2022 Galaxybase audit sponsored by CreateLink:**

-  [Executive summary](LDBC_SNB_I_20220516_SF30-100-300_galaxybase-executive_summary.pdf)
-  [Signatures](LDBC_SNB_I_20220516_SF30-100-300_galaxybase-signatures.pdf)
-  [Attachments](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/audits/LDBC_SNB_I_20220516_SF30-100-300_galaxybase-attachments.tar.gz)

Supplementary material for the **2020 TuGraph audit sponsored by FMA:**

-  [Executive summary](LDBC_SNB_I_20200726_SF30-100-300_tugraph-executive_summary.pdf)
-  [Signatures](LDBC_SNB_I_20200726_SF30-100-300_tugraph-signatures.pdf)
-  [Attachments](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/audits/LDBC_SNB_I_20220816_SF30-100-300_tugraph-attachments.tar.gz)

#### LDBC-certified auditors

SNB Interactive audits can be commissioned from the following LDBC-certified auditors:

* Arnau Prat-Pérez
* Márton Búr
* David Püroja

SNB BI audits can be commissioned from the following LDBC-certified auditors:

* Fabian Murariu (Pometry Ltd.)

For auditing requests, please reach out at `info@ldbcouncil.org`.
Audits can only be commissioned by LDBC member companies by contracting any of the LDBC-certified auditors.
Additionally, there is a 2,000 GBP auditing fee to be paid for the LDBC for non-sponsor company members. Sponsor companies are exempt from this.

#### Legacy audited results

[Social Network Benchmark Interactive, version 0.2.2](/benchmarks/snb/audited-results-v0.2.2)

#### Retrospective review of publications related to LDBC benchmark standards

* [Review of 2019 preprint (sponsored by TigerGraph)](retrospective-report-tigergraph.pdf)
* [Review of 2020 whitepaper (authored by Oracle)](retrospective-report-oracle.pdf)
* [Review of the keynote at NODES 2021 (Neo4j Online Developer Expo and Summit)](retrospective-report-neo4j.pdf)

### Fair use policies

The LDBC Social Network Benchmark is subject to the [LDBC Fair Use Policies](/benchmarks/fair-use-policies).
