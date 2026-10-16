# 南京工业大学开源软件仓库名录：许可证策略

供 [主站](https://github.com/He0xD4C0/njtech-oss-namelist) 匿名同步的完整许可证正文集合。黑白分类是本目录的收录政策，不是对软件合法性、安全性或所有使用场景的法律结论。

## 范围与来源

固定采用 [SPDX License List Data v3.29.0](https://github.com/spdx/license-list-data/releases/tag/v3.29.0)，提交为 `31ba1a50e5397e00a304dbadc76531740e89ee48`。

- 白名单覆盖该版本所有 `isOsiApproved=true` 的 154 个标识（含已弃用标识），另加 CC0-1.0，共 155 个 SPDX 标识；Unlicense 已在 OSI 集合内。
- 包含 GPL、LGPL、AGPL 等 copyleft 许可证。Copyleft 本身不是黑名单理由。
- 额外提供一份仅实例化独立版权声明的 MIT 正文，以适配网站对真实版权年份与持有人的规范化。另补充一份 GNU 官方 AGPL-3.0 HTTPS 正文变体，因此白名单目录有 157 份文件。
- 未纳入白名单不等于黑名单；未匹配的正文进入待处理。

黑名单共 9 份：

| SPDX 标识 | 选入理由 |
| --- | --- |
| SSPL-1.0 | OSI 未认可为开源许可证，其服务源码义务超出通常 copyleft 范围 |
| Elastic-2.0 | 限制作为托管或管理服务提供 |
| BUSL-1.1 | 生产用途受限，另有用途授予和许可转换机制 |
| CC-BY-NC-4.0 | 非商业限制 |
| CC-BY-NC-SA-4.0 | 非商业限制 |
| CC-BY-NC-ND-4.0 | 非商业及禁止分享演绎作品的限制 |
| CC-BY-ND-4.0 | 禁止分享演绎作品的限制 |
| PolyForm-Noncommercial-1.0.0 | 非商业限制 |
| PolyForm-Small-Business-1.0.0 | 使用主体规模限制 |

分类参考 [OSI 对 SSPL 的说明](https://opensource.org/blog/the-sspl-is-not-an-open-source-license)、[Elastic 正文](https://www.elastic.co/licensing/elastic-license/)、[MariaDB BUSL 1.1 正文](https://mariadb.com/bsl11/)、[Creative Commons 许可说明](https://creativecommons.org/share-your-work/cclicenses/) 及 [PolyForm 许可说明](https://polyformproject.org/licenses)。

BUSL 具体项目可能包含 Additional Use Grant、Change Date 和 Change License。本站不会依据许可证名称或日期推定当前授权，也不会自动判断已转换后的授权；应核对具体版本的完整正文并按实际授权维护策略。黑名单不是所有非 OSI 许可证的穷举。

## 目录与网站接入

```text
whitelist/     完整白名单正文，一份一个普通 UTF-8 文件
blacklist/     完整黑名单正文，一份一个普通 UTF-8 文件
sources.json   文件来源、SPDX 元数据、SHA-256 和明确记载的适配
README.md      说明；不进入策略编译
```

在网站的许可证策略源中设置 `https://github.com/He0xD4C0/njtech-oss-license-policy.git`，再触发“同步许可证策略”。网站读取默认分支，不需要 token。只有根目录两个名单目录下一级普通文件会被选中；文件名和扩展名不决定授权身份。不要在名单目录放 README、空占位文件、JSON、符号链接或嵌套目录。

正文每份最多 1 MiB，总计最多 16 MiB，文件数不超过 500。网站编译并激活自有 ScanCode 索引，失败时保留上次有效策略；不应向本仓库提交 pickle、编译索引或服务器缓存。

网站以所有候选文件的完整文本覆盖为准：全白名单可公开，全黑名单打回，混合/未知/改写/多余条款待处理，无候选打回。平台标签、SPDX 简称及高相似度不能代替完整覆盖。双重授权的混合结果仍待处理，不自动按 OR 选取一项。策略更新后按网站任务调度重新机审。

## 保留原文与必要适配

`sources.json` 为每份活动文件记录实际来源和 SHA-256。绝大多数文件逐字来自所固定的 SPDX 提交，未翻译、删节或添加说明。

两个已弃用标识 `GPL-2.0+`、`LGPL-2.1+` 使用同一 SPDX 提交中各自的后继 `GPL-2.0-or-later`、`LGPL-2.1-or-later` 正文。历史文本仅在附录示例占位符的尖括号及排版上不同；两种文本并存会触发 ScanCode 32.5 的重复词法规则错误。元数据保留历史来源、历史校验值和当前采用的后继来源，没有自行修改 GNU 许可条款。历史尖括号版本不承诺自动匹配，原样提交时仍可能进入待处理。

`MIT-copyright-notice.txt` 仅将上游 `Copyright (c) <year> <copyright holders>` 实例化为 `Copyright (c) 2026 Alice Example`。这是供扫描器识别并忽略的合成示例，不主张任何实际项目的著作权，其余条款保持原样。上游原版仍保留在 MIT.txt。

`AGPL-3.0-only-https.txt` 原样取自 [GNU 官方 AGPL-3.0 正文](https://www.gnu.org/licenses/agpl-3.0.txt)（2026-10-16 获取，SHA-256 见 `sources.json`）。与原有 SPDX 版本相比，网站规范化后的差异仅为两处 GNU 许可证链接从 HTTP 改为 HTTPS；三个受影响项目的正文与这份官方文本仅有换行差异。保留原有 HTTP 版本，并增加这一明确变体，不扩展任意 URL 替换或近似匹配的授权范围。

不把 SPDX 模板占位字段视为任意文本通配符。特别是写入条款中的组织名、产品名、额外授予或转换条件，不能仅凭相似名称放行。需要支持新的真实文本时，应审阅完整正文、核验来源和冲突，再添加明确变体。

## 维护边界

2026-10-16 已在 Linux amd64、ScanCode 32.5.0、网站 policy-text-v2 引擎上完成真实验证：166 份文件编译为 147 条去重规则，逐份扫描的黑白分类全部通过；另有 14 项补充检查，覆盖三个受影响项目的固定提交正文、AGPL HTTP/HTTPS 两种原文，以及无许可证、未知文本、黑白混合、附加商业限制、条款改写、未批准链接和版权声明变体。详细结果与引擎校验值见 [validation.json](validation.json)。这不等于生产站点已经同步或部署。

复验时在网站的 Linux scanner 环境读取两个目录构建路径到 UTF-8 正文的映射，调用 `licensecheck.engine.compile_policy(files, empty_directory)` 和 `validate_policy_artifacts`；随后将每份正文作为根目录 LICENSE 分别传入 `scan_candidates`，要求白名单返回 published、黑名单返回 rejected。对照 sources.json 校验每份文件 SHA-256。测试目录与生成缓存属于验证环境，不提交到本仓库。

第三方许可证文本及其自身的复制说明保持原有条件。本仓库收集某许可证，不表示本仓库整体或网站采用它。SPDX 标识与类别元数据用于追溯，不替代许可正文。

升级来源版本应显式审查变更，更新来源清单并重新执行真实扫描验证，不直接跟随上游 main 自动放行。相同正文不得同时进入黑白名单。许可证正文和网站用户协议分别维护；[EULA 仓库](https://github.com/He0xD4C0/njtech-oss-eula) 提供中英隐私政策、使用条款和收录规则。
