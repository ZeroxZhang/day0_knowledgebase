# 断点记录（CHECKPOINTS）

用途：每完成一个批次（3～5 个主题）追加一条记录。任务意外中断时，新会话只需读本文件最后一条 +
[PROGRESS.md](PROGRESS.md)，即可接续工作，不重复、不重建。

记录格式：

```text
## CP-编号 | 日期时间 | 批次名称
- 完成：<文件清单或领域>
- 下一批：<具体文件或主题>
- 遗留：<缺口、待核验项、未解决问题>
- 恢复动作：新会话从这里继续时第一步做什么
```

---

## CP-000 | 2026-09-11 | 知识库骨架初始化

- 完成：knowledge/ 目录及 11 个领域子目录；INDEX.md、PROGRESS.md、CHECKPOINTS.md；11 个领域 README.md（子主题清单，均为"待整理"）。
- 下一批：01_energy 首批三篇 02_electrical_basics.md / 03_generation_methods.md / 04_energy_storage.md。
- 遗留：全部领域文章未写；规则文件尚未加入断点机制说明（马上补）。
- 恢复动作：读 EXECUTION_GUIDE.md → 读 PROGRESS.md"下一批具体主题" → 直接开写对应文章，写完更新 PROGRESS 与本文件。

---

## CP-001 | 2026-09-11 | 能源+食物+居住+健康 基础篇完成

- 完成：
  - 01_energy 全部 5 篇基础（electrical_basics / generation_methods / energy_storage / electrical_safety / energy_estimation），状态均为"待核验"。
  - 03_food 全部 4 篇基础（nutrition_basics / food_storage / food_safety / cooking_basics）。
  - 04_shelter 全部 4 篇基础（shelter_basics / thermal_insulation / cooling_ventilation / fire_safety）。
  - 05_health 全部 4 篇基础（first_aid_basics / wound_care / infection_prevention / common_illness），由子代理完成。
- 下一批：06_comms 四篇（radio_basics / emergency_signaling / maps_navigation / orientation）——其子代理因并发上限失败，需补写；之后 07_tools、08_production、09_materials、10_cooperation、11_science。
- 遗留：全部文章状态"待核验"，关键待核验项集中在：CPR 数值与止血带操作（05）、饮水消毒剂量（02）、燃料热值与光伏等效小时（01/03）、CO 与火灾分类数值（04）。子代理并发上限约为 2，一次最多派 2 个。
- 恢复动作：读 PROGRESS.md 分领域状态表 → 从"下一批"开写 → 每完成一个领域在 CHECKPOINTS 追加一条。

---

## CP-002 | 2026-09-11 | 基础第一轮正文基本完成（差材料领域 2 篇）

- 完成：02_water 5 篇（子代理）、06_comms 4 篇、08_production 4 篇、10_cooperation 4 篇、11_science 4 篇（均自写）；07_tools 4 篇（子代理）。09_materials 已有 01_wood.md、02_metal_basics.md，缺 03_cordage_knots.md、14_ceramics_glass.md（子代理仍在写）。
- 下一批：材料领域补完 2 篇 → 全库补漏检查（链接、模板、重复）→ 更新 INDEX/PROGRESS → 最终审计。
- 遗留：全部 42+ 篇状态"待核验"；子代理报告的关键待核验点：CPR/止血带参数（05）、导线色标与工艺数值（07）、绳索安全工作载荷（09）。子代理并发上限约 2。
- 恢复动作：检查 09_materials 目录是否已有 03_cordage_knots.md 与 14_ceramics_glass.md，缺则补写；随后按 PROGRESS.md 执行补漏与审计。

---

## CP-003 | 2026-09-11 | 基础第一轮完成（全库骨架 + 46 篇基础文章）

