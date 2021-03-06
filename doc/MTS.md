## MTS 高频量化交易系统及策略研发平台 ##


* 针对中小型量化机构，量化团队的，易学易用的微内核模块化的日内高频量化交易及策略研发交易平台。
* 集策略研发及回测，参数优化和实盘交易于一体的综合性平台。
* 针对日内高频交易策略需求进行定制和优化。
* 系统运行在用户终端，不存在交易策略泄密问题。

### 问题 ###

1. 日内高频交易策略可以更好地把握市场机会，其需求正在逐渐受到重视，而市面相应的交易系统匮乏，一些系统从低频交易系统过渡而来，乏善可陈。
1. 日内高频交易所需的tick级别数据异常庞大和精细，其回测所需的时间大大增加，市场需要支持大数据量的回测加速技术。
1. 中小型私募基金公司，技术能力不足，只能购买针对个人的功能不足的交易系统或非法得到别的公司的交易系统代码，稍加修改后使用。
1. 大型私募公司大都组建自己的研发团队，各自开发自己的功能重复的交易系统，系统之间无法兼容，浪费资源。
1. 对于机构而言，交易策略保密性异常敏感。基于web的交易和研发平台没有保密性可言。


### 目标 ###

**让中小型私募基金公司不再需要开发部门，就可以做日内高频量化交易和回测。**
**降低量化交易的门槛，让更多人有机会参与进来；任何人只要对量化交易感兴趣，就可以成为一名宽客。**

### 受众 ###

中小型量化机构或团队，研究日内高频交易策略，强调效率和安全性。


### 特点 ###

1. 完整覆盖量化交易完整生命周期，支持策略研发、策略回测、参数优化、仿真交易、实盘交易与盘后分析优化全过程。
1. 策略研究回测和仿真直接在客户本地进行，安全性高。这点对于机构和团队尤其重要。
1. 微内核方式完全透明化回测模式和实盘模式。减少回测和实盘的逻辑差异，提高回测精准度。回测脚本几乎不需要修改，只需更改参数即可用于实盘交易。
1. 多种不同模式的回测撮合引擎，供用户自由选择使用。减小回测和实盘的差异。
1. 支持直接跨天回测，对于跨天交易策略可以完整方便回测所有历史。
1. 支持智能报单和算法交易。
1. 多种不同粒度数据回测支持。包括逐笔数据，分钟k线数据，日k线数据等。
1. 回测速度快，效率高。支持c++语言开发交易策略，最大程度提高回测速度。
1. 支持跨市场跨品种套利交易支持多账户交易管理
1. 同时支持手动下单交易，支持国内期货四大交易所，支持沪深股市，支持数字货币。
1. 可以结合mts的分布式回测加速系统（DSAS），加速回测速度，快速得出优化结果。
1. 覆盖多种主流开发语言（python，c++，javascript等），用户可以使用自己最熟悉的语言快速转化自己的策略思想。
1. 跨平台特性。同时支持市面三大主流操作系统（windows，Linux 和 MacOS 平台）。
1. 通过包装层，可以兼容市面上各种api（掘金，优矿，米框等），已有的策略几乎不用更改即可运行。

### MTS量化平台组成 ###


1. #### MTS Edgar 数据服务： ####
	在后台默默地提供数据和基础服务（前期用户通过ftp方式网络下载落地。以后可以建立数据服务，或和众多第三方数据提供商合作）；

1. #### MTS 交易核心 ####
	MTS 交易系统的核心，其具备报单管理，仓位管理，分账户/分策略管理，风险控制，算法交易等。

1. #### MTS 回测撮合引擎 ####
	MTS 回测撮合引擎，支持多种回测撮合模拟算法，负责回测时的报单撮合。

1. #### MTS SDK ####
	标准化了数据和交易接口，并以易用、开放、高性能为设计目标针对量化交易进行优化。SDK支持所有主流的编程开发语言，如C, C++, Python，Javascript等语言，最大程度地保证了平台的开放性。

2. #### MTS Cindy 实盘监控下单终端 ####
	基于MTS C++ SDK 的，提供完整的实盘监控和下单、撤单等功能的终端。相对于传统普通终端，具有区分查看各个策略报单和仓位的功能，并支持一键平仓的人工干预方式。

    ![](./images/cindy.png)

1. #### MTS Julia 量化研究终端 ####
	终端提供强大的可视化终端，为策略开发、研究、管理、运行监控、风险控制、信号分析提供一体化的的操作界面 。高级版本提供方便快捷的参数优化，根据不同的参数组合进行自动化回测，调优。帮助寻找到策略的最佳参数组合。

    ![](./images/julia.png)
    ![](./images/julia2.png)
    ![](./images/julia3.png)

1. #### MTS Galaxy 策略回测加速集群平台 ####
	对策略进行并行分布式调度和管理，提高回测的速度和吞吐量。使用并发技术，分布式技术，容器技术和云计算构建的回测加速集群平台。

3. #### MTS Douglas 个人化量化平台 ####
	通过简化和封装MTS SDK，对接现有的一些量化平台API（掘金，优矿，米框，聚宽等）。使的在这些量化平台上的已有策略可以直接运行。



### 支持哪些交易品种 ###

目前主要支持国内四大期货交易所的所有品种（包括股指期货，国债期货和商品期货），沪深股市的所有品种以及数字货币（比特币，以太坊等）。
以后会逐步支持期权，ETF，LOF，分级基金，现货，外汇等其他金融衍生品。

### API 文档 ###


请参见MTS API 手册
