---
title: "LDBC Semantic Publishing Benchmark (LDBC-SPB)"
aliases: [
    "/benchmark-spb/",
    "/developer/spb"
]
type: generic
---

The Semantic Publishing Benchmark (SPB) is an LDBC benchmark for testing the performance of RDF engines inspired by the Media/Publishing industry. In particular, LDBC worked with British Broadcasting Corporation [BBC](http://www.bbc.co.uk/blogs/internet/posts/Linked-Data-Connecting-together-the-BBCs-Online-Content) to define this benchmark, for which BBC donated workloads, [ontologies](https://github.com/ldbc/ldbc_spb_bm_2.0/tree/master/datasets_and_queries/ontologies) and data. The publishing industry is an area where significant adoption of RDF is taking place.

There have been many academic benchmarks for RDF but none of these are truly industrial-grade. The SPB  combines a set of complex queries under inference with continuous updates and special failover tests for systems implementing replication.

SPB performance is measured by producing a workload of CRUD (Create, Read, Update, Delete) operations which are executed simultaneously. The benchmark offers a data generator that uses real reference data to produce datasets of various sizes and tests the scalability aspect of RDF systems. The benchmark workload consists of (a) editorial operations that add new data, alter or delete existing (b) aggregation operations that retrieve content according to various criteria. The benchmark also tests conformance for various rules inside the OWL2-RL rule-set.

The [SPB specification](ldbc-spb-v2.0-specification.pdf) contains the description of the benchmark and the data generator and all information about its software components can be found on the [SPB developer page](/developer/spb).

#### Semantic Publishing Benchmark (SPB) Audited Results

Results for Scale Factors SF1 (64M), SF3 (256M), and SF5 (1G) triples are shown below.

| **Scale Factor**                                | **#Triples**                                        | **Interactive (Q/s)**                                  | **Updates (ops/sec)**                                  | **Cost**        | **Software**         | **Hardware**                             | **Test Sponsor**                                | **Date**                                             | **FDR**                                            |
| ----------------------------------------------- | --------------------------------------------------- | ------------------------------------------------------ | ------------------------------------------------------ | --------------- | -------------------- | ---------------------------------------- | ----------------------------------------------- | ---------------------------------------------------- | -------------------------------------------------- |
| <div style="text-align:right!important">1</div> | <div style="text-align:right!important">64M</div>   | <div style="text-align:right!important">100.85</div>   | <div style="text-align:right!important">10.19</div>    | 37,504&nbsp;EUR | GraphDB EE 6.2       | Intel Xeon E5-1650v3 6×3.5Ghz, 96GB RAM  | [Ontotext AD](https://www.ontotext.com/)        | <time style="white-space: nowrap;">2015-04-26</time> | [FDR](LDBC_SPB20_20150426_SF1_GraphDB-EE-6.2b.pdf) |
| <div style="text-align:right!important">1</div> | <div style="text-align:right!important">64M</div>   | <div style="text-align:right!important">142.7588</div> | <div style="text-align:right!important">10.6725</div>  | 35,323&nbsp;EUR | GraphDB SE 6.3 alpha | Intel Xeon E5-1650v3 6×3.5GHz, 64GB RAM  | [Ontotext AD](https://www.ontotext.com/)        | <time style="white-space: nowrap;">2015-06-10</time> | [FDR](LDBC-SPB-64M-GraphDB-10062015.pdf)           |
| <div style="text-align:right!important">3</div> | <div style="text-align:right!important">256M</div>  | <div style="text-align:right!important">29.90</div>    | <div style="text-align:right!important">9.50</div>     | 37,504&nbsp;EUR | GraphDB EE 6.2       | Intel Xeon E5-1650v3 6×3.5Ghz, 96GB RAM  | [Ontotext AD](https://www.ontotext.com/)        | <time style="white-space: nowrap;">2015-04-26</time> | [FDR](LDBC_SPB20_20150426_SF3_GraphDB-EE-6.2b.pdf) |
| <div style="text-align:right!important">3</div> | <div style="text-align:right!important">256M</div>  | <div style="text-align:right!important">54.6364</div>  | <div style="text-align:right!important">9.4967</div>   | 35,323&nbsp;EUR | GraphDB SE 6.3 alpha | Intel Xeon E5-1650v3 6×3.5GHz, 64GB RAM  | [Ontotext AD](https://www.ontotext.com/)        | <time style="white-space: nowrap;">2015-06-10</time> | [FDR](LDBC-SPB-256M-GraphDB-10062015.pdf)          |
| <div style="text-align:right!important">1</div> | <div style="text-align:right!important">64M</div>   | <div style="text-align:right!important">149.0385</div> | <div style="text-align:right!important">156.8325</div> | 20,213&nbsp;USD | Virtuoso v7.50.3213  | Intel Xeon E5-2630 6×2.30GHz, 192 GB RAM | [OpenLink Software](http://www.openlinksw.com/) | <time style="white-space: nowrap;">2015-06-09</time> | [FDR](LDBC-SPB-64M-Virtuoso-09062015.pdf)          |
| <div style="text-align:right!important">3</div> | <div style="text-align:right!important">256M</div>  | <div style="text-align:right!important">80.6158</div>  | <div style="text-align:right!important">92.7072</div>  | 20,213&nbsp;USD | Virtuoso v7.50.3213  | Intel Xeon E5-2630 6×2.30GHz, 192 GB RAM | [OpenLink Software](http://www.openlinksw.com/) | <time style="white-space: nowrap;">2015-06-09</time> | [FDR](LDBC-SPB-256M-Virtuoso-09062015.pdf)         |
| <div style="text-align:right!important">3</div> | <div style="text-align:right!important">256M</div>  | <div style="text-align:right!important">115.3838</div> | <div style="text-align:right!important">109.8517</div> | 24,528&nbsp;USD | Virtuoso v7.50.3213  | AWS r3.8xlarge                           | [OpenLink Software](http://www.openlinksw.com/) | <time style="white-space: nowrap;">2015-06-09</time> | [FDR](LDBC-SPB-256M-Virtuoso-EC2-09062015.pdf)     |
| <div style="text-align:right!important">5</div> | <div style="text-align:right!important">1000M</div> | <div style="text-align:right!important">32.2789</div>  | <div style="text-align:right!important">72.7192</div>  | 20,213&nbsp;USD | Virtuoso v7.50.3213  | Intel Xeon E5-2630 6×2.30GHz, 192 GB RAM | [OpenLink Software](http://www.openlinksw.com/) | <time style="white-space: nowrap;">2015-06-09</time> | [FDR](LDBC-SPB-1G-Virtuoso-09062015.pdf)           |
| <div style="text-align:right!important">5</div> | <div style="text-align:right!important">10M</div>   | <div style="text-align:right!important">45.8101</div>  | <div style="text-align:right!important">55.4467</div>  | 24,528&nbsp;USD | Virtuoso v7.50.3213  | AWS r3.8xlarge                           | [OpenLink Software](http://www.openlinksw.com/) | <time style="white-space: nowrap;">2015-06-10</time> | [FDR](LDBC-SPB-1G-Virtuoso-EC2-10062015.pdf)       |

#### LDBC-certified auditors

SPB audits can be commissioned from the following LDBC-certified auditors:

* Pjotr Scholtze
