---
description: Att&CK威胁工具
---

# 😀 MITRE\_Att\&ck\_Navigator

### ATT\&CK® Navigator

ATT\&CK Navigator 旨在提供 ATT\&CK 矩阵的基本导航和注释，如今人们已经在 Excel 等工具中执行了这些操作。我们将其设计得简单而通用——您可以使用导航器来可视化您的防守覆盖范围、您的红/蓝团队计划、检测到的技术的频率或您想做的任何其他事情。导航器不在乎 - 它只允许您操作矩阵中的单元格（颜色编码、添加注释、分配数值等）。我们认为拥有一个每个人都可以用来可视化矩阵的简单工具将有助于简化 ATT\&CK 的使用。

Navigator 的主要功能是让用户能够定义层 - ATT\&CK 知识库的自定义视图 - 例如，仅显示特定平台的那些技术或突出显示特定对手已知使用的技术。图层可以在导航器中交互创建或以编程方式生成，然后通过导航器进行可视化。

### 用法

ATT\&CK 导航器通过 GitHub 页面实时托管。您可以在此处找到当前版本的 Navigator 的实时实例。您可以在使用文档（反映在应用程序内帮助页面中）中阅读有关如何使用应用程序本身的更多信息。

ATT\&CK Navigator 4.0 版在应用程序的单个实例中支持所有 ATT\&CK 域，而不需要为每个域使用不同的实例。它还看到了对 ICS 域的支持的引入。有关更多信息，请参阅变更日志。

此外，现在可以在应用程序中加载旧版本的 ATT\&CK。 ATT\&CK Navigator 支持 ATT\&CK 版本 8、7、6、5 和 4。旧版本在应用程序中不起作用，因为它们的数据模型太过时了。

以前版本的 Navigator 应用程序也通过 GitHub Pages 为想要更经典体验的用户托管：

