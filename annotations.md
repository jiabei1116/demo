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
| 12 | Gen-Centric Services / Visibility | 重置综合筛选 | 交互逻辑 | Reset filters 清除模型、聊天品牌、来源和特征条件，日期恢复 30 天，页码回到 1，并刷新聊天与图表、关闭弹窗。保留每页条数、排序、列显隐、图表类型、周月选择、隐藏曲线和查询词搜索。 |
| 13 | Gen-Centric Services / Visibility | 可见度趋势图 | 业务规则 | 展示七个品牌在五个保存周观测点上的可见度百分比；鼠标移动时显示最近观测点的日期与可见品牌数值，移出后隐藏提示。百分比来自保存页，当前资料没有原始样本分母，不把本地图表视为实时分析结果。 |
| 14 | Gen-Centric Services / Visibility | 日周月切换 | 业务规则 | 默认 W。W 使用保存周观测点；M 对当前范围内同月的周观测点求算术平均，并提示计算口径。D 不生成日数据，继续显示周观测点并提示日数据不可用。方向键可在相邻页签间切换。 |
| 15 | Gen-Centric Services / Visibility | 图表更多操作 | 交互逻辑 | 点击省略号打开品牌显示菜单，勾选或取消立即显示／隐藏对应系列；没有“至少保留一个品牌”的限制。Download chart (SVG) 下载当前范围、图表类型和系列显隐状态下的图形。关闭菜单不撤销已完成的切换。 |
| 16 | Gen-Centric Services / Visibility | 折线与柱状图切换 | 交互逻辑 | 默认折线图，点击对应图标切为柱状图或恢复折线图；保留日期范围、周月口径和系列显隐。仅改变表达形式，不改变保存的观测值。 |
| 17 | Gen-Centric Services / Sentiment | 品牌排名列表 | 字段说明 | 展示七个品牌的 Visibility、SoV、Sentiment、Position 及保存的变化值。首次进入沿用保存页行顺序，未运行一次初始排序；当前没有分页。具体指标算法及变化比较期的业务定义资料未说明，排名编号沿用原始行标识。 |
| 18 | Gen-Centric Services / Sentiment | 品牌排名表头排序 | 交互逻辑 | 点击表头或聚焦后按 Enter 进行排序。同一列再次点击反转方向；切换至另一列先降序。Visibility 的初始状态设为降序，因此首次点击该列为升序。品牌名称用文本比较，其他列按数值；相同值沿用原始行相对顺序，左侧原始编号不随排序重排。 |
| 19 | Gen-Centric Services / Sentiment | 显示排名变化 | 交互逻辑 | 默认显示变化值。点击配置图标选择 Show changes／Hide changes，只切换排名表中的变化值显隐，不修改指标数值，也不影响导出内容。 |
| 20 | Gen-Centric Services / Sentiment | 导出品牌排名 | 交互逻辑 | 点击导出图标，再选 Export CSV。导出全部七个品牌及四项指标，行顺序与主排名表当前排序一致；不包含变化值，不受聊天筛选条件影响。 |
| 21 | Gen-Centric Services / Sentiment | 展开品牌排名 | 交互逻辑 | 点击展开图标，打开宽版排名弹窗，沿用数据源原始品牌顺序。点击品牌行打开品牌详情；弹窗内 Export CSV 使用主排名表的当前排序导出，可能与弹窗显示顺序不同。 |
| 22 | Gen-Centric Services / Sentiment | 查看品牌详情 | 交互逻辑 | 点击品牌行、行内图标，或聚焦行后按 Enter，打开品牌详情抽屉，展示域名、四项指标与变化值。以下为相同操作的公共说明，不对七个重复行逐一添加相同标注。 |
| 23 | Gen-Centric Services / Sentiment | 品牌详情与关联聊天 | 业务规则 | 品牌详情中的关联聊天按提及域名包含该品牌，或回答原文包含品牌名称筛选全部保存聊天；不继承聊天列表的筛选和分页。点击关联记录会替换为完整聊天抽屉。指标保持保存页数值，不随关联聊天数量重算。 |
| 24 | Gen-Centric Services / Source | 域名与链接页签 | 交互逻辑 | 默认 Domains 展示保存域名；URLs 展示从完整回答中提取并去重的已保存链接。点击链接行打开该域名的来源详情，不直接跳到外部网页。切换页签保留 Top／New／Trending／Losing 选项。 |
| 25 | Gen-Centric Services / Source | 来源趋势页签 | 业务规则 | 默认 Top，沿用保存页来源顺序。New、Trending、Losing 所需的来源历史没有保存，点击后展示无数据说明，不使用静态总数伪造增减趋势；切回 Top 恢复当前域名／链接视图。 |
| 26 | Gen-Centric Services / Source | 来源域名列表 | 交互逻辑 | Top 下展示八个域名及 Retrievals，当前不提供分页或表头排序。点击域名行打开来源详情。行旁数量是保存的引用次数，不等于当前十条聊天中的匹配数，也不随聊天筛选变化。 |
| 27 | Gen-Centric Services / Source | All domains 入口 | 交互逻辑 | 点击 All domains 打开宽版来源列表，显示全部八个保存域名。列表不继承 URLs 或非 Top 视图；点击域名打开详情。 |
| 28 | Gen-Centric Services / Source | 来源列表展开按钮 | 交互逻辑 | 点击右下角 Expand，与 All domains 打开同一来源列表。弹窗内 Export CSV 导出 Domain、Retrievals 两列，包含八个保存域名，按数据源原顺序输出。 |
| 29 | Gen-Centric Services / Source | 来源类型分布 | 字段说明 | 展示 You、Corporate、Other、UGC、Competitor、Editorial、Institutional、Reference 的保存比例，总引用数为 841。比例经过展示取整，可能不精确合计 100%；类型划分算法资料未说明。此区为静态展示，没有下钻点击逻辑。 |
| 30 | Gen-Centric Services / Source | 来源详情统计 | 业务规则 | 详情展示已保存的引用总数，以及十条保存聊天中来源数组含该域名的记录数；两者口径不同。没有已知总数时不展示统计卡。域名存在但未保存完整 URL 时显示说明，不推测链接地址。 |
| 31 | Gen-Centric Services / Source | 来源详情链接与聊天 | 交互逻辑 | 详情中的完整 URL 在新标签页打开外部网站；关联聊天按来源数组中的域名精确匹配，不继承主列表筛选。点击关联聊天打开完整回答，没有匹配项时展示无关联记录说明。 |
| 32 | Gen-Centric Services / Question Metrics ... | 查询词搜索 | 交互逻辑 | 输入时立即按忽略大小写的包含关系过滤十条保存查询词，无需查询按钮；空输入显示全部。未命中时展示 No query fanouts match your search。搜索不去除首尾空格，也不影响聊天筛选。 |
| 33 | Gen-Centric Services / Question Metrics ... | 查询词列表与排序 | 交互逻辑 | 首次进入沿用保存行顺序。点击表头先按整行文本升序，再次点击降序；筛选不会重置当前顺序。列表没有分页。点击行或聚焦后 Enter 打开查询详情，可复制完整查询词。 |
| 34 | Gen-Centric Services / Question Metrics ... | 导出查询词 | 交互逻辑 | 点击 Export CSV 导出当前搜索命中的查询词，包含 Model、Query 两列。导出保持数据源原顺序，不跟随表头排序；无匹配时仅导出表头。 |
| 35 | Gen-Centric Services / Question Metrics ... | 常用词组 | 交互逻辑 | 展示保存的词组与次数；点击可操作词组，将其填入查询词搜索框并即时筛选、滚动至查询词区域。显示次数不是输入条件命中的行数，不随当前搜索重新计算。 |
| 36 | Gen-Centric Services / Question Metrics ... | 展开查询词 | 交互逻辑 | 点击 Common terms 区域的 Expand 打开全部十条查询词，而非更多常用词组。弹窗搜索独立于主页面搜索，输入即时过滤；点击结果打开查询详情，无匹配时提示 No matching queries。 |
| 37 | Gen-Centric Services / Question Metrics ... | 复制查询词 | 交互逻辑 | 点击 Copy query 将完整查询词写入剪贴板，成功后提示 Copied to clipboard。浏览器不允许复制时改为下载 copied-text.txt；不会修改查询词。 |
| 38 | Gen-Centric Services / Q&A records | 聊天品牌筛选 | 交互逻辑 | 默认 All brands，选择品牌立即按回答文本或提及域名匹配聊天，并回到第 1 页。与模型、来源、特征和日期条件叠加；不改变图表上的品牌选择。 |
| 39 | Gen-Centric Services / Q&A records | 聊天特征筛选 | 交互逻辑 | 默认 All features，可选 Web search／No web search。以保存记录的特征数组是否非空判断，选择立即生效并回到第 1 页。当前样例可能使 No web search 没有结果，不额外生成记录。 |
| 40 | Gen-Centric Services / Q&A records | 聊天来源筛选 | 交互逻辑 | 默认 All sources，选项来自已保存聊天的来源域名去重集合。选择后按域名精确匹配来源数组，立即更新结果并回到第 1 页。缺失的额外来源名称不生成筛选项。 |
| 41 | Gen-Centric Services / Q&A records | 配置聊天列 | 交互逻辑 | 点击配置图标，通过复选框立即显示／隐藏 Mentions、Sources、Features、Position、Created；Chat 为必保留列，复选框禁用。隐藏列不影响筛选、排序或导出字段，刷新后恢复默认列。 |
| 42 | Gen-Centric Services / Q&A records | 导出聊天 | 交互逻辑 | 点击导出图标选择 CSV 或 JSON。导出当前全部筛选结果及当前排序，不只导出当前页。CSV 包含模型、完整回答、已知品牌域名、已知来源域名、位置、创建时间；JSON 保留记录的原有字段。列显隐不改变导出字段。 |
| 43 | Gen-Centric Services / Q&A records | 展开聊天列表 | 交互逻辑 | 点击展开图标，打开当前全部筛选结果的宽版摘要列表，不按主表每页条数截断。点击记录打开聊天抽屉；该弹窗不提供独立搜索或分页。 |
| 44 | Gen-Centric Services / Q&A records | 聊天记录与总数 | 业务规则 | 当前仅有十条完整保存聊天；原页面的 90 条总量不代表本地可读取 90 条。首次进入按保存记录顺序，未主动设置默认排序字段；显示摘要、模型、提及品牌、来源、特征、品牌位置和相对保存日的时间。额外的 +N 为已保存计数，缺少名称时不能展开补全。 |
| 45 | Gen-Centric Services / Q&A records | 聊天表头排序 | 交互逻辑 | 点击表头或聚焦表头按 Enter，首次按该列升序，再次点击反向；切换列先升序并回到第 1 页。文本按字串；品牌／来源按含额外计数的数量；特征按数量；时间按距保存日天数；空位置视为无限大。相同值保留原始记录相对顺序；后续筛选保留排序。 |
| 46 | Gen-Centric Services / Q&A records | 品牌位置说明图标 | 字段说明 | 点击 Position 表头中的品牌图标提示：该列为虎虎保险在保存回答中的位置，横线表示没有记录位置。图标点击不会触发表头排序；不是保险产品优劣的排名。 |
| 47 | Gen-Centric Services / Q&A records | 聊天分页 | 交互逻辑 | 默认每页 10 条，可选 5 条。支持前页、后页和已显示的页码按钮，首末页禁用越界按钮，无自由输入跳页。更改每页条数回到第 1 页；筛选、日期和排序变化也回到第 1 页。总数按筛选后保存记录计算；没有新增或删除聊天操作。 |
| 48 | Gen-Centric Services / Q&A records | 无结果状态 | 交互逻辑 | 组合条件无匹配时隐藏数据行，显示 No chats match your filters 和 Clear filters，总数显示 0。点击 Clear filters 与综合筛选重置一致，清除模型、聊天品牌、来源、特征及日期限制；保留列、排序和每页条数。 |
| 49 | Gen-Centric Services / Q&A records | 打开聊天详情 | 交互逻辑 | 点击聊天行默认打开 Answer；点击 Mentions 或 Sources 单元格时直接打开对应页签；行聚焦后 Enter 打开 Answer。详情显示完整保存回答，未调用模型重新生成。相同操作规则适用于所有记录。 |
| 50 | Gen-Centric Services / Q&A records | 回答与品牌来源页签 | 交互逻辑 | Answer 展示提示词和完整回答，支持段落、列表、表格与外链；Mentions 展示已知品牌，点击进入品牌详情；Sources 展示已知来源及保存链接，点击来源进入详情、点击完整链接新开外部网页。缺失额外名称或链接时仅说明数量，不伪造数据。 |
| 51 | Gen-Centric Services / Q&A records | 上一条与下一条回答 | 业务规则 | Previous／Next 按全部十条保存记录的原始顺序切换，不受主列表筛选、排序和分页限制；每次切换回 Answer 页签。第一条禁用 Previous，最后一条禁用 Next。 |
| 52 | Gen-Centric Services / Q&A records | 复制完整回答 | 交互逻辑 | Copy answer 复制当前记录的原始回答文本，即使当前正在 Mentions／Sources 页签也复制回答。成功提示已复制；剪贴板不可用时下载 copied-text.txt。不复制主表截断摘要或页面标注内容。 |
