# Claims & Compliance Rules / 合规与敏感词规则

> 本文件是 Amazon Visual Designer 的合规基线。
> 所有生成的 Prompt、文案、图片标注中，**不得出现**以下列出的敏感词；
> 所有功能声明（claim）必须以 A 级强证据为前提，否则一律降级或删除。
> 编号体系沿用原始清单（保留原始跳号 74、94），便于与上游规则源对齐追溯。

---

## 目录

1. [敏感词完整清单（117 项）](#1-敏感词完整清单117-项)
2. [风险词处理原则](#2-风险词处理原则)
3. [高风险表达处理表](#3-高风险表达处理表)
4. [证据分级与声明权限](#4-证据分级与声明权限)
5. [替代表达建议表](#5-替代表达建议表)
6. [使用与检查流程](#6-使用与检查流程)

---

## 1. 敏感词完整清单（117 项）

> 说明：以下为全部禁用的英文敏感词。无论出现在 Prompt、图片文字标注、A+ 文案还是 Listing 标题/五点/描述中，**一律禁止使用**。
> 编号保留原始跳号（无 74、94），与上游规则源保持一致，便于追溯。
> 标注"替换词"的项，可使用括号中的建议替换；但**替换是否成立仍必须与真实产品一致**（见第 5 节）。

### 1.1 清单正文

| 编号 | 敏感词 | 备注 / 建议替换 |
|------|--------|------------------|
| 1 | Insecticidal | 杀虫类表述，禁用 |
| 2 | Anti-toxic | 抗毒类表述，禁用 |
| 3 | Anti-mildew | 防霉类表述，禁用 |
| 4 | waterproof | 替换词：water repellent（须与产品真实性能一致） |
| 5 | dustproof | 防尘类表述，禁用 |
| 6 | antifouling | 防污类表述，禁用 |
| 7 | preservatives | 防腐剂类表述，禁用 |
| 8 | sterilization | 灭菌类表述，禁用 |
| 9 | insecticide | 杀虫剂，禁用 |
| 10 | UV | 紫外线相关，禁用（功能声明场景） |
| 11 | Antimicrobial | 抗微生物，禁用 |
| 12 | Used to prevent | "用于预防"，禁用 |
| 13 | Eliminate | "消除"，禁用 |
| 14 | Repel or slow down any pest | 驱赶或减缓任何害虫，禁用 |
| 15 | Anti-oxidation | 抗氧化，禁用 |
| 16 | Mildew proof | 防霉，禁用 |
| 17 | Bacteriostatic | 抑菌，禁用 |
| 18 | Antibacterial | 抗菌，禁用 |
| 19 | anti-virus | 抗病毒，禁用 |
| 20 | filter air | 过滤空气，禁用 |
| 21 | resist ultraviolet rays | 抗紫外线，禁用 |
| 22 | Disinfect | 消毒，禁用 |
| 23 | prevent or inhibit the growth of bacteria | 预防或抑制细菌生长，禁用 |
| 24 | antifungal | 抗真菌，禁用 |
| 25 | allergens | 过敏原，禁用 |
| 26 | filters | 过滤器/过滤，禁用 |
| 27 | mites | 螨虫，禁用 |
| 28 | dust | 灰尘，禁用（功能声明场景） |
| 29 | insect repellent | 驱虫剂，禁用 |
| 30 | insects | 昆虫，禁用 |
| 31 | pests | 害虫，禁用 |
| 32 | Water filtration | 水过滤，禁用 |
| 33 | Anti-Mites | 防螨，禁用 |
| 34 | Inhibit-Algae | 抑藻，禁用 |
| 35 | Sanitize-Blight | 杀菌除疫，禁用 |
| 36 | Sterilize | 杀菌，禁用 |
| 37 | Insect prevention | 防虫，禁用 |
| 38 | Resistant for mosquitoes & ants | 抗蚊蚁，禁用 |
| 39 | Nontoxic | 无毒，禁用 |
| 40 | Healthy | 健康，禁用 |
| 41 | Environmental Protection | 环保，禁用 |
| 42 | Anti-Fouling | 防污，禁用 |
| 43 | disinfect | 消毒，禁用 |
| 44 | repel insects | 驱虫，禁用 |
| 45 | remove allergens | 去除过敏原，禁用 |
| 46 | prevent | 预防，禁用 |
| 47 | bacteria | 细菌，禁用（功能声明场景） |
| 48 | Antibacterial | 抗菌，禁用 |
| 49 | mildew | 霉菌，禁用 |
| 50 | resistant | 抗性，禁用（功能声明场景） |
| 51 | Anti-flu | 抗流感，禁用 |
| 52 | Ultraviolet | 紫外线，禁用 |
| 53 | light/UV | 光/UV，禁用 |
| 54 | germs | 病菌，禁用 |
| 55 | bug | 虫子，禁用 |
| 56 | Anti-Bacteria | 抗菌，禁用 |
| 57 | Stop-Microbe/Mildew | 阻断微生物/霉菌，禁用 |
| 58 | Destroy | 消灭，禁用 |
| 59 | Fungal/Fungus | 真菌，禁用 |
| 60 | Repel-Pesticides | 驱除农药，禁用 |
| 61 | Anti-fouling | 防污，禁用 |
| 62 | antifungal | 抗真菌，禁用 |
| 63 | antimicrobial | 抗微生物，禁用 |
| 64 | antifungal | 抗真菌，禁用 |
| 65 | antibacterial | 抗菌，禁用 |
| 66 | anti-fouling | 防污，禁用 |
| 67 | preventing | 预防，禁用 |
| 68 | destroying | 消灭，禁用 |
| 69 | repelling | 驱除，禁用 |
| 70 | mitigating any pest | 减轻任何害虫，禁用 |
| 71 | anti-mold | 防霉，禁用 |
| 72 | pesticide | 农药/杀虫剂，禁用 |
| 73 | resistant | 抗性，禁用 |
| 75 | non-toxic | 无毒，禁用 |
| 76 | odourless | 无味，禁用 |
| 77 | germs | 病菌，禁用 |
| 78 | safety | 安全，禁用（绝对化声明场景） |
| 79 | remove | 去除，禁用（功能声明场景） |
| 80 | residue | 残留，禁用 |
| 81 | sterilize | 杀菌，禁用 |
| 82 | disinfect | 消毒，禁用 |
| 83 | repel insects | 驱虫，禁用 |
| 84 | remove allergens | 去除过敏原，禁用 |
| 85 | drug | 药物，禁用 |
| 86 | antibiotic | 抗生素，禁用 |
| 87 | non-poisonous | 无毒，禁用 |
| 88 | all natural | 全天然，禁用 |
| 89 | mold | 霉菌，禁用 |
| 90 | anti | anti- 前缀，禁用（功能声明场景） |
| 91 | eco-friendly | 环保，禁用 |
| 92 | environment friendly | 环保，禁用 |
| 93 | moisture | 潮湿，禁用（功能声明场景） |
| 95 | infection | 感染，禁用 |
| 96 | toxic | 有毒，禁用 |
| 97 | hygience | 卫生，禁用 |
| 98 | BPA-Free | 不含 BPA，禁用（无认证证据时） |
| 99 | micro-bio | 微生物，禁用 |
| 100 | non-injurious | 无害，禁用 |
| 101 | Anti-Bacterial vinyl | 抗菌乙烯基，禁用 |
| 102 | repelient | 驱虫（拼写变体），禁用 |
| 103 | virus | 病毒，禁用 |
| 104 | mosquitos | 蚊子，禁用 |
| 105 | protect | 保护，禁用（功能声明场景） |
| 106 | chemical | 化学品，禁用 |
| 107 | hypoallergenic | 低致敏，禁用（无认证证据时） |
| 108 | mildew | 霉菌，禁用 |
| 109 | rat | 老鼠，禁用 |
| 110 | pest | 害虫，禁用 |
| 111 | rodent | 啮齿动物，禁用 |
| 112 | mouse | 老鼠，禁用 |
| 113 | harmless | 无害，禁用 |
| 114 | waterproof | 防水，禁用（须按替换词处理） |
| 115 | against mildew | 抗霉，禁用 |
| 116 | Durable | 替换词：Sturdy（须与产品真实性能一致） |
| 117 | enjoy | "享受"，禁用（易触发绝对化/体验声明） |

### 1.2 清单说明

- **大小写不敏感**：检查时统一转小写比对，`Antibacterial` 与 `antibacterial` 同等处理。
- **词形变体**：包括单复数、时态变体（如 `repelling`、`preventing`、`destroying`）均禁止。
- **拼写变体**：如 `repelient`（错误拼写）同样禁止，防止通过错字绕过。
- **组合词**：含 `anti-` 前缀的功能性组合词（如 `anti-mold`、`anti-fouling`）一律禁止。
- **场景例外**：极少数词在"非功能声明、纯客观描述材质/品类"时可能可用，但**默认禁止**，需人工复核并在 `05_claims_compliance_check.md` 中记录豁免理由。

---

## 2. 风险词处理原则

### 2.1 核心原则：不是机械替词

> **禁止把"替词"当作安全开关。** 把 `waterproof` 自动替换成 `water-resistant` 并不等于合规。

替词是否成立，取决于以下三要素，缺一不可：

1. **真实产品性能一致**：替代表达所描述的功能，必须是产品在真实测试中具备的。例如只有"拒水（water repellent）"性能的产品，不得使用"防水（waterproof）"，也不得夸大为"全防水"。
2. **证据等级达标**：见第 4 节。功能声明需 A 级强证据支撑。
3. **场景适配**：同一替代表达在主图、副图、A+、Listing 标题/五点中的风险不同，需逐场景复核。

**反模式（禁止做法）**：
- 用脚本做全局字符串替换，不校验产品真实性。
- 用同义词库自动改写，绕过敏感词扫描。
- 把禁用词翻译成其他语言再上链（如西语、日语 Listing）。

### 2.2 处理优先级

对每个风险词，按以下优先级处理：

| 优先级 | 处理方式 | 适用场景 |
|--------|----------|----------|
| P0 删除 | 直接删除该表达，不替换 | 无证据、无替代表达、属绝对化/医疗声明 |
| P1 降级 | 改为更弱、更客观的描述 | 有部分证据，但不达 A 级 |
| P2 替换 | 使用第 5 节的安全替代表达 | 有 A 级证据且与产品一致 |
| P3 保留 | 保留原文（仅限非功能声明的客观品类/材质词） | 经人工复核确认豁免 |

### 2.3 证据要求：A级强证据才可表达功能声明

任何功能声明（如拒水、遮光、降噪、耐用），必须满足"A 级强证据"才可在文案与图片标注中出现：

- **A 级（可表达）**：厂商提供的官方测试报告、第三方实验室报告、认证证书、可核验的产品规格书。
- **B 级（仅可弱化表达）**：厂商内部声明、未署名测试数据、行业惯例推断。仅可使用"设计用于…"等弱化措辞，且需在 `06_pending_questions.md` 标注待补证据。
- **C 级（禁止表达）**：无任何证据、仅凭外观猜测、竞品类比。

> 没有证据 = 没有声明。宁可少说，不可乱说。

---

## 3. 高风险表达处理表

> 以下是高频出现、极易触发审核或客诉的风险表达，及其默认处理方式和保守替代表达。
> **所有替代表达仍必须与真实产品一致，否则不得使用。**

| 风险词 | 默认处理 | 保守替代表达 | 触发条件 / 备注 |
|--------|----------|--------------|------------------|
| waterproof | P2 替换 | water repellent（仅当产品具备拒水性能） | 主图/副图/标题均禁用 waterproof；无拒水证据时改为 P0 删除 |
| blackout | P1 降级 | light-blocking / room-darkening（须与实测遮光率一致） | "100% blackout"属绝对化，禁用；需有遮光率测试数据 |
| thermal | P1 降级 | insulating / thermal-lined（须标明具体参数） | "thermal"暗示控温功能，无测试数据时禁用 |
| noise reducing | P1 降级 | sound-dampening（须有降噪测试） | "soundproof / noise canceling"属绝对化，禁用 |
| prevent | P0 删除 | help reduce（仅在有证据时） | "prevent"暗示医疗/防护功效，默认禁用 |
| eliminate | P0 删除 | help reduce / minimize（仅在有证据时） | "eliminate"属绝对化，默认禁用 |
| reduce | P1 降级 | help reduce（加 "help" 弱化） | 需有可量化证据；无证据时改 P0 删除 |
| durable | P2 替换 | sturdy / long-lasting（须与产品真实耐用性一致） | 原始清单第 116 项指定替换为 Sturdy |
| certified | P1 降级 | 须标注具体认证机构与编号 | 无证书原件时禁用；笼统说"certified"属违规 |
| non-toxic / Nontoxic | P0 删除 | 无安全替换 | 无毒声明属安全/健康类，需认证；默认禁用 |
| eco-friendly | P0 删除 | made with recycled materials（须有证据） | 笼统"环保"禁用；须具体说明环保属性与证据 |
| hypoallergenic | P0 删除 | 无安全替换 | 低致敏声明需认证，默认禁用 |
| BPA-Free | P0 删除 | 无安全替换 | 须有检测报告；无报告时禁用 |
| all natural | P0 删除 | 无安全替换 | "全天然"属绝对化，禁用 |
| 100% / absolute | P0 删除 | 无安全替换 | 绝对化用语，禁用 |
| FDA / CE / RoHS | P1 降级 | 须标注证书编号与机构 | 仅在持有有效证书时可用，且必须可核验 |

---

## 4. 证据分级与声明权限

### 4.1 证据分级标准

| 等级 | 定义 | 可声明范围 |
|------|------|------------|
| A 级 | 官方测试报告 / 第三方实验室报告 / 有效认证证书 / 厂商可核验规格书 | 可表达对应功能声明，使用第 5 节替代表达 |
| B 级 | 厂商内部声明 / 未署名数据 / 行业惯例推断 | 仅可用"designed to""help"等弱化措辞，并标注待补证据 |
| C 级 | 无证据 / 外观猜测 / 竞品类比 | 禁止任何功能声明 |

### 4.2 声明权限矩阵

| 声明类型 | 所需证据等级 | 允许的措辞强度 | 备注 |
|----------|--------------|----------------|------|
| 拒水 / 防泼水 | A 级 | water repellent | 须有拒水测试 |
| 遮光 | A 级 | room-darkening / light-blocking | 须有遮光率数据 |
| 降噪 | A 级 | sound-dampening | 须有降噪测试 |
| 耐用 | A 级 | sturdy / long-lasting | 须有耐用性测试或材质规格 |
| 保温 / 隔热 | A 级 | insulating | 须有热学测试 |
| 材质成分 | A 级 | 具体材质名 + 比例 | 须有成分检测报告 |
| 认证（FDA/CE 等） | A 级 | 认证名 + 编号 + 机构 | 须持有有效证书 |
| 尺寸 / 重量 | A 级 | 具体数值 + 单位 | 须有实测数据 |

---

## 5. 替代表达建议表

> 以下是常见禁用词的安全替代表达。
> **重要提示：替代表达仍必须和真实产品一致。** 若产品不具备该性能，连替代表达也不得使用。

| 禁用词 | 安全替代表达 | 适用前提（必须满足） |
|--------|--------------|----------------------|
| waterproof | water repellent | 产品具备拒水性能，且有 A 级证据 |
| Durable | Sturdy / long-lasting | 产品具备相应耐用性，且有 A 级证据 |
| blackout | room-darkening / light-blocking | 有遮光率测试数据，且措辞与数据一致 |
| thermal | insulating / thermal-lined | 有热学测试数据 |
| noise reducing | sound-dampening | 有降噪测试数据 |
| prevent | help reduce | 有可量化证据，且用 "help" 弱化 |
| eliminate | help reduce / minimize | 有可量化证据 |
| reduce | help reduce | 加 "help" 弱化，有证据 |
| non-toxic | （无安全替换） | 需认证；无认证时删除 |
| eco-friendly | made with recycled materials | 须有回收材料比例证据 |
| hypoallergenic | （无安全替换） | 需认证；无认证时删除 |
| BPA-Free | （无安全替换） | 需检测报告；无报告时删除 |
| all natural | （无安全替换） | 绝对化，删除 |
| antibacterial | （无安全替换） | 医疗/抗菌声明，删除 |
| sterilize / disinfect | （无安全替换） | 医疗声明，删除 |
| insect repellent | （无安全替换） | 驱虫声明，删除 |
| mildew proof / anti-mold | （无安全替换） | 防霉声明，删除 |
| UV / ultraviolet | （无安全替换，功能场景） | UV 防护声明，删除 |
| 100% / absolute | （无安全替换） | 绝对化，删除 |
| certified | 认证名 + 编号 + 机构 | 须持有有效证书 |

### 5.1 替代表达使用流程

1. **确认产品真实性能**：从 `01_product_truth_summary.md` 中核对产品事实。
2. **确认证据等级**：查第 4 节，确认达 A 级。
3. **选择替代表达**：从上表选择，确保措辞与证据数据一致。
4. **记录留痕**：在 `05_claims_compliance_check.md` 中记录"原词 → 替代表达 → 证据来源"。
5. **质检复核**：在 QC 阶段再次扫描，确认替代表达未误用。

---

## 6. 使用与检查流程

### 6.1 何时加载本文件

- 编写任何图片生成 Prompt 时（Phase 2）
- 编写图片文字标注时
- 编写 Listing 标题、五点、A+ 文案时
- 执行 QC 质检时（`references/qc_checklist.md` 调用）

### 6.2 检查流程

1. **生成前预检**：编写 Prompt / 文案时，逐词比对第 1 节清单。
2. **生成后扫描**：对生成的 Prompt 和图片中的文字执行敏感词扫描（大小写不敏感、含词形变体）。
3. **风险词复核**：命中第 3 节高风险表达时，按默认处理方式执行。
4. **证据核验**：对保留的功能声明，核验第 4 节证据等级。
5. **记录输出**：将所有处理结果写入 `05_claims_compliance_check.md`，格式如下：

```
| 原始表达 | 处理方式 | 替代表达 | 证据等级 | 证据来源 | 备注 |
|----------|----------|----------|----------|----------|------|
| waterproof | P2 替换 | water repellent | A 级 | 厂商拒水测试报告 2024-XX | 与产品一致 |
```

### 6.3 与其他规则文件的关系

| 关联文件 | 关系 |
|----------|------|
| `product_truth_rules.md` | 提供产品事实基线，是判断"替代表达是否与产品一致"的依据 |
| `prompt_template.md` | Prompt 的"合规约束层"引用本文件 |
| `qc_checklist.md` | QC 质检调用本文件执行敏感词扫描 |
| `amazon_image_rules.md` | 图片规范中的"禁止绝对化用语"与本文件联动 |

---

## 附：版本与维护

- 本清单编号沿用原始规则源（保留跳号 74、94），修改时不得重新编号，以免破坏追溯链。
- 新增敏感词时，续接最大编号追加，并在变更日志中记录。
- 替代表达建议表随亚马逊政策更新而调整，以当前 Seller Central 政策为准。