- 完成：11 个领域全部 46 篇基础正文（01:5 / 02:5 / 03～11 各 4），INDEX/PROGRESS 已更新；补漏检查通过（脚本核验：无死链、模板六节齐全、关键数值跨文一致；修复 1 处乱码字词）。
- 下一批：第二轮——①高优先待核验项来源核对（水净化配比、CPR/止血带、灭火器分类、CO 结合倍数、导线载流量）；②进阶主题开写（建议顺序：02 雨水收集、01 光伏系统、08 留种、10 社区组织）；③近似主题查重（03 保存类、07 测量类）。
- 遗留：46 篇全部"待核验"，无一已核对；进阶主题 34 项待写（各领域 README 已列）。
- 恢复动作：读 PROGRESS.md"下一批具体主题" → 按序执行；若做第二轮来源核对，用 WebSearch/WebFetch 查权威原文并逐篇把状态改为"已核对"，核对结果写回文章来源节。

---

## CP-004 | 2026-09-12 | 第二轮批次 1：高风险数值来源核对完成（4 篇）

- 完成：WebSearch 实际查证并写回——①water_purification：EPA 氯消毒配比（每加仑 2 滴 6%/6 滴 8.25%，30 分钟）与煮沸 1 分钟/高海拔 3 分钟；②wound_care：止血带位置**修正**为近心端 10～15 cm（原 5～8 cm 有误），总时长 ≤2 h，放松流派分歧已注明（来源：中国急诊医学杂志专家共识）；③fire_safety：CO 结合血红蛋白 200～250 倍（StatPearls/Medscape）；④electrical_safety：电流效应分级与漏保 30 mA/0.1 s（二级资料交叉印证，IEC 原文未查）。
- 下一批：①续核对——灭火器分类（04）、CPR 对照现行 AHA/红十字会指南原文（05）、导线载流量表（01）、绳结强度折减（09）；②开写进阶主题（雨水收集、光伏系统、留种）；③查重。
- 遗留：46 篇整体状态仍"待核验"，仅 4 篇含"已核对子项"；WebSearch 偶发超时（重试即可）；84 消毒液国产产品换算、SODIS 时长、明矾用量仍未核对。
- 恢复动作：读 PROGRESS.md"下一批具体主题" → 从"续核对"清单继续，查证结果按"已核对子项"格式写回文章来源节 → 完成后追加 CP-005。

---

## CP-005 | 2026-09-12 | 任务重定义 + 文明重建层启动

- 任务变化：用户将目标从"应急备灾知识库"升级为"从零重建文明知识库"（假设：回到原始时代、一无所有，只靠知识库）。EXECUTION_GUIDE 重写为 v1.0：双轴体系（主题轴 01～12 × 阶段轴 0～5）、三视角层（从零重建/应急/原理）、文章模板新增"视角/阶段/从零实现路径"；爆炸物等安全边界写入规划。
- 完成：00_roadmap.md（技术树与文章登记表）；12_knowledge 新领域；11 个领域 README 追加"从零重建层"清单；INDEX 重写；AGENTS.md 更新。首批 3 篇从零重建文章：fire_making（01）、stone_tools（07）、pottery（09），均含从零实现路径与依赖链。
- 下一批：①阶段 0 补齐 water_from_scratch、foraging_hunting；②阶段 1 补齐 plant_fiber_textile、woodworking_primitive、tanning_basics；③旧 46 篇应急文章逐步补"从零实现路径"跳转或改写（低优先，随缘）。
- 遗留：应急层 46 篇整体仍"待核验"；新 3 篇亦"待核验"；从零路径依赖链中引用了多篇"待写"文章（如 tanning、kiln_construction），写文时注意链接目标补齐后自查。
- 恢复动作：读 EXECUTION_GUIDE v1.0 → 读 00_roadmap.md（✓ 标记 = 已写）→ 按 PROGRESS"下一批具体主题"开写；新文章写完在 roadmap 登记节点 + 更新领域 README + 追加 CP。

---

## CP-006 | 2026-09-12 | 文明重建层全阶段补齐（阶段 0～5 全部节点完成）

