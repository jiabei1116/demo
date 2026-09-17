# Peec AI 可交互复刻 · 注记清单

| 编号 | 菜单路径 | 目标区域 | 注记类型 | 注记内容 |
| --- | --- | --- | --- | --- |
| 1 | Gen-Centric Services / Overview | 提示词摘要 | 字段说明 | 展示提示词名称、添加时间、主题、Mention Rate、地区和 Intent。空主题显示横线；Mention Rate 仅保留保存页中的图形示意，没有数值、分档阈值或查询逻辑；地区固定为 United States。Active／Paused 为本地展示状态，未接入真实采集任务。 |
| 2 | Gen-Centric Services / Overview | 添加时间 | 交互逻辑 | 点击“3 mo. ago”，提示该时间相对于原页面保存时约三个月前。不是相对当前打开日期重新计算的时间，也不支持编辑。 |
| 3 | Gen-Centric Services / Overview | 提示词设置入口 | 交互逻辑 | 点击齿轮打开设置弹窗，并回填当前提示词、主题和状态。该入口可编辑本地展示信息，不修改 Peec 账户中的提示词。 |
| 4 | Gen-Centric Services / Overview | 提示词设置表单 | 字段说明 | Prompt 必填，最多 300 字符，提交时去除首尾空格；仅空格时停留在输入框。Topic 可空，最多 80 字符并去除首尾空格。Status 仅 Active／Paused，默认回填当前值。原型未定义其他校验或权限条件。 |
| 5 | Gen-Centric Services / Overview | 保存提示词设置 | 交互逻辑 | 点击 Save changes，通过校验后更新页面摘要、浏览器标题及后续聊天抽屉的提示词标题，尝试写入本浏览器缓存，关闭弹窗并提示已本地保存。缓存写入失败未单独报错；聊天回答原文不重算。 |
| 6 | Gen-Centric Services / Overview | 取消与关闭弹窗 | 交互逻辑 | 设置弹窗的 Cancel、右上角关闭、Esc 或点击弹窗外部均关闭弹窗，未提交表单不生效，不弹放弃修改确认。其他业务详情沿用关闭规则；打开新的详情会替换原详情，不提供逐层返回栈。 |
| 7 | Gen-Centric Services / Visibility | 图表品牌选择 | 交互逻辑 | 默认选中虎虎保险，可从七个保存品牌中切换。选择其他品牌后突出该品牌曲线、降低其余曲线透明度，并高亮排名表对应行；选择虎虎保险时全部曲线保持正常透明度。此选择不等于聊天列表的品牌筛选。 |
| 8 | Gen-Centric Services / Visibility | 日期范围选择 | 业务规则 | 默认 Last 30 days，可选 24 小时、7／14／30／90 天。按保存记录距保存日的天数筛选聊天，并回到第 1 页；图表在不超过 7 天时取最后 1 个周观测点、不超过 14 天取 2 个，其余取全部 5 个。90 天会提示仅有 30 天图表历史；品牌汇总和来源总计不重算。 |
| 9 | Gen-Centric Services / Visibility | All filters 按钮 | 交互逻辑 | 点击打开模型与品牌组合筛选弹窗。已应用的模型／品牌条件会回填；按钮中的条件数只统计这两个字段，不包含独立的来源、特征或日期条件。 |
| 10 | Gen-Centric Services / Visibility | 综合筛选字段 | 字段说明 | AI model 默认 All models，可选 ChatGPT、Gemini、AI Overview；Brand 默认 All brands，可选七个品牌。模型精确匹配；品牌按回答文本中忽略大小写的包含关系，或已记录提及域名匹配。两个字段与日期、来源、特征条件同时满足才保留聊天。Location 仅 US，不参与实际过滤。 |
| 11 | Gen-Centric Services / Visibility | 应用综合筛选 | 交互逻辑 | 在筛选弹窗点击 Apply filters 后才生效，更新聊天列表、总数和条件标识，回到第 1 页并关闭弹窗，提示匹配数量。该操作不按模型或品牌重新计算趋势、排名和来源分布。 |
| 12 | Gen-Centric Services / Visibility | 重置综合筛选 | 交互逻辑 | Reset filters 清除模型、聊天品牌、来源和特征条件，日期恢复 30 天，页码回到 1，并刷新聊天与图表、关闭弹窗。保留每页条数、排序、列显隐、图表类型。 |
| 13 | Gen-Centric Services / Visibility | 可见度趋势图 | 业务规则 | 展示七个品牌在五个保存周观测点上的可见度百分比；鼠标移动时显示最近观测点的日期与可见品牌数值，移出后隐藏提示。百分比来自保存页，当前资料没有原始样本分母，不把本地图表视为实时分析结果。 |
| 14 | Gen-Centric Services / Visibility | 折线与柱状图切换 | 交互逻辑 | 默认折线图，点击对应图标切为柱状图或恢复折线图；保留日期范围，使用保存的周观测点展示全部品牌。仅改变表达形式，不改变保存的观测值。 |
| 15 | Gen-Centric Services / Sentiment | 品牌排名列表 | 字段说明 | 仅展示 Brand、Mention Rate、Top 3 Mention Rate、#1 Mention Rate 四列，保留七个保险品牌，当前品牌显示“Your brand”标识。品牌提及率沿用保存的 Visibility 百分比；资料未提供 TOP3 和首位提及率，统一显示“—”，不以 SoV、情感分值或平均位置替代。默认按品牌提及率降序，当前没有分页。 |
| 16 | Gen-Centric Services / Sentiment | 品牌排名表头排序 | 交互逻辑 | 点击表头或聚焦后按 Enter 排序；同列再次操作反向，切换列先降序。品牌列按名称，三项提及率按数值；缺失值始终置后，同值及全为空时保持原始记录相对顺序。“—”不是 0%。 |
| 17 | Gen-Centric Services / Sentiment | 导出品牌排名 | 交互逻辑 | 点击导出图标，再选 Export CSV。导出七个品牌的 Brand、Mention Rate、Top 3 Mention Rate、#1 Mention Rate 四列，顺序与主表当前排序一致；百分比带 %，缺失值为“—”。不导出排名序号、SoV、情感、平均位置或涨跌值。 |
| 18 | Gen-Centric Services / Sentiment | 展开品牌排名 | 交互逻辑 | 点击“View more”打开宽版 Brand ranking，列、数值、当前品牌标识和行顺序均与主表一致。点击记录或聚焦后按 Enter 打开品牌详情；弹窗中的 Export CSV 导出相同四列和顺序。 |
| 19 | Gen-Centric Services / Sentiment | 查看品牌详情 | 交互逻辑 | 点击品牌行或聚焦后按 Enter，打开详情抽屉，展示域名及 Mention Rate、Top 3 Mention Rate、#1 Mention Rate。后两项缺失时显示“—”；不展示旧的 SoV、情感、平均位置和涨跌指标。以下为所有品牌的公共规则。 |
| 20 | Gen-Centric Services / Sentiment | 品牌详情与关联聊天 | 业务规则 | 品牌详情中的关联聊天按提及域名包含该品牌，或回答原文包含品牌名称筛选全部保存聊天；不继承聊天列表的筛选和分页。点击关联记录会替换为完整聊天抽屉。指标保持保存页数值，不随关联聊天数量重算。 |
| 21 | Gen-Centric Services / Source | 域名与链接页签 | 交互逻辑 | 默认 Domains 展示保存域名；URLs 展示从完整回答中提取并去重的已保存链接。点击链接行打开该域名的来源详情，不直接跳到外部网页。切换页签保留 Top／New／Trending／Losing 选项。 |
| 22 | Gen-Centric Services / Source | 来源趋势页签 | 业务规则 | 默认 Top，沿用保存页来源顺序。New、Trending、Losing 所需的来源历史没有保存，点击后展示无数据说明，不使用静态总数伪造增减趋势；切回 Top 恢复当前域名／链接视图。 |
| 23 | Gen-Centric Services / Source | 来源域名列表 | 交互逻辑 | Top 下展示八个域名及 Retrievals，当前不提供分页或表头排序。点击域名行打开来源详情。行旁数量是保存的引用次数，不等于当前十条聊天中的匹配数，也不随聊天筛选变化。 |
| 24 | Gen-Centric Services / Source | All domains 入口 | 交互逻辑 | 点击 All domains 打开来源分析。默认展示前八个域名，共 312 次引用，占保存页全部 841 次引用的 37.1%；色块面积按这八个域名的引用数计算，占比以 841 为分母。域名列表默认收起，点击 View all available domains 展开。 |
| 25 | Gen-Centric Services / Source | 来源列表展开按钮 | 交互逻辑 | Expand 与 All domains 打开同一来源分析。点击 AI 平台柱子联动筛选来源色块、数量、占比、域名列表及 CSV；再点同一平台或 Clear platform filter 恢复全平台。平台统计按日期范围内保存聊天的已命名来源计算，不拆分 841 次总引用；缺失平台显示无数据，CSV 禁用。CSV 包含 Scope、Platform、Domain、Retrievals、Share (%)，使用当前筛选结果。来源类型卡片始终注明全平台口径，未提供平台分类明细。 |
| 26 | Gen-Centric Services / Source | 来源类型分布 | 字段说明 | 展示 You、Corporate、Other、UGC、Competitor、Editorial、Institutional、Reference 的保存比例，总引用数为 841。比例经过展示取整，可能不精确合计 100%；类型划分算法资料未说明。此区为静态展示，没有下钻点击逻辑。 |
| 27 | Gen-Centric Services / Source | 来源详情统计 | 业务规则 | 从主列表进入详情，展示保存的引用总数和全部保存聊天的匹配数。从平台筛选结果进入详情，引用数量、完整链接和关联聊天使用当前平台及日期范围内的已保存记录；Named references in sample 区分样本口径。未知完整 URL 显示说明，不推测地址。 |
| 28 | Gen-Centric Services / Source | 来源详情链接与聊天 | 交互逻辑 | 来源详情中的完整 URL 在新标签页打开外部网站；点击关联聊天打开完整回答，无匹配项则显示说明。从来源分析进入的详情提供 Back to source analysis，返回后保留平台筛选和域名列表展开状态。主列表直接进入来源详情时仍使用全部保存聊天。 |
| 29 | Gen-Centric Services / Q&A records | 导出聊天 | 交互逻辑 | 工具栏仅保留 Export 按钮。点击该按钮选择 CSV 或 JSON。导出当前全部筛选结果及当前排序，不只导出当前页。CSV 包含模型、完整回答、已知品牌域名、已知来源域名、位置、创建时间；JSON 保留记录的原有字段。导出行为不受当前分页影响。 |
| 30 | Gen-Centric Services / Q&A records | 聊天记录与总数 | 业务规则 | 当前仅有十条完整保存聊天；原页面的 90 条总量不代表本地可读取 90 条。首次进入按保存记录顺序，未主动设置默认排序字段；显示摘要、模型、提及品牌、来源、品牌位置和相对保存日的时间。额外的 +N 为已保存计数，缺少名称时不能展开补全。 |
| 31 | Gen-Centric Services / Q&A records | 聊天表头排序 | 交互逻辑 | 点击表头或聚焦表头按 Enter，首次按该列升序，再次点击反向；切换列先升序并回到第 1 页。文本按字串；品牌／来源按含额外计数的数量；时间按距保存日天数；空位置视为无限大。相同值保留原始记录相对顺序；后续筛选保留排序。 |
| 32 | Gen-Centric Services / Q&A records | 品牌位置说明图标 | 字段说明 | 点击 Position 表头中的品牌图标提示：该列为虎虎保险在保存回答中的位置，横线表示没有记录位置。图标点击不会触发表头排序；不是保险产品优劣的排名。 |
| 33 | Gen-Centric Services / Q&A records | 聊天分页 | 交互逻辑 | 默认每页 10 条，可选 5 条。支持前页、后页和已显示的页码按钮，首末页禁用越界按钮，无自由输入跳页。更改每页条数回到第 1 页；筛选、日期和排序变化也回到第 1 页。总数按筛选后保存记录计算；没有新增或删除聊天操作。 |
| 34 | Gen-Centric Services / Q&A records | 无结果状态 | 交互逻辑 | 组合条件无匹配时隐藏数据行，显示 No chats match your filters 和 Clear filters，总数显示 0。点击 Clear filters 与综合筛选重置一致，清除模型、聊天品牌及日期限制；保留列、排序和每页条数。 |
| 35 | Gen-Centric Services / Q&A records | 打开聊天详情 | 交互逻辑 | 点击聊天行默认打开 Answer；点击 Mentions 或 Sources 单元格时直接打开对应页签；行聚焦后 Enter 打开 Answer。详情显示完整保存回答，未调用模型重新生成。相同操作规则适用于所有记录。 |
| 36 | Gen-Centric Services / Q&A records | 回答与品牌来源页签 | 交互逻辑 | Answer 展示提示词和完整回答，支持段落、列表、表格与外链；Mentions 展示已知品牌，点击进入品牌详情；Sources 展示已知来源及保存链接，点击来源进入详情、点击完整链接新开外部网页。缺失额外名称或链接时仅说明数量，不伪造数据。 |
| 37 | Gen-Centric Services / Q&A records | 上一条与下一条回答 | 业务规则 | Previous／Next 按全部十条保存记录的原始顺序切换，不受主列表筛选、排序和分页限制；每次切换回 Answer 页签。第一条禁用 Previous，最后一条禁用 Next。 |
| 38 | Gen-Centric Services / Q&A records | 复制完整回答 | 交互逻辑 | Copy answer 复制当前记录的原始回答文本，即使当前正在 Mentions／Sources 页签也复制回答。成功提示已复制；剪贴板不可用时下载 copied-text.txt。不复制主表截断摘要或页面标注内容。 |
