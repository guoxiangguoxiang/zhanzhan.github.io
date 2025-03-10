<div style="display: flex; flex-direction: column; justify-content: center; align-items: center">
  <div style="font-size: 27px; margin: 12px 0px"><strong>詹晓秋</strong></div>
  <div style="font-size: 18px;">15306598108 | 289463414@qq.com</div>
  <div style="font-size: 18px;margin: 12px 0px">求职意向：前端开发 | 期望城市：深圳/北京/上海/杭州</div>
</div>



## 教育经历

<div style="display: flex; justify-content: space-between;">
  <div style="font-size: 18px;"><strong>浙江大学</strong></div>
  <div style="font-size: 18px;">2018年09月 - 2021年03月</div>
</div>

机械制造及自动化  硕士

- GPA：3.38/4.00
- 荣誉/奖项：校一等奖学金

<div style="display: flex; justify-content: space-between;">
  <div style="font-size: 18px;"><strong>中国计量大学</strong></div>
  <div style="font-size: 18px;">2013年09月 - 2017年06月</div>
</div>

工业工程管理  本科

- 荣誉/奖项：院二等奖学金(2013-2016)、国际大学生数学建模竞赛二等奖(2016)、全国大学生数学建模竞赛省三等奖(2015)

- 英语（CET-6）

  

## 技能清单

- **语言**：熟悉JavaScript、TypeScript、ES6、CSS、HTML、Webpack等常用技术

- **开发工具** ：熟练使用 VSCode、Git等开发工具

- **框架** ：熟练掌握React等开发框架

  

## 工作经历

<div style="display: flex; justify-content: space-between;">
  <div style="font-size: 18px;"><strong>酷家乐（2021 年 09 月 ~ 2025 年 01 月共计3年3个月 ）</strong></div>
  <div style="font-size: 18px;">软件高级开发工程师</div>
</div>

1. 负责棚拍影棚页、影棚详情页、镜头设置工具页和管理后台业务的功能迭代与稳定性建设。

2. 负责办公家具业务功能的开发与稳定性建设，业务监控链路完善，统一编码规范、提高测试覆盖率、重构核心代码。

   

## 项目经历

<div style="display: flex; justify-content: space-between; margin: 12px 0 0 0">
  <div style="font-size: 18px;"><strong>办公易用性技术提升项目（2022 年 07 月 - 2025 年 01 月）</strong></div>
  <div style="font-size: 18px;">软件高级开发工程师</div>
</div>

#### 项目描述

竞品CET有许多独有功能酷家乐无法满足，该卡点也是阻碍办公头部客户迟迟无法续约的根本原因，进而导致办公业务无法推广，因此该项目的核心任务是扫清前端工具的可用性卡点，促进办公解决方案在圣奥、震旦等打样KA的落地推广，完成客户内CET软件替代，保障续约，完成办公在中小企业的推广。项目预期收入：**737.5万元~1216.8万元**，预期投入总计：**245.36万**，优先级 ：**P0**。

#### 成果

办公建模和设计的卡点功能成功上线，提升了实施和设计效率，业务方全部验收通过，实施周期**缩短50%**，方案设计时长**缩短50%**，促成办公KA流量增长，最后**震旦、圣奥成功续约**。

#### 工作内容/个人职责

本人在此项目中主要负责以下需求，此类需求均为影响续约的卡点功能，均在预期时间内顺利完成：
- **模式外接入办公基本能力**
  - 模型SelectMenu：复制、固定间距、快速旋转、删除、前处理检测、装配检测等核心按钮
  - 场景内功能：选中、高亮、多选、三轴控件、尺寸线、方向键移动、拖拽、下层选中等核心功能
  - 右侧参数面板：尺寸信息、位置信息、风格样式等参数修改
- 模型快速旋转&固定间距摆放
- 文本标记功能
- 出现点模式设计
- 水平/垂直对齐分布
- 矩形阵列、线性阵列、环形阵列功能接入
- 装配连接样式改版

##### 1. 模式外接入办公能力

**1.1. 概述**

由于模式外无法使用办公主功能，导致办公工具迟迟得不到推广。当前在办公模式外（云图）操作办公模型后会导致模型断开或者没有正确更新，长期以来的处理方式是通过模型隔离禁止选中和清除撤销恢复栈来规避操作模型可能的风险。为了解决该问题，需要在云图中支持办公模型主要核心能力。

**1.2. 难点&优化**

**（1）多种类型模型多种交互场景实现相同功能操作**

  不同对象在不同交互场景中绝大部分要实现的操作功能均相同，比如复制、删除、隐藏、组合等功能，各项功能根据不同对象产生不同的核心逻辑，不同交互场景只是对核心逻辑的扩展处理，模式内面向功能进行逻辑接入，**代码冗余且重复，扩展性差**，如果一处功能需要进行增删改，则需要在所有接入该功能的逻辑内修改，且故障修复困难，一处功能出现故障，可能需要修改多处，甚至会出现遗漏的情况。
  
  ​**优化设计：多模型多功能配置收集器**
  
  不同类型对象在初始化时配置需要挂载的功能方法，收集器收集用户按照对象类型配置的功能方法进行缓存，当某一功能触发时，收集器根据对象类型进行方法过滤与分类，同时依次执行对应的配置方法。

