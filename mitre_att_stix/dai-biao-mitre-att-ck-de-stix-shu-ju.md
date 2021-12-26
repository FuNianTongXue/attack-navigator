# 😃 代表 MITRE ATT & CK 的 STIX 数据

### ATT & CK® STIX 数据

[MITRE ATT\&CK](https://attack.mitre.org) 是基于现实世界观察的全球可访问的对手战术和技术知识库。 ATT\&CK 知识库被用作在私营部门、政府以及网络安全产品和服务社区中开发特定威胁模型和方法的基础.

该存储库包含以 STIX 2.1 JSON 集合表示的 MITRE ATT\&CK 数据集。如果您正在寻找代表 ATT\&CK 的 STIX 2.0 JSON，请参阅我们的 [MITRE/CTI](https://github.com/mitre/cti) GitHub 存储库包含相同的数据集，但在 STIX 2.0 中，并且没有此存储库提供的集合功能。

### 存储库结构

```
.
├─ enterprise-attack ∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙ [1] Collection folder for Enterprise
│   ├─ enterprise-attack.json ∙∙∙∙∙∙∙∙∙∙∙∙∙∙ [2] Most recent Enterprise release
│   ├─ enterprise-attack-9.0.json ∙∙∙∙∙∙∙∙∙∙ [3] Enterprise ATT&CK v9.0 collection
│   └─ [other releases of Enterprise ATT&CK]
├─ mobile-attack
│   └─ [Mobile ATT&CK releases]
├─ ics-attack
│   └─ [ATT&CK for ICS releases]
├─ index.json ∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙ [4] Collection index JSON
└─ index.md ∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙∙ [5] Collection index markdown
```

**\[1]** ATT\&CK 的每个域（企业、移动和 ICS）都表示为一系列 STIX 2.1 集合包，代表数据集的各个版本，在集合文件夹中组织。

**\[2]** 每个域都包含一个没有版本标记的 STIX 2.1 集合包，它始终与数据集的最新版本相匹配。

**\[3]** 集合文件夹中的每个 STIX 包都代表集合的一个特定版本。在我们的了解更多 [collections](https://github.com/center-for-threat-informed-defense/attack-workbench-frontend/blob/master/docs/collections.md#collections) 文档.

**\[4]** 这 [collection index JSON](https://raw.githubusercontent.com/mitre-attack/attack-stix-data/master/index.json) 以机器可读的格式列出此存储库的内容。在我们的了解更多 [collections](https://github.com/center-for-threat-informed-defense/attack-workbench-frontend/blob/master/docs/collections.md#collection-indexes) 文档.

**\[5]** The [collection index markdown](broken-reference) lists the contents of this repository in a human-readable format.

### 支持文档

#### [STIX](https://oasis-open.github.io/cti-documentation/)

结构化威胁信息表达式 (STIX™) 是一种用于交换网络威胁情报 (CTI) 的语言和序列化格式。

STIX 使组织能够以一致和机器可读的方式相互共享 CTI，使安全社区能够更好地了解他们最有可能看到哪些基于计算机的攻击，并更快、更有效地预测和/或响应这些攻击。

STIX is designed to improve many different capabilities, such as collaborative threat analysis, automated threat exchange, automated detection and response, and more.

#### [Collections](https://github.com/center-for-threat-informed-defense/attack-workbench-frontend/blob/master/docs/collections.md#collections)

Collections are sets of related ATT\&CK objects, and may be used to represent specific releases of a dataset such as “Enterprise ATT\&CK v9.0” or any other set of objects one may want to share with someone else.

Each ATT\&CK release on this repository is itself a collection. A full list of collections on this repository can be found in [index.md](broken-reference).

#### [Collection Indexes](https://github.com/center-for-threat-informed-defense/attack-workbench-frontend/blob/master/docs/collections.md#collection-indexes)

Collection indexes are organized lists of collections intended to ease their distribution to data consumers. Collection indexes track individual releases of given collections (e.g Enterprise v7, Enterprise v8, Enterprise v9) and allow applications such as the [ATT\&CK Workbench](https://github.com/center-for-threat-informed-defense/attack-workbench-frontend) to check if new releases have been published. Collection indexes are represented as JSON objects.

The ATT\&CK collection index for the contents of this repository is [index.json](https://raw.githubusercontent.com/mitre-attack/attack-stix-data/master/index.json), with a human-readable representation available in [index.md](broken-reference).

#### [Usage](broken-reference)

The Usage document includes documentation of the ATT\&CK data model as well as code examples for accessing and querying this content with [cti-python-stix2](https://github.com/oasis-open/cti-python-stix2). Additional information and tooling for maintaining the data in this repository is available in the [util](<../.gitbook/assets/util (2)>) folder.

### Notice

Copyright 2020-2021 The MITRE Corporation. Approved for public release. Case number 19-3504.

This project makes use of ATT\&CK®

[ATT\&CK Terms of Use](https://attack.mitre.org/resources/terms-of-use/)
