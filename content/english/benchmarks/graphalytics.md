---
title: "LDBC Graphalytics Benchmark (LDBC Graphalytics)"
aliases: [
    "/benchmark-graphalytics/",
    "/ldbc-graphalytics-0"
]
type: generic
---

The Graphalytics benchmark is an industrial-grade benchmark for **graph analysis platforms** such as Giraph. It consists of six core algorithms, standard data sets, synthetic data set generators, and reference outputs, enabling the objective comparison of graph analysis platforms.

The design of the benchmark process takes into account that graph-processing is impeded by three dimensions of diversity: **platform**,  **algorithms** and **data set**.

The benchmark harness consists of a core component, which is extendable by a driver for each different platform implementation. The choice of the six algorithms:

1.  breadth-first search,
2.  PageRank,
3.  weakly connected components,
4.  community detection using label propagation,
5.  local clustering coefficient, and
6.  single-source shortest paths

was carefully motivated, using the LDBC TUC and extensive literature surveys to ensure good coverage of scenarios. The standard data sets include both real and synthetic data sets, which are classified into intuitive “T-shirt” sizes (e.g., **S, M, L, XL**).

Each experiment set in Graphalytics consists of **multiple platform runs** (a platform executes an algorithm on a data set), and diverse set of experiments are carried out to evaluate different performance characteristics of a system-under-test.

All completed benchmarks must go through a strict **validation process** to ensure the integrity of the performance results.

The development of Graphalytics is supported by many active vendors in the field of large-scale graph analytics. Currently, Graphalytics already facilitates benchmark for a large number of graph analytics platforms, such as GraphBLAS, Giraph, GraphX, and PGX.D, allowing comparison of the state-of-the-art system performance of both community-driven and industrial-driven platforms. To get started, the details of the Graphalyics documentation and its software components are described below.

Documents and repositories:

* [Benchmark specification](https://arxiv.org/pdf/2011.15028.pdf). The source code is stored in the [`ldbc_graphalytics_docs`](https://github.com/ldbc/ldbc_graphalytics_docs) repository
* [VLDB paper](http://www.vldb.org/pvldb/vol9/p1317-iosup.pdf)
* [`ldbc_graphalytics`](https://github.com/ldbc/ldbc_graphalytics): Generic driver
* [`ldbc_graphalytics_platforms_reference`](https://github.com/ldbc/ldbc_graphalytics_platforms_reference): Reference implementation

## Data sets

The Graphalytics data sets are compressed using [`zstd`](https://github.com/facebook/zstd). The total size of the compressed archives is 326GB. Decompressed, it's approximately 1.1TB.

The data sets are available in the 3 locations:

* [Cloudflare R2](https://www.cloudflare.com/products/r2/) bucket: see the links and scripts below (recommended)
* [CWI/SURF data repository](https://hdl.handle.net/11112/7ec6a51e-6fdb-bf8d-4507-456ccadc9291)
* [CWI/SURFdrive directory (NextCloud)](https://surfdrive.surf.nl/files/index.php/s/R8XkQNhVRLu9HaF)

| data set           | #nodes      | #edges         | scale | link                                                                                                                        | size     |
| ------------------ | ----------- | -------------- | ----- | --------------------------------------------------------------------------------------------------------------------------- | -------- |
| cit-Patents        | 3,774,768   | 16,518,947     | XS    | [`cit-Patents.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/cit-Patents.tar.zst)               | 119.1 MB |
| com-friendster     | 65,608,366  | 1,806,067,135  | XL    | [`com-friendster.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/com-friendster.tar.zst)         | 6.7 GB   |
| datagen-7_5-fb     | 633,432     | 34,185,747     | S     | [`datagen-7_5-fb.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/datagen-7_5-fb.tar.zst)         | 162.3 MB |
| datagen-7_6-fb     | 754,147     | 42,162,988     | S     | [`datagen-7_6-fb.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/datagen-7_6-fb.tar.zst)         | 200.0 MB |
| datagen-7_7-zf     | 13,180,508  | 32,791,267     | S     | [`datagen-7_7-zf.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/datagen-7_7-zf.tar.zst)         | 434.5 MB |
| datagen-7_8-zf     | 16,521,886  | 41,025,255     | S     | [`datagen-7_8-zf.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/datagen-7_8-zf.tar.zst)         | 544.3 MB |
| datagen-7_9-fb     | 1,387,587   | 85,670,523     | S     | [`datagen-7_9-fb.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/datagen-7_9-fb.tar.zst)         | 401.2 MB |
| datagen-8_0-fb     | 1,706,561   | 107,507,376    | M     | [`datagen-8_0-fb.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/datagen-8_0-fb.tar.zst)         | 502.5 MB |
| datagen-8_1-fb     | 2,072,117   | 134,267,822    | M     | [`datagen-8_1-fb.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/datagen-8_1-fb.tar.zst)         | 625.4 MB |
| datagen-8_2-zf     | 43,734,497  | 106,440,188    | M     | [`datagen-8_2-zf.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/datagen-8_2-zf.tar.zst)         | 1.4 GB   |
| datagen-8_3-zf     | 53,525,014  | 130,579,909    | M     | [`datagen-8_3-zf.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/datagen-8_3-zf.tar.zst)         | 1.7 GB   |
| datagen-8_4-fb     | 3,809,084   | 269,479,177    | M     | [`datagen-8_4-fb.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/datagen-8_4-fb.tar.zst)         | 1.2 GB   |
| datagen-8_5-fb     | 4,599,739   | 332,026,902    | L     | [`datagen-8_5-fb.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/datagen-8_5-fb.tar.zst)         | 1.5 GB   |
| datagen-8_6-fb     | 5,667,674   | 421,988,619    | L     | [`datagen-8_6-fb.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/datagen-8_6-fb.tar.zst)         | 1.9 GB   |
| datagen-8_7-zf     | 145,050,709 | 340,157,363    | L     | [`datagen-8_7-zf.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/datagen-8_7-zf.tar.zst)         | 4.6 GB   |
| datagen-8_8-zf     | 168,308,893 | 413,354,288    | L     | [`datagen-8_8-zf.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/datagen-8_8-zf.tar.zst)         | 5.3 GB   |
| datagen-8_9-fb     | 10,572,901  | 848,681,908    | L     | [`datagen-8_9-fb.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/datagen-8_9-fb.tar.zst)         | 3.7 GB   |
| datagen-9_0-fb     | 12,857,671  | 1,049,527,225  | XL    | [`datagen-9_0-fb.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/datagen-9_0-fb.tar.zst)         | 4.6 GB   |
| datagen-9_1-fb     | 16,087,483  | 1,342,158,397  | XL    | [`datagen-9_1-fb.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/datagen-9_1-fb.tar.zst)         | 5.8 GB   |
| datagen-9_2-zf     | 434,943,376 | 1,042,340,732  | XL    | [`datagen-9_2-zf.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/datagen-9_2-zf.tar.zst)         | 13.7 GB  |
| datagen-9_3-zf     | 555,270,053 | 1,309,998,551  | XL    | [`datagen-9_3-zf.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/datagen-9_3-zf.tar.zst)         | 17.4 GB  |
| datagen-9_4-fb     | 29,310,565  | 2,588,948,669  | XL    | [`datagen-9_4-fb.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/datagen-9_4-fb.tar.zst)         | 10.9 GB  |
| datagen-sf3k-fb    | 33,484,375  | 2,912,009,743  | XL    | [`datagen-sf3k-fb.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/datagen-sf3k-fb.tar.zst)       | 12.9 GB  |
| datagen-sf10k-fb   | 100,218,750 | 9,404,822,538  | 2XL   | [`datagen-sf10k-fb.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/datagen-sf10k-fb.tar.zst)     | 32.0 GB  |
| dota-league        | 61,170      | 50,870,313     | S     | [`dota-league.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/dota-league.tar.zst)               | 114.3 MB |
| example-directed   | 10          | 17             | -     | [`example-directed.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/example-directed.tar.zst)     | 1.0 KB   |
| example-undirected | 9           | 12             | -     | [`example-undirected.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/example-undirected.tar.zst) | 1.0 KB   |
| graph500-22        | 2,396,657   | 64,155,735     | S     | [`graph500-22.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/graph500-22.tar.zst)               | 202.4 MB |
| graph500-23        | 4,610,222   | 129,333,677    | M     | [`graph500-23.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/graph500-23.tar.zst)               | 410.6 MB |
| graph500-24        | 8,870,942   | 260,379,520    | M     | [`graph500-24.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/graph500-24.tar.zst)               | 847.7 MB |
| graph500-25        | 17,062,472  | 523,602,831    | L     | [`graph500-25.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/graph500-25.tar.zst)               | 1.7 GB   |
| graph500-26        | 32,804,978  | 1,051,922,853  | XL    | [`graph500-26.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/graph500-26.tar.zst)               | 3.4 GB   |
| graph500-27        | 63,081,040  | 2,111,642,032  | XL    | [`graph500-27.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/graph500-27.tar.zst)               | 7.2 GB   |
| graph500-28        | 121,242,388 | 4,236,163,958  | 2XL   | [`graph500-28.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/graph500-28.tar.zst)               | 14.5 GB  |
| graph500-29        | 232,999,630 | 8,493,569,115  | 2XL   | [`graph500-29.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/graph500-29.tar.zst)               | 29.7 GB  |
| graph500-30        | 447,797,986 | 17,022,117,362 | 3XL   | [`graph500-30.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/graph500-30.tar.zst)               | 32.0 GB  |
| kgs                | 832,247     | 17,891,698     | XS    | [`kgs.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/kgs.tar.zst)                               | 65.7 MB  |
| twitter_mpi        | 52,579,678  | 1,963,263,508  | XL    | [`twitter_mpi.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/twitter_mpi.tar.zst)               | 5.7 GB   |
| wiki-Talk          | 2,394,385   | 5,021,410      | 2XS   | [`wiki-Talk.tar.zst`](https://pub-383410a98aef4cb686f0c7601eddd25f.r2.dev/graphalytics/wiki-Talk.tar.zst)                   | 34.9 MB  |

* [`.sh` script to download the data sets from surf.nl](/scripts/download-graphalytics-data-sets.sh)
* [`.sh` script to download the data sets from Cloudflare R2](/scripts/download-graphalytics-data-sets-r2.sh)