**（2）Application核心文件代码堆叠复杂，仅考虑到模式内核心逻辑**

  核心Application由于历史债包袱，仅当前模式内注册逻辑就有上千行，如果模式外在Application文件内继续注入业务注册逻辑，将导致该文件过于庞大，后期维护越来越困难，且该文件为核心文件，出现问题，造成的影响面会过大，因此该处重构优化迫在眉睫。
  
  **优化设计：面向执行时机的事件监听机制**
  
  1. ​核心思路为**订阅派发模式，设计一个通用的事件监听器，根据约定的标识符注测对应的订阅派发事件**。办公将执行时机作为事件标识符进行监听对象收集。按照执行时机拆分完代码后，我们再根据功能进行代码的二次拆分。
  2. ​**设计一个hook收集类**，以功能为依据将代码拆分为功能hook。

  ​最终形成一条按照**执行时机订阅事件——Application根据执行时机派发事件——依次执行功能hook——移除hook——注销事件监听完整的订阅派发链路**。​该重构的成功执行厘清了办公复杂核心代码，提升了开发人员效率，提升了代码维护性，因此得到了推广，效仿此次重构又扩展了办公退出进入时机、方案加载时机等一些核心代码的事件订阅机制。

**（3）模型加载顺序问题与加载异常处理**

  由于装配模型是在定制模型基础上创建的，因此在定制模型未加载成功前或定制模型加载异常时创建的装配模型属于无效模型，历史方案是将装配模型延时100毫秒解决，该方案覆盖98%的模型加载问题，但是对于比较简单的模型来时，时间过长，影响性能。
  
  **优化设计：异步任务队列**
  
  1. ​创建异步任务队列，将装配模型加载完成前需要执行的异步任务添加进任务队列中，finally模块中迭代执行异步任务。
  2. 为防止某一异步任务阻塞进度，我们新增计时器并透出是否匹配计时器属性，对不影响装配模型形成的异步任务添加计时器，每一个异步任务与一个计时器同时放入Promise.race中进行比较，如果某一任务超时加载，则报出异常，但不阻塞后续加载。

**（4）模式内外数据备份同步&模型更新性能优化**

  装配内外模式进行切换后，如果数据备份不一致，则会造成装配数据丢失的问题，导致模式外装配操作均为无效操作。且旧有模型更新链路为装配模型属性更新驱动定制模型更新，但当前技术壁垒（装配核心代码与基类代码在二方包内，二方包仅在装配模式内加载），使得模式外无法获取到模式内的装配数据备份从而无法及时更新与渲染装配模型。
  
  **优化设计：**
  
  ​模式外单独创建一份装配数据备份，仅做核心数据处理。同时将备份文档分为底层数据类和业务操作类，业务操作类封装针对底层数据的各种业务操作方法，比如合并数据，复制时对底层数据的处理。原始模型更新路线为装配属性值更新驱动定制模型更新渲染，装配响应定制再次更新的二次更新机制，通过仅做数据更新处理，将原有更新路线改为定制模型更新渲染——>装配仅做数据同步的一次更新机制。

<div style="display: flex; justify-content: space-between; margin: 12px 0 0 0">
  <div style="font-size: 18px;"><strong>办公重点客户冲刺计划（2023 年 01 月 - 2023 年 08 月）</strong></div>
  <div style="font-size: 18px;">软件高级开发工程师</div>
</div>

#### 项目描述

为提升头部用户工作效率，提升办公工具专业度与体验，扩大解决方案在头部客户终端的推广，办公侧成立项目组推动震旦、圣奥系列需求的执行。项目投入总计：302.5人天，跨敏捷组个数：7，优先级：**P0**

#### 成果

震旦、圣奥作为办公家具行业的头部客户，对行业有标杆效应，且产品开发需求通用性强。本项目的成功落地，使得震旦、圣奥**性能优化突破2000平大方案瓶颈**，（设计+报价方案+一键下单）等一系列功能的落地，助力震旦六月份的成功推广，大大提升了用户办公效率，**直接助力商务拿下百丽家居**，**合同金额200W+**。

#### 工作内容/个人职责

本人主要负责以下需求，此类需求均为冲刺计划内卡点功能，并在预期时间内顺利完成，促进了震旦、圣奥落地与推广：
- **通用性装配检测引擎**
- 复制&连续复制通用性设计
- 新版左侧素材栏开发
- 装配中间态屏蔽
- 撤销恢复

##### 1. 装配检测引擎通用性设计

**1.1. 概述**