- 完成：新增 49 篇从零重建文章，全库正文 95 篇 + 4 管理文件 + 12 领域 README。写作粒度原则（零基础、术语全解释、禁止跳步）已入 EXECUTION_GUIDE 第 3 节。阶段 0～5 全部 roadmap 节点 ✓（含补写的 natural_dyes、small_livestock、earth_building、cordage_knots 从零路径）。
- 质量核验：全库相对链接脚本清零（中途修复约 30 处跨目录路径错误与 1 处 sed 误伤，均已修复）；95 篇模板六/七节齐全。
- 高危待核验（子代理自报，需优先人工/来源核对）：助产产科数值（宫口 10 cm、产程时长、断脐）、草药"小试"流程是否可能诱导试毒（需独立评估）、水轮功率系数与风能折减、灰水浓度鸡蛋漂浮法、蒸汽膨胀倍数、玻璃配比。
- 下一批（可选扩展，非 roadmap 节点）：①应急视角进阶主题约 30 项（各领域 README"进阶（待整理）"）；②来源核对第二轮（助产/草药/绳结/种子寿命）；③fiber_materials.md 与 04_plant_fiber_textile.md 查重合并。
- 恢复动作：读 PROGRESS.md"下一批具体主题"；新文章仍按"写→登记 roadmap→更新 README→追加 CP"流程。

---

## CP-007 | 2026-09-12 | 旧文细化改写战役启动（46 篇 → 120～200 行零基础标准）

- 完成：①查重合并——fiber_materials.md 从未创建，已在 08 README 移除条目并指向 ../09_materials/04_plant_fiber_textile.md；②细化改写已完成 9 篇：03_food 全部 4 篇（nutrition/food_storage/food_safety/cooking）、04_shelter 全部 4 篇（shelter_basics/thermal/cooling/fire，fire 保留已核对子项）、05_health 的 first_aid_basics 与 wound_care（wound 保留止血带已核对子项）。全部加"视角：应急"字段、更新时间 2026-09-12。
- 进行中：01_energy 5 篇与 02_water 5 篇的改写子代理（agent_bad4e9b1 / agent_9602f009）运行中，指令要求保留 electrical_safety 与 water_purification 的已核对子项。
- 下一批：剩余 22 篇旧文改写——05 剩 2（infection/common_illness）、06 通信 4、07 工具 4、08 生产 4、09 材料 4、10 协作 4、11 科学 4；派代理规则：每轮 2 个并发，每代理 1 个领域（4~5 篇），指令模板同 01/02 轮（保留已核对子项、加视角字段、120~200 行）。
- 遗留：全部文章状态仍"待核验"；来源核对第二轮未开始；应急进阶 30 项待整理。
- 恢复动作：按"下一批"清单派代理/自写，每完成 1～2 个领域追加一次 CP。

---

## CP-008 | 2026-09-12 | 旧文改写进度：36/46

- 完成：在 CP-007 基础上新增——05_health 剩余 2 篇（infection/common_illness，代理）、06_comms 4 篇（代理）、11_science 全部 4 篇（units/physics/chemistry/biology，自写，视角标"通用"）。累计 36/46。
- 进行中：07_tools 4 + 08_production 4（agent_df2a3c58）；09_materials 4 + 10_cooperation 4（agent_7d2b3270）。
- 全部完成后动作：①全库链接脚本核验（改写中链接大量更新，必须重跑）；②抽查已核对子项保留情况（electrical_safety / water_purification / wound_care / fire_safety 四篇）；③写 CP-009 与 PROGRESS 收官；④来源核对第二轮（助产/草药/绳结/种子寿命/玻璃配比/蒸汽膨胀倍数等 CP-006 清单）。
- 恢复动作：读 PROGRESS 与本条 → 检查两个进行中代理的产出（行数+链接+已核对子项）→ 派发未完成领域或自写 → 收官流程。

---

## CP-009 | 2026-09-12 | 46 篇旧文改写完成 + 细化扩写战役启动（62 篇 <标准）

