### pybacktest 编程特点

察看源码多遍，感觉软件的设计和编程模式“高端、大气、上档次”，值得参考、学习。

1. pybacktest 采用了函数式编程，技术手段包括 lambda、闭包（嵌套函数）、@修饰函数等；
2. pybacktest 的类设计，使用了 \__dir\__、\__getattr\__、\__repr\__ 等特殊函数；
3. 数据结构几乎完全使用 pandas 的 Series 和 DataFrame；

### pybacktest 的交易策略接口

原作 tutorial 给出了交易策略的接口，4个 Series ，即 buy,sell,cover,short (后2个是重复的冗余），分别表示买点和卖点。

### pybacktest 的基本用法

1. 取得股票某段时期的价格数据 ohlc即开盘价、最高价、最低价、收盘价；
2. 运算价格数据，确定各个买入、卖出的时间点，形成 buy 和 sell 两个 Series；
3. 调用 bt = pybacktest.Backtest(locals())，将 2 个 Series 等数据付给回测模块；
4. 调用 bt.summary()，令统计引擎计算该交易策略的损益结果；
5. 分别调用 bt.plot_equity()、bt.plot_trades() 和 bt.trdplot\['2016':'2017‘]），画出交易策略的3种运用结果