由于装配连接会出现非预期的连接无效或者异常断开的情况，对用户后续操作产生严重影响，进而产生资损，针对此核心场景，设计了不同的拦截功能，包括未装配模型爆红框、手动装配检测、下单检测、预处理检测、自检系统报错。

**1.2. 难点**

**（1）通用检测设计**

  装配检测功能链路为：对模型类型筛查过滤，将处理后的模型数据根据触发的不同检测功能进行对应的检测算法检测，最后根据触发的功能进行结果展示。由于触发功能、触发时机和检测入口各不相同，且处理对象也均不相同，多种类型的检测对象+多种检测类型+多种调用方会形成多种排列组合，我们需要设计一个可扩展上下游的通用检测设计。且检测设计还需要考虑到以后未知的检测类型扩展，以及检测对象扩展。
  
  **优化设计：装配检测引擎**
  
  该装配检测引擎设计核心思想遵循**最小单元化，核心模式为工厂方法设计模式**。将装配检测引擎核心抽象成数据预处理、检测单元和检测后处理三大工厂类。外部的应用层可以通过组合任意的检测单元，组合成业务方需要的检测任务。装配检测引擎作为生成器，根据下游业务场景送检信息调度三大工厂，生成检测结果返回给调用方。

**（2）检测性能卡点**

  在约3000平建面、2300万面片、方案数据3GB+的环境下，装配检测整个流程持续40秒左右，大大影响用户使用体验，是项目主要的性能卡点。通过Performance的性能工具分析后，**卡点问题**主要存在于在以下业务逻辑内：
  1. 检测前进行方案保存，后端接口耗时较多，20%左右。
  2. 检测后方案模型数据变化，触发LOD行为，占比30%左右。

**优化设计：基于脏更新过滤的检测前置与增量保存异步逻辑后置的分离优化方法**
  
  1. 对方案数据进行脏更新增量过滤，以模型基本参数属性作为计算颗粒度对方案数据进行打标，将筛选后的数据送检
  2. 装配检测可以作为不依赖后端的纯前端逻辑前置，将增量的保存逻辑后置异步，交予整个工具的增量保存队列中，这样不仅不影响用户体验，同时在保存数据一致性的前提下，减少了LOD行为的执行，大大缩短了保存时间。

以上性能优化缩短了约90%的用户操作时间，将40秒的等待时间优化至6秒左右，提升了用户对检测功能的体验，同时提高了接入检测引擎的下游业务功能的效率。

<div style="display: flex; justify-content: space-between; margin: 12px 0 0 0">
  <div style="font-size: 18px;"><strong>办公稳定性保障项目（2023 年 10 月 - 2024 年 06 月）</strong></div>
  <div style="font-size: 18px;">软件高级开发工程师</div>
</div>

#### 项目描述

圣奥需要在2024年8月全面推广，震旦需要在2024年10月全面推广，在5月底之前，需要全面保障业务底层稳定，保障办公核心链路业务功能不回退。

#### 成果

项目成果的成功落地，保障了产品线上稳定性的长期治理和有效运作，建立的监控链路以及配合测试搭建的办公自动化测试框架有效辅助开发测试提早发现异常，加速了问题定位。办公单测全链路覆盖提前暴露了功能问题导致效果不符合预期的潜在资损问题。

#### 工作内容/个人职责

本人主要负责以下需求，成果均已落地且为开发人员和测试人员提供了强有力的辅助，定位问题的效率得到了质的飞跃：
- 工程化层级目录治理
- 办公家具前端稳定性监控链路
- 办公家具性能监控链路
- 办公自动化拆分
- 办公单元测试全链路覆盖

<div style="display: flex; justify-content: space-between; margin: 12px 0 0 0">
  <div style="font-size: 18px;"><strong>棚拍（2021 年 09 月 - 2022 年 06 月 ）</strong></div>
  <div style="font-size: 18px;">软件开发培训生</div>
</div>

#### 项目描述

针对没有线下门店的商家，决策链路短，用户在购买之前唯一可以感知的全部内容便是放虚拟店铺上的图，棚拍就是搭建生态的平台方，为不同的产品提供理想的影棚进行拍摄。

#### 成果

虚拟棚拍自改版以来，目前已经发展到千万级别回款，同时保持200+%的指数级增长趋势。棚拍在软装行业内的产品完善度上已经到达了一个平台期，并且借助诸多大KA的案例（顾家、联邦、美克美家等）树立了具有号召力的产品品牌形象，同时可以借助棚拍的产品影响力正向赋能其他产品。

#### 工作内容/个人职责

- 选择影棚页、影棚详情页、镜头设置工具页改版
- 管理后台开发，包括影棚专题、影棚看板、HDR管理、账号权限管理
- 优化预览效果与待拍视角页面，达到批量拍摄、批量预览、批量选择、批量生成的效果

<p style="text-align: right;">感谢您花时间阅读我的简历，期待能与您共事！</p>
<div style="page-break-after: always;"></div>