- 完成：①46 篇应急旧文全部改写至细化标准（01/02/06/07/08/09/10 由代理，03/04/05/11 自写），行数达标、链接全库核验清零、四篇"已核对子项"保留确认；②发现口径问题——自写的段落式文章物理行数少（58～118 行）且字符量（2200～3300）低于代理改写基准（≥4200 字符），共 62 篇低于"≥120 行且 ≥4200 字符"组合标准。
- 进行中：扩写战役第一轮两个子代理——A：01_energy 6 + 06_comms 6（agent_e527a690）；B：03_food 7 + 04_shelter 7（agent_97cd9e81）。规则：保留现有内容只增不删、条目化短行、已核对子项逐字保留、新增待核验点标注。
- 待派批次（每轮 2 并发）：③05_health 2 + 07_tools 2 + 08_production 6；④09_materials 8 + 12_knowledge 6；⑤10_cooperation 10 + 11_science 5。清单以脚本 `wc -l <120 或 wc -m <4200` 复查为准（先批完成后可能新增越界者）。
- 遗留：全部文章"待核验"；来源核对第二轮未开始；应急进阶 30 项未写（非 roadmap 节点）。
- 恢复动作：重跑清单脚本 → 派发未完成批次 → 全部达标后收官（全库链接核验 + 已核对子项抽查 + CP-010 + PROGRESS）。

---

## CP-009 补 | 2026-09-12 | 扩写战役第一轮结果与新批次

- 第一轮两个子代理因"Model request failed"中断，但实际完成大部分：01_energy 全 6 篇达标；06_comms 完成 signal/telegraph（radio 差字符量）；03_food 完成 cooking/food_storage/nutrition（food_safety 116行/4149字接近，granary/salt/sugar_fat 未完成）；04_shelter 完成 cooling/earth_building/fire_safety 大部（kiln/shelter/thermal 未完成）。已核对子项抽查通过（electrical_safety 保留确认）。
- 进行中（改 8 篇/批，降低单批时长防失败）：agent_73c2a7a7（06_comms 剩 4 + 03_food 剩 4）；agent_84472d0f（04_shelter 剩 6 + 05_health 2）。
- 待派批次：③07_tools 2 + 08_production 6；④09_materials 8；⑤12_knowledge 6；⑥10_cooperation 10 + 11_science 5。每批完成后用脚本复查"wc -l <120 或 wc -m <4200"。
- 恢复动作：重跑清单脚本 → 补派未完成文件 → 全部达标后收官（链接核验 + 已核对子项抽查 + CP-010 + PROGRESS）。

---

## CP-010 | 2026-09-12 | 文件名编号化（用户要求）

- 方案：域内两位序号前缀，序号=技术树/学习顺序（如 02_water/04_water_purification.md）。规则已写入 EXECUTION_GUIDE 第 3 节"文件命名规则"。
- 已完成：01_energy（11 篇）、02_water（7）、07_tools（7）、08_production（7）、09_materials（14）、10_cooperation（9）、11_science（7）、12_knowledge（6）共 68 篇改名；全库引用（README/00_roadmap/INDEX/PROGRESS/CHECKPOINTS/文内链接）同步替换；安全领域链接核验清零、无双前缀误伤。
- **延迟处理**：03_food、04_shelter、05_health、06_comms 正被扩写子代理（agent_73c2a7a7 / agent_84472d0f）编辑，改名与引用替换推迟到代理完成后执行：①mv 改名（03: nutrition 01/food_storage 02/food_safety 03/cooking 04/foraging_hunting 05/salt 06/sugar_fat 07/granary 08；04: shelter_basics 01/thermal 02/cooling 03/fire 04/kiln 05/earth 06；05: first_aid 01/wound 02/infection 03/common 04/midwifery 05/herbal 06/public_health 07；06: radio 01/signaling 02/signal_systems 03/maps 04/orientation 05/telegraph 06）；②对四领域全部 md 跑与本次相同的 sed 替换（含代理新写产出中的旧名引用）；③重跑全库链接核验。
- 恢复动作：确认两个扩写代理状态 → 已完成则执行延迟改名流程 → 继续扩写待派批次（07+08 → 09 → 12 → 10+11，注意这些领域文件已带编号，派单时用新文件名）。

## CP-010 完成 | 2026-09-12 | 编号化全库收官