| ATT\&CK Version                                              | Navigator Version                                                                        | Domains                                                                      |                                                                      |
| ------------------------------------------------------------ | ---------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------- | -------------------------------------------------------------------- |
| [ATT\&CK v7.2](https://attack.mitre.org/resources/versions/) | [Navigator v3.1](https://github.com/mitre-attack/attack-navigator/releases/tag/v3.1)     | [Enterprise](https://mitre-attack.github.io/attack-navigator/v3/enterprise/) | [Mobile](https://mitre-attack.github.io/attack-navigator/v3/mobile/) |
| [ATT\&CK v6.3](https://attack.mitre.org/resources/versions/) | [Navigator v2.3.2](https://github.com/mitre-attack/attack-navigator/releases/tag/v2.3.2) | [Enterprise](https://mitre-attack.github.io/attack-navigator/v2/enterprise/) | [Mobile](https://mitre-attack.github.io/attack-navigator/v2/mobile/) |

有关如何在本地设置 ATT\&CK Navigator 的信息，请参阅安装和运行。

重要说明：访问托管在 GitHub 页面上的 Navigator 实例时上传的层文件不会存储在服务器端，因为 Navigator 是仅客户端应用程序。但是，如果您的图层文件包含任何敏感内容，我们仍然建议安装和运行您自己的 ATT\&CK Navigator 实例。

使用我们的 GitHub 问题跟踪器让我们知道您遇到的任何错误或其他问题。如果您以一种很酷的方式扩展了导航器并希望与社区分享，我们也鼓励拉取请求！

有关为 ATT\&CK 导航器做出贡献的更多信息，请参阅 CONTRIBUTING.md。

### 要求

* [Node.js](https://nodejs.org) version 8 or greater
* [AngularCLI](https://cli.angular.io)

### 支持的浏览器

* Chrome
* Firefox
* Internet Explorer 11\[1]
* Edge
* Opera
* Safari \[2]

**\[1]** Internet Explorer 上的 SVG 导出功能存在记录问题。由于该浏览器中缺少 SVGElements 的功能，文本将无法在该浏览器中导出的 SVG 中正确垂直居中。我们建议切换到更现代的浏览器以获得最佳结果。

**\[2]** ATT\&CK Navigator 仅支持 Safari 版本 14 及更高版本，因为旧版本的浏览器在选择图层选项卡时可能会出现无法修复的冻结。使用不受支持的浏览器版本的用户将在打开应用程序时收到这种可能性的警告。

### 安装并运行

#### 第一次

1. 导航到 nav-app 目录
2. Run `npm install`

在本地机器上服务应用程序

1. 启动 `ng serve` 在 nav-app 目录中
2. 在浏览器中导航到 localhost:4200

#### 编译在别处使用

#### 编译在别处使用

1. 在 nav-app 目录中运行 ng build
2. 从 nav-app/dist/ 目录复制文件

注意： ng build --prod 目前不适用于没有附加标志的 ATT\&CK Navigator。要构建生产环境，请改用 ng build --prod --aot=false --build-optimizer=false。

#### 离线运行导航器

1. 按照上述说明安装导航器。
2. 按照从本地文件加载内容下的说明配置导航器以在没有 Internet 连接的情况下填充矩阵。对于企业攻击，请使用此文件。对于移动攻击，请使用此文件。对于预攻击，请使用此文件。

常见问题

1. 如果服务或编译应用程序给出警告模块未找到：无法解析 'fs'，请运行命令 npm run postinstall。 postinstall 步骤通常在 npm install 之后自动运行以修补 fs 问题，但在某些环境中它必须手动运行。

### 文档

在浏览器中查看应用程序时，单击 ? ATT\&CK® Navigator 标题右侧的图标以查看其文档。

### 图层文件夹

图层文件夹包含图层格式的规范以及示例图层和演示程序图层生成的脚本。随着新脚本的实施，我们将继续向此存储库添加内容。此外，如果您想在此处添加新功能，请随时创建拉取请求！

可以在 ATT\&CK Navigator 文档中找到有关如何使用和开发图层的更多信息，单击 ?在浏览器中和图层文件夹中的自述文件中运行应用程序时。

### 添加自定义上下文菜单选项

要使用导航器中的数据为 ATT\&CK® 导航器上下文菜单创建自定义选项，必须将对象添加到 nav-app/src/assets/config.json 中标记为 custom\_context\_menu\_options 的数组中。每个对象都必须有一个属性标签，即上下文菜单中显示的文本，以及一个属性 url，即用户导航到的位置。

要在 url 中使用有关右键单击技术的数据，可以将双大括号包围的参数添加到字符串中。例如：使用`http://www.someurl.com/{{technique_attackID}}}` 因为自定义选项中的网址会导致 `http://www.someurl.com/T1098`, 如果右键单击的技术的attackID 是T1098。将解析以下数据替换:

* `{{technique_attackID}}` 将替换为技术的 ATT\&CK ID，例如 `T1234`
* `{{technique_stixID}}` 将替换为该技术的 STIX ID，例如 `attack-pattern--12345678-1234-1234-1234-123456789123`
* `{{technique_name}}` 将用小写的技术名称替换，并用连字符替换空格，例如 `example-technique-name`
* `{{tactic_attackID}}` 将替换为策略的 ATT\&CK ID，例如 `TA1234`
* `{{tactic_stixID}}` 将替换为战术的 STIX ID，例如 `x-mitre-tactic--12345678-1234-1234-1234-123456789123`
* `{{tactic_name}}` 将替换为小写的战术名称，空格替换为连字符，例如`example-tactic`. 这也等效于策略的 x\_mitre\_shortname 属性。

可选地，可以将 subtechnique\_url 字段添加到自定义选项中。当该选项用于子技术而不是用于技术的普通 URL 时，将解析此字段。如果未使用 subtechnique\_url，则上面定义的 technology\_ 替换将引用子技术对象本身。

将为子技术解析以下替换：

* `{{parent_technique_attackID}}` 将替换为子技术的父级的 ATT\&CK ID，例如 `T1234`
* `{{parent_technique_stixID}}` 将替换为子技术的父级的 STIX ID，例如 `attack-pattern--12345678-1234-1234-1234-123456789123`
* `{{parent_technique_name}}` 将被替换为小写的子技术的父级名称，并用连字符替换空格，例如 `example-technique-name`
* `{{subtechnique_attackID}}` 将替换为子技术的 ATT\&CK ID，例如`T1234.001`
* `{{subtechnique_attackID_suffix}}` 将在定界期后替换为子技术的ATT\&CK ID部分，例如 `001`
* `{{subtechnique_stixID}}` 将替换为子技术的 STIX ID，例如 `attack-pattern--98765432-9876-9876-9876-987654321987`
* `{{subtechnique_name}}` 将替换为小写的子技术名称，并用连字符替换空格，例如 `example-subtechnique-name`
* `{{tactic_attackID}}`将替换为策略的 ATT\&CK ID，例如 `TA1234`
* `{{tactic_stixID}}`将替换为战术的 STIX ID，例如 `x-mitre-tactic--12345678-1234-1234-1234-123456789123`
* `{{tactic_name}}` 将替换为小写的战术名称，空格替换为连字符，例如 `example-tactic`. 这也相当于战术的 x\_mitre\_shortname 属性.

示例自定义上下文菜单对象:

```
{
    "label": "view technique on ATT&CK website",
    "url": "https://attack.mitre.org/techniques/{{technique_attackID}}",
    "subtechnique_url": "https://attack.mitre.org/techniques/{{parent_technique_attackID}}/{{subtechnique_attackID_suffix}}"
}
```

```
{
    "label": "view tactic on ATT&CK website",
    "url": "https://attack.mitre.org/tactics/{{tactic_attackID}}"
}
```

### 从 TAXII 服务器加载内容

默认情况下，导航器从托管在 MITRE/CTI 存储库上的 ATT\&CK STIX 数据加载内容。注意：从 TAXII 服务器加载内容时不支持 TAXII 2.1/STIX 2.1 包。

1. 编辑 nav-app/src/assets 目录中的 config.json 文件。
2. 定义taxii\_url 属性代替data 属性并将值设置为您的服务器的URL。
3. 定义taxii\_collection 属性并将值设置为TAXII 服务器设置的集合UUID。

从 TAXII 服务器加载内容的示例:

```
"domains": [
    {
        "name": "Enterprise",
        "taxii_url": "https://cti-taxii.mitre.org/",
        "taxii_collection": "95ecc380-afe9-11e4-9b6c-751b66dd541e"
    }
]
```

### 从本地文件加载内容

可以使用由 STIX 对象包组成的文件来填充导航器，类似于此文件。支持 STIX 2.0 和 STIX 2.1 包_._

1. 将 stix 包放在 src/assets 中。这将告诉托管导航器的服务器也托管数据
2. 编辑 nav-app/src/assets 目录中的 config.json 文件。
3. 将数据数组中指定的 URL 更改为 STIX 包的路径（例如 assets/enterprise-attack.json）。可以将多个路径添加到数据数组中以在单个实例中显示多个 STIX 包。

从本地文件加载内容的示例:

```
"domains": [
    {
        "name": "Enterprise",
        "data": ["assets/enterprise-attack.json"]
    }
]
```

### 运行 Docker 文件

1. 导航到 nav-app 目录
2. Run `docker build -t yourcustomname .`
3. Run `docker run -p 4200:4200 yourcustomname`
4. 在浏览器中导航到 localhost:4200

### 初始化时加载默认图层

导航器可以配置为在初始化时加载一组层。这些层可以来自网络和/或来自本地文件。要加载的本地文件应放在 nav-app/src/assets/ 目录中。

1. 将 src/assets/config.json 中 default\_layers 中的 enabled 属性设置为 true
2.  将所需默认图层的路径添加到 default\_layers 中的 urls 数组。例如,

    ```
    "default_layers": {
         "enabled": true,
         "urls": [
             "assets/example.json", 
             "https://raw.githubusercontent.com/mitre-attack/attack-navigator/master/layers/data/samples/Bear_APT.json"
         ]
     }
    ```

    将从本地资产目录加载 example.json，并从 Github 上此 repo 的示例层文件夹加载 Bear\_APT.json.
3. 加载/重新加载导航器

还可以使用导航器 URL 中的查询字符串设置来自 Web 的默认图层。有关更多详细信息，请参阅应用程序内帮助页面部分“自定义导航器”。

如果默认层已过时，则不会提示用户将默认层升级到当前版本的 ATT\&CK。

### 在导航器中启用横幅

默认情况下，nav-app/src/assets/config.json 中的横幅设置是一个空字符串 """（并且不可见），并且可以设置为您希望在导航器顶部横幅内显示的任何内容网页。横幅在内容中支持 HTML 和超链接。

### 禁用导航器功能

nav-app/src/assets/config.json 中的 features 数组列出了您可能想要禁用的 Navigator 功能。在配置文件中的某个功能上设置启用字段将隐藏与该功能相关的所有控制元素。

但是，如果上传的图层带有与该要素相关的注释或配置，则该图层不会被隐藏。例如，如果评论被禁用，添加新评论注释的功能将被删除，但是如果上传的图层带有评论，它们仍将显示在工具提示中并用下划线标记。

也可以使用创建自定义导航器功能禁用功能。有关更多详细信息，请参阅应用程序内帮助页面部分“自定义导航器”。

### 在网页中嵌入导航器

如果要在网页中嵌入导航器，请使用 iframe:

```
<iframe src="https://mitre-attack.github.io/attack-navigator/enterprise/" width="1000" height="500"></iframe>
```

如果您想要嵌入已删除特定功能（例如选项卡、添加注释）或带有默认图层的导航器版本，我们建议使用创建自定义导航器功能。我们强烈建议在嵌入导航器时通过这种方式禁用“离开站点对话框”，否则每当您尝试离开嵌入页面时都会收到警告。有关更多详细信息，请参阅应用程序内帮助页面部分“自定义导航器”.

以下是一个示例 iframe，它嵌入了我们的 \*Bear APTs 层，带有选项卡，并删除了添加注释的功能:

```
<iframe src="https://mitre-attack.github.io/attack-navigator/enterprise/#layerURL=https%3A%2F%2Fraw.githubusercontent.com%2Fmitre%2Fattack-navigator%2Fmaster%2Flayers%2Fdata%2Fsamples%2FBear_APT.json&tabs=false&selecting_techniques=false" width="1000" height="500"></iframe>
```

### 相关的 MITRE 工作

**CTI**

ATT\&CK 目录的网络威胁情报存储库，以 STIX 2.0 JSON 表示.

**ATT\&CK**

ATT\&CK® 是网络对手行为的策划知识库和模型，反映了对手生命周期的各个阶段以及他们已知的目标平台。 ATT\&CK 可用于了解针对已知对手行为的安全风险、规划安全改进以及验证防御是否按预期工作.

[https://attack.mitre.org](https://attack.mitre.org)

**STIX**

结构化威胁信息表达式 (STIX™) 是一种用于交换网络威胁情报 (CTI) 的语言和序列化格式.

STIX 使组织能够以一致和机器可读的方式相互共享 CTI，使安全社区能够更好地了解他们最有可能看到哪些基于计算机的攻击，并更快、更有效地预测和/或响应这些攻击.

STIX 旨在改进许多不同的功能，例如协作威胁分析、自动威胁交换、自动检测和响应等.

[https://oasis-open.github.io/cti-documentation/](https://oasis-open.github.io/cti-documentation/)

### 注意

版权所有 2020 MITRE 公司已获准公开发行；分发无限。案件编号 18-0128。根据 Apache 许可，版本 2.0（“许可”）获得许可；除非遵守许可，否则您不得使用此文件。您可以在以下网址获得许可证的副本

[http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0)

除非适用法律要求或书面同意，否则根据许可分发的软件是按“原样”分发的，没有任何类型的明示或暗示的保证或条件。请参阅许可证以了解许可证下管理权限和限制的特定语言.

这个项目使用了ATT\&CK®

[ATT\&CK® Terms of Use](https://attack.mitre.org/resources/terms-of-use/)
