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
2. Copy files from `nav-app/dist/` directory

_Note: `ng build --prod` does not currently work for ATT\&CK Navigator without additional flags. To build the production environment instead use `ng build --prod --aot=false --build-optimizer=false`._

**Running the Navigator offline**

1. Install the Navigator as per instructions above.
2. Follow instructions under [loading content from local files](broken-reference) to configure the Navigator to populate the matrix without an internet connection. For enterprise-attack, use [this file](https://raw.githubusercontent.com/mitre/cti/master/enterprise-attack/enterprise-attack.json). For mobile-attack, use [this file](https://raw.githubusercontent.com/mitre/cti/master/mobile-attack/mobile-attack.json). For pre-attack, use [this file](https://raw.githubusercontent.com/mitre/cti/master/pre-attack/pre-attack.json).

**Common issues**

1. If serving or compiling the application gives the warning `Module not found: can't resolve 'fs'`, run the command `npm run postinstall`. The postinstall step usually runs automatically after `npm install` to patch the `fs` issue, but in some environments it must be run manually.

### Documentation

When viewing the app in a browser, click on the **?** icon to the right of the **ATT\&CK® Navigator** title to view its documentation.

### Layers Folder

The **layers** folder contains specifications for the layer format as well as example layers and a script demonstrating programatic layer generation. We will continue to add content to this repository as new scripts are implemented. Also, feel free to create pull requests if you want to add new capabilities here!

More information on how layers are used and developed can be found in the ATT\&CK Navigator documentation that can be viewed by clicking **?** when running the app in a browser, and in the README in the **layers** folder.

### Adding Custom Context Menu Options

To create custom options to the **ATT\&CK® Navigator** context menu using data in the Navigator, objects must be added to the array labeled `custom_context_menu_options` in `nav-app/src/assets/config.json`. Each object must have a property **label**, which is the text displayed in the context menu, and a property **url**, which is where the user is navigated.

To utilize data on right-clicked technique in the url, parameters surrounded by double curly brackets can be added to the string. For example: using `http://www.someurl.com/{{technique_attackID}}}` as the url in the custom option would lead to `http://www.someurl.com/T1098`, if the right-clicked technique's attackID was T1098.

The following data substitutions will be parsed:

* `{{technique_attackID}}` will be substituted with the ATT\&CK ID of the technique, e.g `T1234`
* `{{technique_stixID}}` will be substituted with the STIX ID of the technique, e.g `attack-pattern--12345678-1234-1234-1234-123456789123`
* `{{technique_name}}` will be substituted with the technique name in lower case and with spaces replaced with hyphens, e.g `example-technique-name`
* `{{tactic_attackID}}` will be substituted with the ATT\&CK ID of the tactic, e.g `TA1234`
* `{{tactic_stixID}}` will be substituted with the STIX ID of the tactic, e.g `x-mitre-tactic--12345678-1234-1234-1234-123456789123`
* `{{tactic_name}}` will be substituted with the tactic name in lower case and with spaces replaced with hyphens, e.g `example-tactic`. This is also equivalent to the x\_mitre\_shortname property of the tactic.

Optionally, a `subtechnique_url` field may be added to a custom option. This field will be parsed when the option is used on a sub-technique instead of the normal URL, which will be used for techniques. If `subtechnique_url` is not used, the `technique_` substitutions defined above will refer to the sub-technique object itself.

The following substitutions will be parsed for sub-techniques:

* `{{parent_technique_attackID}}` will be substituted with the ATT\&CK ID of the sub-technique's parent, e.g `T1234`
* `{{parent_technique_stixID}}` will be substituted with the STIX ID of the sub-technique's parent, e.g `attack-pattern--12345678-1234-1234-1234-123456789123`
* `{{parent_technique_name}}` will be substituted with the name of the sub-technique's parent in lower case and with spaces replaced with hyphens, e.g `example-technique-name`
* `{{subtechnique_attackID}}` will be substituted with the ATT\&CK ID of the sub-technique, e.g `T1234.001`
* `{{subtechnique_attackID_suffix}}` will be substituted with the portion of the ATT\&CK ID of the sub-technique after the delimiting period, e.g `001`
* `{{subtechnique_stixID}}` will be substituted with the STIX ID of the sub-technique, e.g `attack-pattern--98765432-9876-9876-9876-987654321987`
* `{{subtechnique_name}}` will be substituted with the sub-technique name in lower case and with spaces replaced with hyphens, e.g `example-subtechnique-name`
* `{{tactic_attackID}}` will be substituted with the ATT\&CK ID of the tactic, e.g `TA1234`
* `{{tactic_stixID}}` will be substituted with the STIX ID of the tactic, e.g `x-mitre-tactic--12345678-1234-1234-1234-123456789123`
* `{{tactic_name}}` will be substituted with the tactic name in lower case and with spaces replaced with hyphens, e.g `example-tactic`. This is also equivalent to the x\_mitre\_shortname property of the tactic.

Example custom context menu objects:

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

### Loading content from a TAXII server

_By default, the Navigator loads content from ATT\&CK STIX data hosted on the_ [_MITRE/CTI repository_](broken-reference)_. Note: TAXII 2.1/STIX 2.1 bundles are **not** supported when loading content from a TAXII server._

1. Edit the `config.json` file in the **nav-app/src/assets** directory.
2. Define the `taxii_url` property in place of the `data` property and set the value to your server's URL.
3. Define the `taxii_collection` property and set the value to the collection UUIDs your TAXII server has set.

Example loading content from a TAXII server:

```
"domains": [
    {
        "name": "Enterprise",
        "taxii_url": "https://cti-taxii.mitre.org/",
        "taxii_collection": "95ecc380-afe9-11e4-9b6c-751b66dd541e"
    }
]
```

### Loading content from local files

_It's possible to populate the the Navigator using files that consist of bundles of STIX objects, similarly to_ [_this_](https://raw.githubusercontent.com/mitre/cti/master/enterprise-attack/enterprise-attack.json) _file. STIX 2.0 and STIX 2.1 bundles are supported._

1. Put the stix bundles in `src/assets`. This will tell the server hosting the Navigator to host the data as well.
2. Edit the `config.json` file in the **nav-app/src/assets** directory.
3. Change the URL specified in the `data` array to the path to the STIX bundle (e.g `assets/enterprise-attack.json`). Multiple paths may be added to the `data` array to display multiple STIX bundles in a single instance.

Example loading content from local files:

```
"domains": [
    {
        "name": "Enterprise",
        "data": ["assets/enterprise-attack.json"]
    }
]
```

### Running the Docker File

1. Navigate to the **nav-app** directory
2. Run `docker build -t yourcustomname .`
3. Run `docker run -p 4200:4200 yourcustomname`
4. Navigate to `localhost:4200` in browser

### Loading Default Layers Upon Initialization

The Navigator can be configured so as to load a set of layers upon initialization. These layers can be from the web and/or from local files. Local files to load should be placed in the `nav-app/src/assets/` directory.

1. Set the `enabled` property in `default_layers` in `src/assets/config.json` to `true`
2.  Add the paths to your desired default layers to the `urls` array in `default_layers`. For example,

    ```
    "default_layers": {
         "enabled": true,
         "urls": [
             "assets/example.json", 
             "https://raw.githubusercontent.com/mitre-attack/attack-navigator/master/layers/data/samples/Bear_APT.json"
         ]
     }
    ```

    would load `example.json` from the local assets directory, and `Bear_APT.json` from this repo's sample layer folder on Github.
3. Load/reload the Navigator

Default layers from the web can also be set using a query string in the Navigator URL. Refer to the in-application help page section "Customizing the Navigator" for more details.

Users will not be prompted to upgrade default layers to the current version of ATT\&CK if they are outdated.

### Enabling Banner in Navigator

The `banner` setting in `nav-app/src/assets/config.json` by default is an empty string `"""` (and not visible), and can be set to whatever content you wish to display inside a banner at the top of the Navigator webpage. The banner supports HTML and hyperlinks in the content.

### Disabling Navigator Features

The `features` array in `nav-app/src/assets/config.json` lists Navigator features you may want to disable. Setting the `enabled` field on a feature in the configuration file will hide all control elements related to that feature.

However, if a layer is uploaded with an annotation or configuration relating to that feature it will not be hidden. For example, if `comments` are disabled the ability to add a new comment annotation will be removed, however if a layer is uploaded with comments present they will still be displayed in tooltips and and marked with an underline.

Features can also be disabled using the _create customized Navigator_ feature. Refer to the in-application help page section "Customizing the Navigator" for more details.

### Embedding the Navigator in a Webpage

If you want to embed the Navigator in a webpage, use an iframe:

```
<iframe src="https://mitre-attack.github.io/attack-navigator/enterprise/" width="1000" height="500"></iframe>
```

If you want to embed a version of the Navigator with specific features removed (e.g tabs, adding annotations), or with a default layer, we recommend using the _create customized Navigator_ feature. We highly recommend disabling the "leave site dialog" via this means when embedding the Navigator since otherwise you will be warned whenever you try to leave the embedding page. Refer to the in-application help page section "Customizing the Navigator" for more details.

The following is an example iframe which embeds our \*Bear APTs layer with tabs and the ability to add annotations removed:

```
<iframe src="https://mitre-attack.github.io/attack-navigator/enterprise/#layerURL=https%3A%2F%2Fraw.githubusercontent.com%2Fmitre%2Fattack-navigator%2Fmaster%2Flayers%2Fdata%2Fsamples%2FBear_APT.json&tabs=false&selecting_techniques=false" width="1000" height="500"></iframe>
```

### Related MITRE Work

**CTI**

[Cyber Threat Intelligence repository](https://github.com/mitre/cti) of the ATT\&CK catalog expressed in STIX 2.0 JSON.

**ATT\&CK**

ATT\&CK® is a curated knowledge base and model for cyber adversary behavior, reflecting the various phases of an adversary’s lifecycle and the platforms they are known to target. ATT\&CK is useful for understanding security risk against known adversary behavior, for planning security improvements, and verifying defenses work as expected.

[https://attack.mitre.org](https://attack.mitre.org)

**STIX**

Structured Threat Information Expression (STIX™) is a language and serialization format used to exchange cyber threat intelligence (CTI).

STIX enables organizations to share CTI with one another in a consistent and machine readable manner, allowing security communities to better understand what computer-based attacks they are most likely to see and to anticipate and/or respond to those attacks faster and more effectively.

STIX is designed to improve many different capabilities, such as collaborative threat analysis, automated threat exchange, automated detection and response, and more.

[https://oasis-open.github.io/cti-documentation/](https://oasis-open.github.io/cti-documentation/)

### Notice

Copyright 2020 The MITRE Corporation

Approved for Public Release; Distribution Unlimited. Case Number 18-0128.

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

[http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0)

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.

This project makes use of ATT\&CK®

[ATT\&CK® Terms of Use](https://attack.mitre.org/resources/terms-of-use/)