- 04_shelter（6 篇）与 05_health（7 篇）延迟改名已执行；全库 95 篇文件名均带域内两位序号前缀；全库链接核验清零（修复了 04/05 内部旧引用与 3 处双前缀）；无双前缀残留。
- 剩余扩写（18 篇，文件名已编号）：12_knowledge 03_ink_and_pen / 04_printing_basics / 05_education_system / 06_library_records；10_cooperation 01～09 全部 9 篇；11_science 01_units / 02_physics / 03_chemistry / 04_biology / 05_astronomy。
- 进行中：agent_78a903bf（07_tools 2 + 08_production 6）；agent_0472ede9（09_materials 7 + 12_knowledge 01/02）。
- 恢复动作：两代理完成后 → 派最后两批（12 剩 4 + 11 全 5；10 全 9）→ 全库清单脚本复查（wc -l≥120 且 wc -m≥4200）→ 链接核验 → CP-011 + PROGRESS 收官。

## CP-011 | 2026-09-12 | 细化扩写战役完成（94/95 达标 + 1 篇在途）

- 完成：全部 46 篇应急旧文 + 48 篇从零重建文章扩写至"≥120 行且 ≥4200 字符"标准；全库链接核验清零；模板字段 95/95 齐全；编号化全库完成（含 03/04/05/06 延迟改名）。
- 在途：agent_0472ede9（09+12 领域批次）仍在写 12_knowledge/02_papermaking.md（其余 8 篇已交付达标），完成后 95/95。
- git：仓库已建（main 分支），每批一提交，当前 4 个提交。
- 下一批：①02_papermaking 达标确认；②来源核对第二轮（CP-006/009 清单：助产产科数值、草药小试流程、水轮功率系数、风能折减、灰水鸡蛋法、蒸汽膨胀倍数、玻璃配比、绳结强度、种子寿命）；③应急进阶 30 项（非 roadmap 节点，可选）。
- 恢复动作：复查 02_papermaking（wc ≥120/≥4200）→ CP-012 + PROGRESS 收官 → 来源核对第二轮。

## CP-012 | 2026-09-12 | 细化战役全面收官（95/95 达标）

- 完成：02_papermaking 由 agent_0472ede9 补齐（123 行/4690 字）——**全部 95 篇文章达到"≥120 物理行且 ≥4200 字符"细化标准**；全库链接核验清零；模板字段 95/95 齐全；四篇"已核对子项"完整保留（electrical_safety / water_purification / fire_safety / wound_care）。
- 知识库现状：12 领域 × 95 篇（应急层 46 + 从零重建层 49），全部带域内序号前缀，全部"待核验"状态；技术树阶段 0～5 全节点 ✓。
- 下一批：①来源核对第二轮（助产产科数值、草药小试流程、水轮功率系数、风能折减、灰水鸡蛋法、蒸汽膨胀倍数、玻璃配比、绳结强度、种子寿命、饮水配比国产化等，清单散布各篇"待核验项"）；②应急视角进阶 30 项（各领域 README"进阶（待整理）"，可选扩展）。
- 恢复动作：读 PROGRESS.md"下一批具体主题" → 用 WebSearch 逐项核对并把结果写回文章来源节（核对通过者整篇升"已核对"）→ 每批追加 CP。

## CP-013 | 2026-09-12 | 来源核对第二轮完成（10/10 项核验，9 篇升"已核对"）

