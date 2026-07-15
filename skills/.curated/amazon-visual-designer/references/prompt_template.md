# 图片生成提示词模板（Prompt Template）

> 本文件是 Amazon Visual Designer 的核心参考文件之一。
> 当需要为 Listing 主图、副图、A+ 内容编写图片生成 Prompt 时加载本文件。
>
> 设计原则：
> 1. 高内聚低耦合 —— 产品不可变层与视觉表达层严格分离，产品事实锁定后不再改动。
> 2. 先策划后生图 —— 所有 Prompt 必须基于已锁定的产品事实，不得凭空编造。
> 3. 合规优先 -- 所有 Prompt 不得出现 `references/claims_compliance.md` 中列出的 115 个敏感词。

---

## 目录

1. [提示词三层结构](#1-提示词三层结构)
2. [统一产品描述模板](#2-统一产品描述模板)
3. [Negative Prompt 模板](#3-negative-prompt-模板)
4. [文字标注规范](#4-文字标注规范)
5. [实战经验教训](#5-实战经验教训)
6. [各类产品特殊约束模板](#6-各类产品特殊约束模板)
7. [完整 Prompt 组装示例](#7-完整-prompt-组装示例)

---

## 1. 提示词三层结构

每张图的 Prompt 必须严格区分以下三层。三层之间用明确的分隔标记，便于质检和调试。

### 第 1 层：产品不可变层（所有图共用）

- **作用范围**：全套图片（主图 + 副图）共用，一旦锁定不可更改。
- **内容**：真实产品的形状、颜色、图案、数量、结构、比例等客观事实。
- **字数**：约 200 字。
- **数据来源**：从已锁定的产品事实（`approved_image_plan.json` 中的 `product_truth`）提取。
- **核心规则**：本层内容必须 100% 来自真实产品资料，不得有任何编造。

```
【产品不可变层 — 开始】
{统一产品描述段落，约200字，见第2节模板}
【产品不可变层 — 结束】
```

> 注意：产品不可变层是所有图片一致性的基石。如果本层描述不准确，
> 后续所有图片都会出现产品造型不一致的问题。

### 第 2 层：视觉表达层（每张图不同）

- **作用范围**：每张图独立编写。
- **内容**：场景设定、构图方式、信息层级、文字标注、背景风格、拍摄角度等。
- **核心规则**：只描述"如何展示产品"，不得改变产品本身的任何属性。

```
【视觉表达层 — 开始】
- 场景：{如：厨房台面 / 客厅窗前 / 白底纯色}
- 构图：{如：居中正面 / 45度俯拍 / 局部特写}
- 信息层级：{如：产品为主体，文字标注在右上方}
- 文字标注：{如："108" × 54" | 1.6IN Grommet"}
- 背景：{如：纯白 #FFFFFF / 浅灰渐变}
- 光线：{如：柔光箱左侧打光 / 自然光}
【视觉表达层 — 结束】
```

### 第 3 层：合规约束层（所有图共用）

- **作用范围**：全套图共用，可按产品类型微调。
- **内容**：禁用表达清单、Negative Prompt。
- **核心规则**：参考 `references/claims_compliance.md` 中的 115 个敏感词，
  确保不出现任何违规表达。

```
【合规约束层 — 开始】
- 禁用表达：{列出本产品需禁用的敏感词，如 best, #1, FDA approved 等}
- Negative Prompt：{见第3节模板}
【合规约束层 — 结束】
```

---

## 2. 统一产品描述模板

### 目的

从参考图（真实产品白底图）和产品资料中提取关键特征，写成一段约 200 字的统一描述。
此描述作为"产品不可变层"，被所有图片共用，确保产品在每张图中保持一致。

### 提取流程

```
步骤 1：观察参考图（真实产品白底图）
  → 记录：整体形状、颜色、表面纹理、光泽类型
  → 记录：可见部件数量（按钮数、孔眼数、配件数）
  → 记录：结构特征（顶部结构类型、连接方式）

步骤 2：查阅产品资料（说明书、规格表）
  → 补充：精确尺寸（带单位）
  → 补充：包装数量
  → 补充：材质信息
  → 补充：包含/不包含清单

步骤 3：整合为统一描述段落（约200字）
  → 按下方模板填写
  → 用精确、可量化的语言
  → 避免模糊词（如"大约""差不多""可能"）
```

### 统一产品描述模板（填空式）

```
【统一产品描述】

产品为 {品牌} 品牌的 {产品类型}，整体呈 {形状描述}。
主体颜色为 {主色调}，{如有次要颜色/图案则描述}，
表面为 {光泽类型：如哑光matte / 拉丝缎面brushed satin / 高光镜面mirror polished} 质感。
{如有图案：描述图案类型、位置、密度}。

产品 {可见部件描述}：
- {部件1}：{数量} 个，{位置}，{形态描述}
- {部件2}：{数量} 个，{位置}，{形态描述}
- {如有控制面板：明确按钮数量、排列方式、每个按钮功能标识}

产品尺寸为 {长 × 宽 × 高/直径，带单位}。
包装内含 {数量} 件 {产品名称}。
材质为 {材质描述}。
{如有顶部结构：明确类型，如 grommet top 金属孔眼 / rod pocket 杆袋 / tab top 挂带}，
孔眼/配件材质为 {材质}，颜色为 {颜色}，光泽为 {光泽类型}。

包含：{列出所有包含的配件}。
不包含：{列出常见误以为包含但不包含的配件}。
```

### 示例：窗帘产品统一描述

```
【统一产品描述】

产品为 XYZHOME 品牌的窗帘（curtain panel），整体呈长方形垂坠布艺形态。
主体颜色为深灰色（dark gray），表面为哑光（matte）质感，无图案，纯色。
布料有自然垂坠褶皱，厚度中等，不透光（blackout）。

产品结构：
- 顶部结构：grommet top（金属孔眼顶部），共 8 个银色金属孔眼
- 孔眼材质：银色不锈钢（silver stainless steel），拉丝缎面光泽（brushed satin finish）
- 孔眼内径：1.6 英寸（1.6 inch inner diameter）
- 孔眼沿顶部均匀分布

产品尺寸为 52 英寸 × 108 英寸（宽 × 长，每片）。
包装内含 2 件窗帘（2 panels per package）。
材质为 100% 涤纶（100% polyester）三层编织遮光面料。

包含：2 × 窗帘面板。
不包含：窗帘杆（curtain rod）、安装配件。
```

> 注意：以上描述约 200 字。所有图片的"产品不可变层"直接引用此段落，
> 任何图都不得改变其中的产品属性。如果发现描述与某张图的视觉表达冲突，
> 应修改视觉表达层，而非修改产品不可变层。

---

## 2.5 产品锁段落（每张图必须包含）

> 注意：本节内容与 references/product_fidelity_lock.md 第5节一致，修改时需同步更新。

> 产品锁是保真锁定卡的 Prompt 版本，从 `references/product_fidelity_lock.md` 提取。
> 每张图的 Prompt 中必须原样包含此段落，放在产品不可变层之后、视觉表达层之前。
> 这是防止 AI 在生成时改变可量化细节的核心约束手段。

### 模板

```
【产品锁 — 不可更改，每张图必须包含】
- EXACTLY {数量} {部件} per {单位}, total {总数}
  (NOT {数量-1}, NOT {数量+1}, NOT {数量+2})
- {结构名称} ONLY
  (NOT {错误结构1}, NOT {错误结构2}, NOT {错误结构3})
- {尺寸描述}
  (NOT {错误尺寸描述})
- {材质描述}, {光泽类型}
  (NOT {错误光泽1}, NOT {错误光泽2})
- {颜色描述}
  (NOT {近似色1}, NOT {近似色2})
【产品锁 — 结束】
```

### 使用规则

1. **原样复制**：产品锁段落一旦从保真锁定卡生成，所有图片必须原样包含，不得修改。
2. **位置固定**：放在产品不可变层之后、视觉表达层之前。
3. **NOT 约束**：数量必须列出 `NOT 数量-1, NOT 数量+1` 等排除项，因为 AI 不会数数，需要明确排除错误数量。
4. **与保真锁定卡一致**：产品锁内容必须与保真锁定卡完全一致，不得有出入。

### 在三层结构中的位置

```
【产品不可变层 — 开始】
{统一产品描述段落，约200字}
【产品不可变层 — 结束】

【产品锁 — 不可更改，每张图必须包含】          ← 新增
- EXACTLY ...
- ... ONLY ...
- ...
【产品锁 — 结束】                              ← 新增

【视觉表达层 — 开始】
{每张图独立的场景、构图、文字标注}
【视觉表达层 — 结束】

【合规约束层 — 开始】
{禁用表达、Negative Prompt}
【合规约束层 — 结束】
```

> 注意：产品锁段落是"防翻车"的核心手段。即使 AI 忽略了产品不可变层中的描述，
> 产品锁中的 NOT 约束也能起到二次防御的作用。

---

## 3. Negative Prompt 模板

### 通用 Negative Prompt（所有产品共用）

以下为通用约束，适用于所有产品的所有图片：

```
【通用 Negative Prompt】
blurry, low quality, distorted, deformed, watermark, signature, logo overlay,
text artifacts, misspelled words, garbled text, extra limbs, floating objects,
unnatural shadows, oversaturated, cartoon, anime, 3d render, illustration,
painting, sketch, pixelated, noisy, grainy
```

### 按产品类型的 Negative Prompt 约束

> 使用规则：当产品需要某种特定形态时，用 NOT 约束排除容易混淆的错误形态。
> 这是实战中最有效的"防翻车"手段之一。

#### 窗帘/布艺类产品

```
# 当需要 grommet top（金属孔眼）时：
NOT rod pocket, NOT tab top, NOT back tab, NOT pleated tape,
NOT gold grommet, NOT bronze grommet, NOT black grommet,
NOT shiny mirror polished grommet, NOT plastic grommet,

# 当需要 rod pocket（杆袋）时：
NOT grommet top, NOT tab top, NOT clip ring,

# 孔眼颜色约束（当需要银色时）：
NOT gold, NOT bronze, NOT brass, NOT copper, NOT rose gold,
NOT shiny mirror polished (when brushed satin is needed),
NOT matte rubber (when metal is needed),
```

#### 家电类产品

```
# 按钮数量约束（当需要4个按钮时）：
NOT 3 buttons, NOT 5 buttons, NOT 6 buttons, NOT 8 buttons,
extra buttons, missing buttons,

# 控制面板约束：
NOT analog dial (when digital display is needed),
NOT touchscreen (when physical buttons are needed),
NOT LED display (when LCD is needed),

# 材质约束：
NOT plastic body (when stainless steel is needed),
NOT white finish (when black is needed),
NOT chrome (when brushed steel is needed),
```

#### 通用材质/颜色约束

```
# 金属表面光泽（当需要拉丝缎面时）：
NOT shiny mirror polished, NOT chrome plated, NOT glossy,
NOT matte powder coated (when brushed satin is needed),

# 颜色约束（当需要银色时）：
NOT gold, NOT bronze, NOT brass, NOT rose gold, NOT copper,

# 颜色约束（当需要黑色时）：
NOT silver, NOT white, NOT gray (when pure black is needed),
```

### Negative Prompt 使用原则

1. **针对性**：只约束与本产品当前需求冲突的形态，不要无差别堆砌。
2. **精准描述**：用具体的形态词（如 `rod pocket`），不要用模糊词（如 `wrong top`）。
3. **成对使用**：指定需要的形态 + NOT 排除错误形态，双重保险。
4. **与产品不可变层一致**：Negative Prompt 必须与第 1 层产品描述保持一致，
   不得矛盾。

---

## 4. 文字标注规范

### 基本原则

AI 生成文字的可靠性远低于生成图像。因此文字标注必须遵循以下原则，
最大程度降低拼写错误和排版问题。

### 文字标注规则

| 规则 | 要求 | 原因 |
|------|------|------|
| 字号 | 英文字符至少 36px，推荐 48-72px | 确保缩放后可读 |
| 内容类型 | 优先使用简单数字和短词 | AI 容易拼错长单词 |
| 句子长度 | 避免长句，每段不超过 3 个单词 | 长句拼写错误率高 |
| 字体 | 白色或黑色粗体 sans-serif | 高对比度，可读性好 |
| 位置 | 叠加在产品上或留白区域 | 避免与产品细节冲突 |
| 数字格式 | 使用简单写法：108, 54, 1.6IN | 避免特殊符号 |

### 推荐的文字标注类型

```
# 尺寸标注（最推荐，纯数字）
"52" × 108""          → 窗帘尺寸
"1.6IN"               → 孔眼内径
"120V / 60Hz"         → 电气参数

# 数量标注
"2 PANELS"            → 包装数量
"PACK OF 6"           → 包装数量

# 短词标注（≤3个单词）
"BLACKOUT"            -> 功能特性
"EASY INSTALL"        -> 卖点
"ROOM DARKENING"      -> 功能特性
```

> 注："100%"属绝对化用语（P0禁用），"blackout"需降级为 "room darkening" 或 "light blocking"（须与实测遮光率一致）。上方 "BLACKOUT" 标注同理：无实测遮光率数据时应降级为 "ROOM DARKENING" 或 "LIGHT BLOCKING"。

### 应避免的文字标注

```
# 长句（AI 容易拼错）
"Experience the ultimate blackout protection for your bedroom"
-> 改为："ROOM DARKENING"

# 含敏感词的标注
"The best curtains for your home"
→ "best" 是敏感词，删除

# 复杂专有名词
"Triple-Weave Thermal Insulated Technology"
→ 改为："THERMAL" 或 "INSULATED"（短词）
```

### 文字叠加的 Prompt 写法

```
# 在视觉表达层中描述文字标注时，按以下格式：
- 文字标注1：大号白色粗体 "108""，位于产品右侧留白区
- 文字标注2：中号黑色粗体 "1.6IN"，位于孔眼特写旁
- 文字标注3：大号白色粗体 "2 PANELS"，位于底部居中

# 对应的 Negative Prompt 补充：
misspelled text, garbled letters, reversed text, overlapping text,
tiny text, blurry text
```

---

## 5. 实战经验教训

> 以下内容基于实际生图经验总结，每条都包含"翻车现象"和"避免方法"。

### 教训 1：产品造型不一致

- **翻车现象**：各张图中的产品看起来像不同的产品，形状、颜色、细节各不相同。
- **根本原因**：每张图的 Prompt 独立编写，产品描述不统一。
- **避免方法**：
  1. 使用第 2 节的统一产品描述模板，提取约 200 字的"产品不可变层"。
  2. 所有图片的 Prompt 都引用同一段产品描述。
  3. 产品描述要精确到数量、尺寸、颜色色值、光泽类型。
  4. 质检时逐张对比参考图，发现偏差立即修正。

### 教训 2：控制面板按钮数量错误

- **翻车现象**：真实产品有 4 个按钮，生成的图中有 3 个、5 个或 6 个按钮。
- **根本原因**：Prompt 中没有明确按钮数量和布局。
- **避免方法**：
  1. 在产品不可变层中明确写出："控制面板含 4 个圆形按钮，横向排列"。
  2. 在视觉表达层中重申："清晰显示 4 个按钮，从左到右"。
  3. 在 Negative Prompt 中排除错误数量：`NOT 3 buttons, NOT 5 buttons`。
  4. 如果是特写图，逐个描述按钮标识（如 Power / Timer / Speed / Light）。

### 教训 3：孔眼/配件形态不对

- **翻车现象**：需要银色拉丝孔眼，生成的是金色亮面孔眼；需要金属孔眼，生成的是塑料杆袋。
- **根本原因**：AI 倾向于生成"常见"形态，而非指定形态。
- **避免方法**：
  1. 在产品不可变层中精确描述："grommet top，银色不锈钢，拉丝缎面光泽"。
  2. 在 Negative Prompt 中用 NOT 排除错误形态：
     `NOT rod pocket, NOT gold grommet, NOT shiny mirror polished`。
  3. 质检时重点检查孔眼颜色、材质、光泽是否与参考图一致。

### 教训 4：场景图顶部结构错误

- **翻车现象**：产品是 grommet top 窗帘，场景图中窗帘挂在杆上时顶部变成了 rod pocket。
- **根本原因**：场景描述中没有强制指定顶部结构类型。
- **避免方法**：
  1. 在视觉表达层中明确："窗帘通过 grommet top 孔眼穿过金属杆悬挂"。
  2. 在产品不可变层中已锁定的顶部结构类型，在视觉表达层中重申。
  3. 在 Negative Prompt 中排除：`NOT rod pocket hanging style`。
  4. 质检时特别关注场景图中产品顶部结构的呈现。

### 教训 5：AI 生成文字拼写错误

- **翻车现象**：标注 "BLACKOUT" 生成成了 "BLAKOUT" 或 "BLACKUOT"；长句几乎必有拼写错误。
- **根本原因**：AI 文字生成能力有限，长单词和长句错误率高。
- **避免方法**：
  1. 尽量使用简单数字（108, 54, 1.6IN），数字几乎不会出错。
  2. 短词不超过 3 个字母组合，如 "2 PANELS"。
  3. 避免长句和复杂专有名词。
  4. 字号至少 36px，大字号更不容易出错。
  5. 如果文字必须准确，考虑后期在图片上手动叠加文字层。

### 教训 6：产品颜色偏色

- **翻车现象**：真实产品是深灰色，生成的图偏蓝或偏紫。
- **避免方法**：
  1. 在产品描述中使用英文色名 + 中文注释，如 "dark gray (not blue, not purple)"。
  2. 在 Negative Prompt 中排除偏色：`NOT blue tint, NOT purple tint`。
  3. 质检时与参考图并排对比颜色。

### 教训 7：配件多余或缺失

- **翻车现象**：产品不包含安装螺丝，但图中出现了螺丝；或产品包含 2 片窗帘，图中只有 1 片。
- **避免方法**：
  1. 在产品不可变层中明确"包含"和"不包含"清单。
  2. 在 Negative Prompt 中排除不包含的物品：
     `NOT screws, NOT hardware kit, NOT tiebacks (when not included)`。
  3. 质检时对照"包含/不包含"清单逐项检查。

---

## 6. 各类产品特殊约束模板

### 6.1 家电类产品特殊约束

适用产品：厨房电器、生活电器、个人护理电器等。

```
【家电类 — 产品不可变层补充】

控制面板：
- 按钮总数：{数量} 个
- 排列方式：{横向排列 / 纵向排列 / 网格排列}
- 每个按钮标识：{如：Power | Timer | Speed | Light}
- 按钮形状：{圆形 / 方形 / 触摸式}
- 按钮颜色：{颜色}

显示屏（如有）：
- 类型：{LED / LCD / 无屏幕}
- 显示内容：{如：数字时间 / 温度}
- 位置：{面板上方 / 居中}

品牌 Logo：
- 位置：{正面下方 / 顶部居中 / 控制面板旁}
- 颜色：{银色 / 黑色}
- 尺寸比例：{相对于产品的大小}

接口/端口（如有）：
- 类型和数量：{如：USB-C × 1, HDMI × 2}
- 位置：{背面 / 侧面}

【家电类 — Negative Prompt 补充】
NOT {错误按钮数量} buttons,
NOT touchscreen (when physical buttons needed),
NOT analog dial (when digital display needed),
extra buttons, missing buttons,
NOT different brand logo,
```

### 6.2 窗帘/布艺类产品特殊约束

适用产品：窗帘、浴帘、桌布、窗帘配件等。

```
【窗帘/布艺类 — 产品不可变层补充】

顶部结构（必须明确，这是窗帘最关键的特征）：
- 类型：{grommet top / rod pocket / tab top / back tab / pleated tape}
- 如果是 grommet top：
  - 孔眼数量：{数量} 个
  - 孔眼材质：{不锈钢 / 锌合金 / 塑料}
  - 孔眼颜色：{银色 / 黑色 / 古铜色}
  - 孔眼光泽：{拉丝缎面 brushed satin / 高光镜面 mirror polished / 哑光 matte}
  - 孔眼内径：{尺寸，如 1.6 inch}
- 如果是 rod pocket：
  - 杆袋宽度：{尺寸}
  - 有无后背标签（back tab）：{有 / 无}

布料特征：
- 厚度：{轻薄 / 中等 / 厚重}
- 透光度：{遮光 blackout / 半遮光 room darkening / 透光 sheer}
- 垂坠感：{自然褶皱 / 挺括}
- 表面纹理：{光滑 / 有纹理 / 织纹}

尺寸标注规范：
- 标注格式：宽 × 长，如 "52" × 108""
- 单位：英寸（inch）
- 标注位置：图中留白区，大号粗体

【窗帘/布艺类 — Negative Prompt 补充】
# 根据实际顶部结构类型选择：
# grommet top 时：
NOT rod pocket, NOT tab top, NOT back tab,
NOT gold grommet, NOT bronze grommet, NOT black grommet (when silver needed),
NOT shiny mirror polished (when brushed satin needed),
NOT plastic grommet (when metal needed),

# rod pocket 时：
NOT grommet top, NOT tab top,

# 通用：
NOT sheer fabric (when blackout needed),
NOT thin fabric (when heavy weight needed),
NOT curtain rod, NOT hardware (when not included),
```

### 6.3 通用约束模板

适用所有产品类型的通用约束。

```
【通用 — 产品不可变层补充】

颜色：
- 主色调：{英文色名 + 中文，如 dark gray 深灰}
- 次要颜色：{如有}
- 禁止偏色：{列出容易混淆的偏色，如 NOT blue tint, NOT purple tint}

材质：
- 主体材质：{如 100% polyester / 304 stainless steel / ABS plastic}
- 表面处理：{如 brushed / polished / matte / textured}

数量：
- 包装内数量：{数字}
- 可见部件数量：{逐项列出}

尺寸/比例：
- 产品尺寸：{长 × 宽 × 高，带单位}
- 比例特征：{如 长宽比 2:1}

【通用 — Negative Prompt 补充】
NOT {错误颜色},
NOT {错误材质},
NOT {错误数量},
wrong proportions, distorted shape,
```

---

## 7. 完整 Prompt 组装示例

以下是一个完整的窗帘副图 Prompt 组装示例，展示三层结构如何拼接。

```
==================================================
图片编号：listing-03（尺寸特写图）
==================================================

【产品不可变层 — 开始】
产品为 XYZHOME 品牌的窗帘（curtain panel），整体呈长方形垂坠布艺形态。
主体颜色为深灰色（dark gray），表面为哑光（matte）质感，无图案，纯色。
布料有自然垂坠褶皱，厚度中等，不透光（blackout）。
顶部结构为 grommet top（金属孔眼顶部），共 8 个银色金属孔眼，
孔眼材质为银色不锈钢（silver stainless steel），拉丝缎面光泽（brushed satin finish），
孔眼内径为 1.6 英寸（1.6 inch inner diameter），孔眼沿顶部均匀分布。
产品尺寸为 52 英寸 × 108 英寸（宽 × 长，每片）。包装内含 2 件窗帘。
材质为 100% 涤纶三层编织遮光面料。
包含：2 × 窗帘面板。不包含：窗帘杆、安装配件。
【产品不可变层 — 结束】

【视觉表达层 — 开始】
- 场景：纯白背景（#FFFFFF），产品局部特写
- 构图：聚焦窗帘顶部 grommet top 孔眼区域，45度角度展示孔眼穿过金属杆的细节
- 信息层级：孔眼特写为主体，尺寸标注在右侧留白区
- 文字标注1：大号白色粗体 "1.6IN"，位于孔眼特写旁，标注孔眼内径
- 文字标注2：中号黑色粗体 "52" × 108""，位于底部居中，标注产品尺寸
- 文字标注3：大号白色粗体 "8 GROMMETS"，位于顶部留白区
- 光线：柔光箱左侧打光，突出孔眼拉丝缎面质感
- 背景：纯白，无阴影干扰
【视觉表达层 — 结束】

【合规约束层 — 开始】
- 禁用表达：best, #1, top quality, FDA approved, energy saving, eco-friendly
  （参考 references/claims_compliance.md 完整清单）
- Negative Prompt：
  blurry, low quality, distorted, watermark, signature,
  misspelled text, garbled letters, reversed text, overlapping text, tiny text,
  NOT rod pocket, NOT tab top, NOT back tab,
  NOT gold grommet, NOT bronze grommet, NOT black grommet,
  NOT shiny mirror polished (brushed satin needed),
  NOT plastic grommet (metal needed),
  NOT sheer fabric (blackout needed),
  NOT curtain rod, NOT hardware, NOT screws,
  NOT blue tint, NOT purple tint,
  cartoon, anime, 3d render, illustration, painting, sketch
【合规约束层 — 结束】

==================================================
默认尺寸：1600 × 1600 px（方形）
==================================================
```

> 以上示例展示了完整的三层结构组装方式。实际使用时：
> - 产品不可变层直接复用统一产品描述（不改字）
> - 视觉表达层每张图独立编写
> - 合规约束层基本复用，按图微调

---

## 8. A+ 内容 Prompt 模板

> A+ 内容（A+ Content / Enhanced Brand Content）是 Amazon 品牌卖家在商品详情页中
> 可使用的富媒体图文模块。与 Listing 主图、副图相比，A+ 内容图片通常尺寸更大、
> 文字更多、构图更复杂，且需要同时适配桌面版（Desktop）和移动版（Mobile）两种展示场景。
> 本节提供 A+ 内容图片的专用 Prompt 模板，与 Listing 图共用产品不可变层和产品锁段落，
> 仅视觉表达层和合规约束层根据 A+ 特点独立编写。

### 8.1 概述

A+ 内容图片的 Prompt 同样遵循三层结构 + 产品锁的整体框架：

- **产品不可变层**：与 Listing 主图、副图完全一致，直接复用第 2 节的统一产品描述段落，
  不做任何修改。
- **产品锁段落**：与 Listing 图完全一致，直接复用第 2.5 节的产品锁模板，原样包含。
- **视觉表达层（A+ 专属）**：根据 A+ 桌面版/移动版的不同尺寸和构图特点独立编写，
  是本节的核心内容。
- **合规约束层（A+ 专属）**：在通用合规约束基础上，增加 A+ 专属的尺寸方向约束和
  文字可读性约束。

> 注意：A+ 内容图片的产品保真要求与 Listing 图完全一致。产品不可变层和产品锁段落
> 不得因为 A+ 图片尺寸更大而做任何调整。如果 A+ 图片中出现产品造型偏差，
> 仍然只能修改视觉表达层，不得改动产品不可变层和产品锁。

---

### 8.2 Desktop Prompt 模板（1464 × 600 或 1940 × 1200）

A+ 桌面版图片为横向宽幅 banner 格式，采用左右分区构图，适合展示场景全景和较丰富的信息。默认尺寸 1464 × 600，也可选择 1940 × 1200 大尺寸规格。

#### 8.2.1 Desktop 模板

```
【A+ 视觉表达层 — Desktop — 开始】
- 尺寸：horizontal 1464 × 600 px, wide landscape banner format
- 构图：left-right split composition（横向左右分区构图）
  - 左侧（约 50%-60% 宽度）：产品主体展示区，产品居中或偏左放置
  - 右侧（约 40%-50% 宽度）：信息/场景区，文字标注和辅助场景
- 文字规范：text at least 36px, bold sans-serif font, high contrast（白色或黑色）
- 文字位置：右侧信息区，垂直居中或顶部对齐
- 背景风格：gradient or brand color block transitions（渐变或品牌色块过渡）
  - 左侧可为纯白或浅色，右侧可过渡到品牌色或场景色
- 光线：均匀柔光，确保产品细节清晰
- 信息密度：可容纳 2-3 个文字标注和 1 个辅助图标/场景元素
【A+ 视觉表达层 — Desktop — 结束】
```

#### 8.2.2 Desktop 组装示例（窗帘产品）

以下为窗帘产品的 A+ Desktop 完整 Prompt 组装示例：

```
==================================================
图片编号：aplus-desktop-01（场景展示 Desktop 版）
==================================================

【产品不可变层 — 开始】
产品为 XYZHOME 品牌的窗帘（curtain panel），整体呈长方形垂坠布艺形态。
主体颜色为深灰色（dark gray），表面为哑光（matte）质感，无图案，纯色。
布料有自然垂坠褶皱，厚度中等，不透光（blackout）。
顶部结构为 grommet top（金属孔眼顶部），共 8 个银色金属孔眼，
孔眼材质为银色不锈钢（silver stainless steel），拉丝缎面光泽（brushed satin finish），
孔眼内径为 1.6 英寸（1.6 inch inner diameter），孔眼沿顶部均匀分布。
产品尺寸为 52 英寸 × 108 英寸（宽 × 长，每片）。包装内含 2 件窗帘。
材质为 100% 涤纶三层编织遮光面料。
包含：2 × 窗帘面板。不包含：窗帘杆、安装配件。
【产品不可变层 — 结束】

【产品锁 — 不可更改，每张图必须包含】
- EXACTLY 8 grommets per panel, total 16 grommets (2 panels)
  (NOT 6, NOT 7, NOT 9, NOT 10)
- grommet top ONLY
  (NOT rod pocket, NOT tab top, NOT back tab)
- 52" × 108" per panel
  (NOT 63", NOT 84", NOT 95")
- silver stainless steel, brushed satin finish
  (NOT shiny mirror polished, NOT chrome plated)
- dark gray
  (NOT blue tint, NOT purple tint, NOT light gray)
【产品锁 — 结束】

【A+ 视觉表达层 — Desktop — 开始】
- 尺寸：horizontal 1464 × 600 px, wide landscape banner format
- 构图：left-right split composition
  - 左侧（约 55%）：窗帘悬挂在窗前的客厅场景，自然光透过窗帘，
    展示垂坠质感和遮光效果
  - 右侧（约 45%）：深灰渐变背景上的信息区
- 文字标注1：大号白色粗体 "ROOM DARKENING"，位于右上方
- 文字标注2：中号白色粗体 "52" × 108""，位于右侧中部
- 文字标注3：中号白色粗体 "2 PANELS"，位于右下方
- 背景风格：左侧自然光客厅场景 → 右侧深灰渐变色块过渡
- 光线：左侧自然光，右侧均匀柔光
【A+ 视觉表达层 — Desktop — 结束】

【合规约束层 — 开始】
- 禁用表达：best, #1, top quality, FDA approved, energy saving, eco-friendly
  （参考 references/claims_compliance.md 完整清单）
- Negative Prompt：
  blurry, low quality, distorted, watermark, signature,
  misspelled text, garbled letters, reversed text, tiny text,
  NOT vertical layout, NOT square, NOT portrait orientation,
  NOT rod pocket, NOT gold grommet, NOT shiny mirror polished,
  NOT sheer fabric (blackout needed),
  NOT blue tint, NOT purple tint,
  cartoon, anime, 3d render, illustration
【合规约束层 — 结束】

==================================================
默认尺寸：1464 × 600 px（横版 Desktop）
==================================================
```

---

### 8.3 Mobile Prompt 模板（1600 × 1200）

A+ 移动版图片为纵向 4:3 格式，采用上下分区构图，文字更大、信息更精简，确保小屏可读。

#### 8.3.1 Mobile 模板

```
【A+ 视觉表达层 — Mobile — 开始】
- 尺寸：vertical 1600 × 1200 px, portrait 4:3 format
- 构图：top-bottom split composition（纵向上下分区构图）
  - 上方（约 60%-65% 高度）：产品主体展示区，产品居中放置
  - 下方（约 35%-40% 高度）：信息/文字区
- 文字规范：text at least 48px (larger than desktop), bold sans-serif font, high contrast
  - 移动版文字必须比 Desktop 更大，确保小屏幕可读
- 文字位置：下方信息区，水平居中
- 背景风格：上下渐变或色块过渡，上方可为场景色，下方可为品牌色
- 信息精简原则：less text than desktop, fewer elements
  - 移动版最多 2 个文字标注，避免信息过载
- 光线：均匀柔光，突出产品主体
【A+ 视觉表达层 — Mobile — 结束】
```

#### 8.3.2 Mobile 组装示例（窗帘产品）

以下为窗帘产品的 A+ Mobile 完整 Prompt 组装示例：

```
==================================================
图片编号：aplus-mobile-01（场景展示 Mobile 版）
==================================================

【产品不可变层 — 开始】
产品为 XYZHOME 品牌的窗帘（curtain panel），整体呈长方形垂坠布艺形态。
主体颜色为深灰色（dark gray），表面为哑光（matte）质感，无图案，纯色。
布料有自然垂坠褶皱，厚度中等，不透光（blackout）。
顶部结构为 grommet top（金属孔眼顶部），共 8 个银色金属孔眼，
孔眼材质为银色不锈钢（silver stainless steel），拉丝缎面光泽（brushed satin finish），
孔眼内径为 1.6 英寸（1.6 inch inner diameter），孔眼沿顶部均匀分布。
产品尺寸为 52 英寸 × 108 英寸（宽 × 长，每片）。包装内含 2 件窗帘。
材质为 100% 涤纶三层编织遮光面料。
包含：2 × 窗帘面板。不包含：窗帘杆、安装配件。
【产品不可变层 — 结束】

【产品锁 — 不可更改，每张图必须包含】
- EXACTLY 8 grommets per panel, total 16 grommets (2 panels)
  (NOT 6, NOT 7, NOT 9, NOT 10)
- grommet top ONLY
  (NOT rod pocket, NOT tab top, NOT back tab)
- 52" × 108" per panel
  (NOT 63", NOT 84", NOT 95")
- silver stainless steel, brushed satin finish
  (NOT shiny mirror polished, NOT chrome plated)
- dark gray
  (NOT blue tint, NOT purple tint, NOT light gray)
【产品锁 — 结束】

【A+ 视觉表达层 — Mobile — 开始】
- 尺寸：vertical 1600 × 1200 px, portrait 4:3 format
- 构图：top-bottom split composition
  - 上方（约 60%）：窗帘悬挂在窗前场景，竖向聚焦展示垂坠质感
  - 下方（约 40%）：深灰渐变背景信息区
- 文字标注1：特大号白色粗体 "ROOM DARKENING"，位于下方居中
- 文字标注2：大号白色粗体 "2 PANELS"，位于下方底部
- 背景风格：上方自然光场景 → 下方深灰渐变色块过渡
- 光线：上方自然光，下方均匀柔光
【A+ 视觉表达层 — Mobile — 结束】

【合规约束层 — 开始】
- 禁用表达：best, #1, top quality, FDA approved, energy saving, eco-friendly
  （参考 references/claims_compliance.md 完整清单）
- Negative Prompt：
  blurry, low quality, distorted, watermark, signature,
  misspelled text, garbled letters, reversed text, tiny text,
  NOT horizontal layout, NOT wide banner, NOT landscape orientation,
  NOT rod pocket, NOT gold grommet, NOT shiny mirror polished,
  NOT sheer fabric (blackout needed),
  NOT blue tint, NOT purple tint,
  cartoon, anime, 3d render, illustration
【合规约束层 — 结束】

==================================================
默认尺寸：1600 × 1200 px（竖版 Mobile）
==================================================
```

---

### 8.4 Desktop vs Mobile 构图差异对照表

> 注意：本表与 references/aplus_content_guide.md 第6节内容一致，修改时需同步更新。

同一主题在桌面版和移动版上的关键差异如下：

| 维度 | Desktop | Mobile |
|------|---------|--------|
| 构图方向 | 横向左右分区（left-right split） | 纵向上下分区（top-bottom split） |
| 产品位置 | 左侧 | 上方居中 |
| 文字位置 | 右侧 | 下方 |
| 文字大小 | ≥ 36px | ≥ 48px |
| 信息密度 | 可较高 | 必须精简 |
| 场景宽度 | 宽幅全景（wide panorama） | 竖向聚焦（vertical focus） |
| 色块使用 | 可左右渐变 | 可上下渐变 |
| 尺寸比例 | 1464 × 600（约 2.44:1）或 1940 × 1200（约 1.62:1） | 1600 × 1200（4:3） |
| 文字标注数量 | 2-3 个 | 最多 2 个 |

> 注意：同一主题的 Desktop 版和 Mobile 版必须共用相同的产品不可变层和产品锁段落，
> 只有视觉表达层和合规约束层中的尺寸方向约束不同。切勿在两版之间改动产品属性。

---

### 8.5 A+ Prompt 组装顺序

A+ 内容 Prompt 的完整组装方式与 Listing 图一致，遵循以下拼接顺序：

```
[产品不可变层] + [产品锁段落] + [A+视觉表达层] + [合规约束层] + [negative prompt]
```

各段落说明：

1. **产品不可变层**：直接复用第 2 节统一产品描述，不改字。
2. **产品锁段落**：直接复用第 2.5 节产品锁模板，原样包含。
3. **A+ 视觉表达层**：根据 Desktop（8.2）或 Mobile（8.3）选择对应模板填写。
4. **合规约束层**：通用合规约束 + A+ 专属约束（见 8.6）。
5. **Negative Prompt**：通用 Negative Prompt + A+ 专属 Negative Prompt。

> 组装顺序固定不变。产品不可变层和产品锁段落必须在最前面，确保 AI 最先读取
> 产品事实约束；视觉表达层在中间，描述如何展示；合规约束层和 Negative Prompt 在最后，
> 排除违规和错误形态。

---

### 8.6 A+ 专属 Negative Prompt

A+ 内容图片由于尺寸和方向特殊，需要在通用 Negative Prompt 基础上增加专属约束。

#### 8.6.1 Desktop 专属 Negative Prompt

```
# Desktop 版方向约束（防止生成竖版或方形图）：
NOT vertical layout, NOT square, NOT portrait orientation,

# Desktop 版尺寸约束：
NOT wide vertical banner, NOT centered square composition,
```

#### 8.6.2 Mobile 专属 Negative Prompt

```
# Mobile 版方向约束（防止生成横版或宽幅图）：
NOT horizontal layout, NOT wide banner, NOT landscape orientation,

# Mobile 版尺寸约束：
NOT left-right split composition, NOT horizontal text alignment at top,
```

#### 8.6.3 A+ 通用 Negative Prompt

```
# 文字可读性约束（A+ 图片文字多，拼写风险高）：
NOT tiny text, NOT garbled text, NOT watermark,
misspelled words, reversed text, overlapping text, blurry text,

# 信息过载约束：
NOT too many text labels, NOT cluttered layout, NOT overcrowded elements,
```

---

### 8.7 A+ 文字标注注意事项

A+ 内容图片通常比 Listing 图包含更多文字，拼写错误和排版风险更高。以下为 A+ 专属注意事项：

1. **文字量更大，风险更高**：A+ 图片中文字标注数量通常多于 Listing 副图，
   AI 拼写错误概率随文字量增加而上升。需格外注意质检。

2. **建议使用短词和数字**：尽量使用不超过 3 个单词的短词组合和纯数字标注，
   如 "ROOM DARKENING"、"2 PANELS"、"52" × 108""。避免长句和复杂专有名词。

3. **移动版文字必须更大**：Mobile 版文字至少 48px，比 Desktop 的 36px 更大，
   确保在手机小屏幕上清晰可读。信息密度必须精简，最多 2 个文字标注。

4. **考虑后期 PS 叠加文字层策略**：当文字内容较多或必须完全准确时，
   建议在 AI 生成图片时仅保留文字占位区域（留白），生成后用 Photoshop 等工具
   手动叠加精确文字层。此策略可彻底规避 AI 文字拼写错误问题，
   同时保证排版精确可控。

5. **Desktop 与 Mobile 文字一致性**：同一主题的 Desktop 版和 Mobile 版中，
   相同信息的文字内容必须保持一致（如尺寸标注、功能卖点），仅排版位置和
   字号因构图不同而调整。

> 注意：A+ 内容的文字标注同样不得出现 `references/claims_compliance.md` 中
> 列出的 115 个敏感词。质检时需逐字核对所有文字标注。

---

> 以上示例以窗帘产品为主。对于其他产品类型（家电、收纳、工具等），请参照三层 Prompt 结构，将产品锁段落、视觉表达层和合规约束层适配为对应产品的特征。
