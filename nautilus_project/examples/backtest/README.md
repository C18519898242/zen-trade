# 回测示例 (Backtest Examples)

这个目录包含了 NautilusTrader 的回测示例，展示了如何使用平台的不同功能。

## 示例 1: 从自定义 CSV 加载 K线 (example_01_load_bars_from_custom_csv)

这个示例演示了如何从自定义的 CSV 文件加载 K线数据到 NautilusTrader 中。它展示了以下步骤：
- 配置和创建回测引擎。
- 定义交易所并将其添加到引擎。
- 创建合约定义并将其添加到引擎。
- 从 CSV 文件加载 K线数据到 Pandas DataFrame。
- 将 DataFrame 重构为 `BarDataWrangler` 所需的结构（包含 'open', 'high', 'low', 'close', 'volume' 列，并以 'timestamp' 作为索引）。
- 定义加载 K线的类型。
- 使用 `BarDataWrangler` 将每一行转换为 `Bar` 对象。
- 将加载的数据添加到引擎。
- 创建策略并将其添加到引擎。
- 运行回测并释放系统资源。

这个示例的重点在于如何将外部的 K线数据导入到 NautilusTrader 中进行回测。

## 示例 2: 使用时钟定时器 (example_02_use_clock_timer)

这个示例展示了如何在 NautilusTrader 策略中使用 **定时器 (Timer)** 功能。
该策略通过在固定的时间间隔内运行操作，同时处理市场数据事件。它展示了 **定时器事件** 和 **市场数据** 如何同时独立工作。

这个策略的功能包括：
- 使用 NautilusTrader 的定时器按计划触发事件。
- 独立处理市场数据和定时器事件。

这有助于您了解定时器如何与市场数据处理并行工作而互不干扰。

## 示例 3: K线聚合 (example_03_bar_aggregation)

这个示例演示了如何使用 NautilusTrader 的 **K线聚合** 功能，从较低时间周期的数据创建较高时间周期的 K线。

具体来说，这个策略展示了如何：
- 从 CSV 文件加载 1 分钟的 K线数据。
- 使用内部聚合功能，从 1 分钟数据创建 5 分钟的 K线。
- 在同一个策略中独立处理这两种时间周期的数据。

这个示例旨在帮助您理解 NautilusTrader 中 K线聚合的工作原理，以及如何在您的策略中处理多个时间周期。