- 核验结果（WebSearch 实际查证，结果已写回各篇来源节"已核对子项"）：
  1. 助产产科数值 ✓（PPH≥500 ml/WHO 2025 新建议 300 ml+体征、延迟断脐 1～3 分钟、宫口开全 10 cm、初产妇第一产程 11～12 小时）→ midwifery 升"已核对"
  2. 饮水消毒国产化 ✓（84 有效氯 4%～5.5%、应急饮水加氯 4～8 mg/L 静置 30 分钟、井水 10～15 mg/L、余氯≥0.5）→ water_purification 升"已核对"；84 浓度上限表述修正
  3. 水轮功率系数 ✓（P=9.81ηQH；上击 60%～85%、下击 22%～50%，本文取值偏保守可用）→ 升"已核对"
  4. 风能折减 ✓（三次方关系、贝茨极限 59.3%、实机 35%～45%、阻力型约十分之一）→ 升"已核对"
  5. 蒸汽膨胀倍数 ✓（常压 1600 倍理论/工程 1700 倍）→ 升"已核对"
  6. 玻璃配比 ✓（成品 70-73/13-15/9-10；生料 73:15:12，纯碱略高于本文"一份"）→ 升"已核对"
  7. 灰水鸡蛋法 ✓（硬币大小露顶≈28%～33% 浓度）→ 升"已核对"
  8. 绳结强度折减 ✓（打结损失 25%～55%，WLL 1/5～1/10 通行）→ 升"已核对"
  9. 种子寿命 ✓（葱 1～2/豆 3～5/番茄 3～5/葫芦科 4～5+）→ 升"已核对"
  10. 草药：原理层 ✓（天然≠安全、乌头碱 0.2/2～4 mg 炖煮不破坏、柳皮水杨苷机理）——但"口服小试"无标准流程，**herbal_medicine_boundaries 保留"待核验"**（已核对子项+保留警示已写回）
- 知识库现状：95 篇中 9 篇"已核对"（关键数值有来源支撑）、86 篇"待核验"（各项待核验点已逐条列出）。
- 下一批：①继续来源核对第三轮（下批优先：灭火器分类、CPR 现行指南、导线载流量、C₁V₁ 稀释口径、巴氏消毒组合）；②应急进阶 30 项（可选）；③使用层建设（可选）。
- 恢复动作：读 PROGRESS"下一批"→ WebSearch 逐项 → 写回来源节 → 升级状态 → 追加 CP。

## CP-015 | 2026-09-12 | 来源核对第四轮完成（4 项，food_safety 升"已核对"）

- 核验结果（WebSearch 实际查证）：
  1. 睡觉关门挡火 ✓（UL/FSRI "Close Before You Doze"：现代家具轰燃 <5 分钟；关门房约 38 ℃ vs 开门 >540 ℃；CO 差十倍）——本文"延阻数分钟"偏保守成立
  2. 冷柜停电窗口 ✓（USDA/CDC：冷藏 4 h、满载冷冻 48 h、半载 24 h）
  3. 危险温度带 ✓（USDA 40～140 ℉/2 小时废弃规则；"禁止尝"为原文级要求）
  4. 锂电池充电 ✓（CPSC"勿整夜充电"；充满即拔、无人看管不充）；灭火器检查 ✓（月检压力表绿区、罐体 5 年水压试验）
- 全部写回 fire_safety 与 food_safety（后者升"已核对"）。
- 知识库现状：95 篇中 14 篇"已核对"、81 篇"待核验"。
- 下一批（可选）：来源核对第五轮（次要项清单见各篇待核验项）；应急进阶 30 项；使用层建设（入门导读、阶段测评）。
- 恢复动作：读 PROGRESS"下一批"→ 逐项核验写回 → 追加 CP。

## CP-016 | 2026-09-12 | 来源核对第五轮 + 使用层建设

- 来源核对第五轮（3 项，写回来源节）：①木耳泡发精确化（冷水 1～2 小时、上限 4 小时、超 6 小时细菌繁殖/超 8 小时中毒风险；隔夜冰箱 ≤24 小时为条件性可接受）；②奶酪霉斑（USDA：硬质切 ≥2.5 cm、刀勿触霉，软质整弃）；③SODIS（晴天 6 小时/全阴 48 小时/浊度 ≤30 NTU，WHO 推广）。
- 使用层建设：新建 [00_使用指南.md]——三种使用方式（系统学习/应急速查/教学材料）、文章标记读法、**六个阶段达标自测清单**、应急速查索引、知识库维护纪律；已挂入 INDEX。
- 知识库现状：95 篇正文（14 篇已核对）+ 00_roadmap + 00_使用指南 + 管理文件；git 13 提交。
- 下一批（可选）：应急进阶 30 项；剩余次要项核对（随用随核）。
- 恢复动作：读 PROGRESS/本条 → 按需继续可选批次。
