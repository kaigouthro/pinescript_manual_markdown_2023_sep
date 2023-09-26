## bar_index

Current bar index. Numbering is zero-based, index of the first bar is 0.

### Type

series int

### Example

```
//@version=5indicator("bar_index")plot(bar_index)plot(bar_index > 5000 ? close : 0)
```

### Remarks

Note that **bar_index** has replaced **n** variable in version 4.

Note that bar indexing starts from 0 on the first historical bar.

Please note that using this variable/function can cause [indicator repainting](https://www.tradingview.com/pine-script-docs/en/v5/concepts/Repainting.html).

### See also

[last_bar_index](#var_last_bar_index)[barstate.isfirst](#var_barstate.isfirst)[barstate.islast](#var_barstate.islast)[barstate.isrealtime](#var_barstate.isrealtime)

## barstate.isconfirmed

Returns true if the script is calculating the last (closing) update of the current bar. The next script calculation will be on the new bar data.

### Type

` series bool `

### Remarks

PineScript code that uses this variable could calculate differently on history and real-time data.

It is NOT recommended to use [barstate.isconfirmed](#var_barstate.isconfirmed) in [request.security](#fun_request.security) expression. Its value requested from [request.security](#fun_request.security) is unpredictable.

Please note that using this variable/function can cause [indicator repainting](https://www.tradingview.com/pine-script-docs/en/v5/concepts/Repainting.html).

### See also

[barstate.isfirst](#var_barstate.isfirst)[barstate.islast](#var_barstate.islast)[barstate.ishistory](#var_barstate.ishistory)[barstate.isrealtime](#var_barstate.isrealtime)[barstate.isnew](#var_barstate.isnew)[barstate.islastconfirmedhistory](#var_barstate.islastconfirmedhistory)

## barstate.isfirst

Returns true if current bar is first bar in barset, false otherwise.

### Type

` series bool `

### Remarks

PineScript code that uses this variable could calculate differently on history and real-time data.

Please note that using this variable/function can cause [indicator repainting](https://www.tradingview.com/pine-script-docs/en/v5/concepts/Repainting.html).

### See also

[barstate.islast](#var_barstate.islast)[barstate.ishistory](#var_barstate.ishistory)[barstate.isrealtime](#var_barstate.isrealtime)[barstate.isnew](#var_barstate.isnew)[barstate.isconfirmed](#var_barstate.isconfirmed)[barstate.islastconfirmedhistory](#var_barstate.islastconfirmedhistory)

## barstate.ishistory

Returns true if current bar is a historical bar, false otherwise.

### Type

` series bool `

### Remarks

PineScript code that uses this variable could calculate differently on history and real-time data.

Please note that using this variable/function can cause [indicator repainting](https://www.tradingview.com/pine-script-docs/en/v5/concepts/Repainting.html).

### See also

[barstate.isfirst](#var_barstate.isfirst)[barstate.islast](#var_barstate.islast)[barstate.isrealtime](#var_barstate.isrealtime)[barstate.isnew](#var_barstate.isnew)[barstate.isconfirmed](#var_barstate.isconfirmed)[barstate.islastconfirmedhistory](#var_barstate.islastconfirmedhistory)

## barstate.islast

Returns true if current bar is the last bar in barset, false otherwise. This condition is true for all real-time bars in barset.

### Type

` series bool `

### Remarks

PineScript code that uses this variable could calculate differently on history and real-time data.

Please note that using this variable/function can cause [indicator repainting](https://www.tradingview.com/pine-script-docs/en/v5/concepts/Repainting.html).

### See also

[barstate.isfirst](#var_barstate.isfirst)[barstate.ishistory](#var_barstate.ishistory)[barstate.isrealtime](#var_barstate.isrealtime)[barstate.isnew](#var_barstate.isnew)[barstate.isconfirmed](#var_barstate.isconfirmed)[barstate.islastconfirmedhistory](#var_barstate.islastconfirmedhistory)

## barstate.islastconfirmedhistory

Returns true if script is executing on the dataset's last bar when market is closed, or script is executing on the bar immediately preceding the real-time bar, if market is open. Returns false otherwise.

### Type

` series bool `

### Remarks

PineScript code that uses this variable could calculate differently on history and real-time data.

Please note that using this variable/function can cause [indicator repainting](https://www.tradingview.com/pine-script-docs/en/v5/concepts/Repainting.html).

### See also

[barstate.isfirst](#var_barstate.isfirst)[barstate.islast](#var_barstate.islast)[barstate.ishistory](#var_barstate.ishistory)[barstate.isrealtime](#var_barstate.isrealtime)[barstate.isnew](#var_barstate.isnew)

## barstate.isnew

Returns true if script is currently calculating on new bar, false otherwise. This variable is true when calculating on historical bars or on first update of a newly generated real-time bar.

### Type

` series bool `

### Remarks

PineScript code that uses this variable could calculate differently on history and real-time data.

Please note that using this variable/function can cause [indicator repainting](https://www.tradingview.com/pine-script-docs/en/v5/concepts/Repainting.html).

### See also

[barstate.isfirst](#var_barstate.isfirst)[barstate.islast](#var_barstate.islast)[barstate.ishistory](#var_barstate.ishistory)[barstate.isrealtime](#var_barstate.isrealtime)[barstate.isconfirmed](#var_barstate.isconfirmed)[barstate.islastconfirmedhistory](#var_barstate.islastconfirmedhistory)

## barstate.isrealtime

Returns true if current bar is a real-time bar, false otherwise.

### Type

` series bool `

### Remarks

PineScript code that uses this variable could calculate differently on history and real-time data.

Please note that using this variable/function can cause [indicator repainting](https://www.tradingview.com/pine-script-docs/en/v5/concepts/Repainting.html).

### See also

[barstate.isfirst](#var_barstate.isfirst)[barstate.islast](#var_barstate.islast)[barstate.ishistory](#var_barstate.ishistory)[barstate.isnew](#var_barstate.isnew)[barstate.isconfirmed](#var_barstate.isconfirmed)[barstate.islastconfirmedhistory](#var_barstate.islastconfirmedhistory)

## box.all

Returns an array filled with all the current boxes drawn by the script.

### Type

` box[] `

### Example

```
//@version=5indicator("box.all")//delete all boxesbox.new(time, open, time + 60 * 60 * 24, close, xloc=xloc.bar_time, border_style=line.style_dashed)a_allBoxes = box.allif array.size(a_allBoxes) > 0    for i = 0 to array.size(a_allBoxes) - 1        box.delete(array.get(a_allBoxes, i))
```

### Remarks

The array is read-only. Index zero of the array is the ID of the oldest object on the chart.

### See also

[box.new](#fun_box.new)[line.all](#var_line.all)[label.all](#var_label.all)[table.all](#var_table.all)

## chart.bg_color

Returns the color of the chart's background from the "Chart settings/Appearance/Background" field. When a gradient is selected, the middle point of the gradient is returned.

### Type

` input color `

### See also

[chart.fg_color](#var_chart.fg_color)

## chart.fg_color

Returns a color providing optimal contrast with [chart.bg_color](#var_chart.bg_color).

### Type

` input color `

### See also

[chart.bg_color](#var_chart.bg_color)

## chart.is_heikinashi

### Type

` simple bool `

### Returns

Returns [true](#op_true) if the chart type is Heikin Ashi, [false](#op_false) otherwise.

### See also

[chart.is_renko](#var_chart.is_renko)[chart.is_linebreak](#var_chart.is_linebreak)[chart.is_kagi](#var_chart.is_kagi)[chart.is_pnf](#var_chart.is_pnf)[chart.is_range](#var_chart.is_range)

## chart.is_kagi

### Type

` simple bool `

### Returns

Returns [true](#op_true) if the chart type is Kagi, [false](#op_false) otherwise.

### See also

[chart.is_renko](#var_chart.is_renko)[chart.is_linebreak](#var_chart.is_linebreak)[chart.is_heikinashi](#var_chart.is_heikinashi)[chart.is_pnf](#var_chart.is_pnf)[chart.is_range](#var_chart.is_range)

## chart.is_linebreak

### Type

` simple bool `

### Returns

Returns [true](#op_true) if the chart type is Line break, [false](#op_false) otherwise.

### See also

[chart.is_renko](#var_chart.is_renko)[chart.is_heikinashi](#var_chart.is_heikinashi)[chart.is_kagi](#var_chart.is_kagi)[chart.is_pnf](#var_chart.is_pnf)[chart.is_range](#var_chart.is_range)

## chart.is_pnf

### Type

` simple bool `

### Returns

Returns [true](#op_true) if the chart type is Point & figure, [false](#op_false) otherwise.

### See also

[chart.is_renko](#var_chart.is_renko)[chart.is_linebreak](#var_chart.is_linebreak)[chart.is_kagi](#var_chart.is_kagi)[chart.is_heikinashi](#var_chart.is_heikinashi)[chart.is_range](#var_chart.is_range)

## chart.is_range

### Type

` simple bool `

### Returns

Returns [true](#op_true) if the chart type is Range, [false](#op_false) otherwise.

### See also

[chart.is_renko](#var_chart.is_renko)[chart.is_linebreak](#var_chart.is_linebreak)[chart.is_kagi](#var_chart.is_kagi)[chart.is_pnf](#var_chart.is_pnf)[chart.is_heikinashi](#var_chart.is_heikinashi)

## chart.is_renko

### Type

` simple bool `

### Returns

Returns [true](#op_true) if the chart type is Renko, [false](#op_false) otherwise.

### See also

[chart.is_heikinashi](#var_chart.is_heikinashi)[chart.is_linebreak](#var_chart.is_linebreak)[chart.is_kagi](#var_chart.is_kagi)[chart.is_pnf](#var_chart.is_pnf)[chart.is_range](#var_chart.is_range)

## chart.is_standard

### Type

` simple bool `

### Returns

Returns [true](#op_true) if the chart type is bars, candles, hollow candles, line, area or baseline, [false](#op_false) otherwise.

### See also

[chart.is_renko](#var_chart.is_renko)[chart.is_linebreak](#var_chart.is_linebreak)[chart.is_kagi](#var_chart.is_kagi)[chart.is_pnf](#var_chart.is_pnf)[chart.is_range](#var_chart.is_range)[chart.is_heikinashi](#var_chart.is_heikinashi)

## chart.left_visible_bar_time

The [time](#var_time) of the leftmost bar currently visible on the chart.

### Type

` input int `

### Remarks

Scripts using this variable will automatically re-execute when its value updates to reflect changes in the chart, which can be caused by users scrolling the chart, or new real-time bars.

### See also

[chart.right_visible_bar_time](#var_chart.right_visible_bar_time)

## chart.right_visible_bar_time

The [time](#var_time) of the rightmost bar currently visible on the chart.

### Type

` input int `

### Remarks

Scripts using this variable will automatically re-execute when its value updates to reflect changes in the chart, which can be caused by users scrolling the chart, or new real-time bars.

### See also

[chart.left_visible_bar_time](#var_chart.left_visible_bar_time)

## close

Close price of the current bar when it has closed, or last traded price of a yet incomplete, realtime bar.

### Type

` series float `

### Remarks

Previous values may be accessed with square brackets operator [], e.g. close[1], close[2].

### See also

[open](#var_open)[high](#var_high)[low](#var_low)[volume](#var_volume)[time](#fun_time)[hl2](#var_hl2)[hlc3](#var_hlc3)[hlcc4](#var_hlcc4)[ohlc4](#var_ohlc4)

## dayofmonth

Date of current bar time in exchange timezone.

### Type

` series int `

### Remarks

Note that this variable returns the day based on the time of the bar's open. For overnight sessions (e.g. EURUSD, where Monday session starts on Sunday, 17:00) this value can be lower by 1 than the day of the trading day.

### See also

[dayofmonth](#fun_dayofmonth)[time](#var_time)[year](#var_year)[month](#var_month)[weekofyear](#var_weekofyear)[dayofweek](#var_dayofweek)[hour](#var_hour)[minute](#var_minute)[second](#var_second)

## dayofweek

Day of week for current bar time in exchange timezone.

### Type

` series int `

### Remarks

Note that this variable returns the day based on the time of the bar's open. For overnight sessions (e.g. EURUSD, where Monday session starts on Sunday, 17:00) this value can be lower by 1 than the day of the trading day.

You can use [dayofweek.sunday](#var_dayofweek.sunday), [dayofweek.monday](#var_dayofweek.monday), [dayofweek.tuesday](#var_dayofweek.tuesday), [dayofweek.wednesday](#var_dayofweek.wednesday), [dayofweek.thursday](#var_dayofweek.thursday), [dayofweek.friday](#var_dayofweek.friday) and [dayofweek.saturday](#var_dayofweek.saturday) variables for comparisons.

### See also

[dayofweek](#fun_dayofweek)[time](#var_time)[year](#var_year)[month](#var_month)[weekofyear](#var_weekofyear)[dayofmonth](#var_dayofmonth)[hour](#var_hour)[minute](#var_minute)[second](#var_second)

## earnings.future_eps

Returns the estimated Earnings per Share of the next earnings report in the currency of the instrument, or [na](#var_na) if this data isn't available.

### Type

` series float `

### Remarks

This value is only fetched once during the script's initial calculation. The variable will return the same value until the script is recalculated, even after the expected time of the next earnings report.

### See also

[request.earnings](#fun_request.earnings)

## earnings.future_period_end_time

Checks the data for the next earnings report and returns the UNIX timestamp of the day when the financial period covered by those earnings ends, or [na](#var_na) if this data isn't available.

### Type

` series float `

### Remarks

This value is only fetched once during the script's initial calculation. The variable will return the same value until the script is recalculated, even after the expected time of the next earnings report.

### See also

[request.earnings](#fun_request.earnings)

## earnings.future_revenue

Returns the estimated Revenue of the next earnings report in the currency of the instrument, or [na](#var_na) if this data isn't available.

### Type

` series float `

### Remarks

This value is only fetched once during the script's initial calculation. The variable will return the same value until the script is recalculated, even after the expected time of the next earnings report.

### See also

[request.earnings](#fun_request.earnings)

## earnings.future_time

Returns a UNIX timestamp indicating the expected time of the next earnings report, or [na](#var_na) if this data isn't available.

### Type

` series float `

### Remarks

This value is only fetched once during the script's initial calculation. The variable will return the same value until the script is recalculated, even after the expected time of the next earnings report.

### See also

[request.earnings](#fun_request.earnings)

## high

Current high price.

### Type

` series float `

### Remarks

Previous values may be accessed with square brackets operator [], e.g. high[1], high[2].

### See also

[open](#var_open)[low](#var_low)[close](#var_close)[volume](#var_volume)[time](#fun_time)[hl2](#var_hl2)[hlc3](#var_hlc3)[hlcc4](#var_hlcc4)[ohlc4](#var_ohlc4)

## hl2

Is a shortcut for (high + low)/2

### Type

` series float `

### See also

[open](#var_open)[high](#var_high)[low](#var_low)[close](#var_close)[volume](#var_volume)[time](#fun_time)[hlc3](#var_hlc3)[hlcc4](#var_hlcc4)[ohlc4](#var_ohlc4)

## hlc3

Is a shortcut for (high + low + close)/3

### Type

` series float `

### See also

[open](#var_open)[high](#var_high)[low](#var_low)[close](#var_close)[volume](#var_volume)[time](#fun_time)[hl2](#var_hl2)[hlcc4](#var_hlcc4)[ohlc4](#var_ohlc4)

## hlcc4

Is a shortcut for (high + low + close + close)/4

### Type

` series float `

### See also

[open](#var_open)[high](#var_high)[low](#var_low)[close](#var_close)[volume](#var_volume)[time](#fun_time)[hl2](#var_hl2)[hlc3](#var_hlc3)[ohlc4](#var_ohlc4)

## hour

Current bar hour in exchange timezone.

### Type

` series int `

### See also

[hour](#fun_hour)[time](#var_time)[year](#var_year)[month](#var_month)[weekofyear](#var_weekofyear)[dayofmonth](#var_dayofmonth)[dayofweek](#var_dayofweek)[minute](#var_minute)[second](#var_second)

## label.all

Returns an array filled with all the current labels drawn by the script.

### Type

` label[] `

### Example

```
//@version=5indicator("label.all")//delete all labelslabel.new(bar_index, close)a_allLabels = label.allif array.size(a_allLabels) > 0    for i = 0 to array.size(a_allLabels) - 1        label.delete(array.get(a_allLabels, i))
```

### Remarks

The array is read-only. Index zero of the array is the ID of the oldest object on the chart.

### See also

[label.new](#fun_label.new)[line.all](#var_line.all)[box.all](#var_box.all)[table.all](#var_table.all)

## last_bar_index

Bar index of the last chart bar. Bar indices begin at zero on the first bar.

### Type

` series int `

### Example

```
//@version=5strategy("Mark Last X Bars For Backtesting", overlay = true, calc_on_every_tick = true)lastBarsFilterInput = input.int(100, "Bars Count:")// Here, we store the 'last_bar_index' value that is known from the beginning of the script's calculation.// The 'last_bar_index' will change when new real-time bars appear, so we declare 'lastbar' with the 'var' keyword.var lastbar = last_bar_index// Check if the current bar_index is 'lastBarsFilterInput' removed from the last bar on the chart, or the chart is traded in real-time.allowedToTrade = (lastbar - bar_index <= lastBarsFilterInput) or barstate.isrealtimebgcolor(allowedToTrade ? color.new(color.green, 80) : na)
```

### Returns

Last historical bar index for closed markets, or the real-time bar index for open markets.

### Remarks

Please note that using this variable can cause [indicator repainting](https://www.tradingview.com/pine-script-docs/en/v5/concepts/Repainting.html).

### See also

[bar_index](#var_bar_index)[last_bar_time](#var_last_bar_time)[barstate.ishistory](#var_barstate.ishistory)[barstate.isrealtime](#var_barstate.isrealtime)

## last_bar_time

Time in UNIX format of the last chart bar. It is the number of milliseconds that have elapsed since 00:00:00 UTC, 1 January 1970.

### Type

` series int `

### Remarks

Please note that using this variable/function can cause [indicator repainting](https://www.tradingview.com/pine-script-docs/en/v5/concepts/Repainting.html).

Note that this variable returns the timestamp based on the time of the bar's open.

### See also

[time](#var_time)[timenow](#var_timenow)[timestamp](#fun_timestamp)[last_bar_index](#var_last_bar_index)

## line.all

Returns an array filled with all the current lines drawn by the script.

### Type

` line[] `

### Example

```
//@version=5indicator("line.all")//delete all linesline.new(bar_index - 10, close, bar_index, close)a_allLines = line.allif array.size(a_allLines) > 0    for i = 0 to array.size(a_allLines) - 1        line.delete(array.get(a_allLines, i))
```

### Remarks

The array is read-only. Index zero of the array is the ID of the oldest object on the chart.

### See also

[line.new](#fun_line.new)[label.all](#var_label.all)[box.all](#var_box.all)[table.all](#var_table.all)

## linefill.all

Returns an array filled with all the current linefill objects drawn by the script.

### Type

` linefill[] `

### Remarks

The array is read-only. Index zero of the array is the ID of the oldest object on the chart.

## low

Current low price.

### Type

` series float `

### Remarks

Previous values may be accessed with square brackets operator [], e.g. low[1], low[2].

### See also

[open](#var_open)[high](#var_high)[close](#var_close)[volume](#var_volume)[time](#fun_time)[hl2](#var_hl2)[hlc3](#var_hlc3)[hlcc4](#var_hlcc4)[ohlc4](#var_ohlc4)

## minute

Current bar minute in exchange timezone.

### Type

` series int `

### See also

[minute](#fun_minute)[time](#var_time)[year](#var_year)[month](#var_month)[weekofyear](#var_weekofyear)[dayofmonth](#var_dayofmonth)[dayofweek](#var_dayofweek)[hour](#var_hour)[second](#var_second)

## month

Current bar month in exchange timezone.

### Type

` series int `

### Remarks

Note that this variable returns the month based on the time of the bar's open. For overnight sessions (e.g. EURUSD, where Monday session starts on Sunday, 17:00) this value can be lower by 1 than the month of the trading day.

### See also

[month](#fun_month)[time](#var_time)[year](#var_year)[weekofyear](#var_weekofyear)[dayofmonth](#var_dayofmonth)[dayofweek](#var_dayofweek)[hour](#var_hour)[minute](#var_minute)[second](#var_second)

## na

A keyword signifying "not available", indicating that a variable has no assigned value.

### Type

` simple na `

### Example

```
//@version=5indicator("na")// CORRECT// Plot no value when on bars zero to nine. Plot `close` on other bars.plot(bar_index < 10 ? na : close)// CORRECT ALTERNATIVE// Initialize `a` to `na`. Reassign `close` to `a` on bars 10 and later.float a = naif bar_index >= 10    a := closeplot(a)// INCORRECT// Trying to test the preceding bar's `close` for `na`.// Will not work correctly on bar zero, when `close[1]` is `na`.plot(close[1] == na ? close : close[1])// CORRECT// Use the `na()` function to test for `na`.plot(na(close[1]) ? close : close[1])// CORRECT ALTERNATIVE// `nz()` tests `close[1]` for `na`. It returns `close[1]` if it is not `na`, and `close` if it is.plot(nz(close[1], close))
```

### Remarks

Do not use this variable with [comparison operators](https://www.tradingview.com/pine-script-docs/en/v5/language/Operators.html#comparison-operators) to test values for `na`, as it might lead to unexpected behavior. Instead, use the [na](#fun_na) function. Note that `na` can be used to initialize variables when the initialization statement also specifies the variable's type.

### See also

[na](#fun_na)[nz](#fun_nz)[fixnan](#fun_fixnan)

## ohlc4

Is a shortcut for (open + high + low + close)/4

### Type

` series float `

### See also

[open](#var_open)[high](#var_high)[low](#var_low)[close](#var_close)[volume](#var_volume)[time](#fun_time)[hl2](#var_hl2)[hlc3](#var_hlc3)[hlcc4](#var_hlcc4)

## open

Current open price.

### Type

` series float `

### Remarks

Previous values may be accessed with square brackets operator [], e.g. open[1], open[2].

### See also

[high](#var_high)[low](#var_low)[close](#var_close)[volume](#var_volume)[time](#fun_time)[hl2](#var_hl2)[hlc3](#var_hlc3)[hlcc4](#var_hlcc4)[ohlc4](#var_ohlc4)

## second

Current bar second in exchange timezone.

### Type

` series int `

### See also

[second](#fun_second)[time](#var_time)[year](#var_year)[month](#var_month)[weekofyear](#var_weekofyear)[dayofmonth](#var_dayofmonth)[dayofweek](#var_dayofweek)[hour](#var_hour)[minute](#var_minute)

## session.isfirstbar

Returns [true](#op_true) if the current bar is the first bar of the day's session, `false` otherwise. If extended session information is used, only returns [true](#op_true) on the first bar of the pre-market bars.

### Type

` series bool `

## session.isfirstbar_regular

Returns [true](#op_true) on the first regular session bar of the day, `false` otherwise. The result is the same whether extended session information is used or not.

### Type

` series bool `

## session.islastbar

Returns [true](#op_true) if the current bar is the last bar of the day's session, `false` otherwise. If extended session information is used, only returns [true](#op_true) on the last bar of the post-market bars.

### Type

` series bool `

### Remarks

This variable is not guaranteed to return [true](#op_true) once in every session because the last bar of the session might not exist if no trades occur during what should be the session's last bar.

This variable is not guaranteed to work as expected on non-standard chart types, e.g., Renko.

## session.islastbar_regular

Returns [true](#op_true) on the last regular session bar of the day, `false` otherwise. The result is the same whether extended session information is used or not.

### Type

` series bool `

### Remarks

This variable is not guaranteed to return [true](#op_true) once in every session because the last bar of the session might not exist if no trades occur during what should be the session's last bar.

This variable is not guaranteed to work as expected on non-standard chart types, e.g., Renko.

## session.ismarket

Returns true if the current bar is a part of the regular trading hours (i.e. market hours), false otherwise

### Type

` series bool `

### See also

[session.ispremarket](#var_session.ispremarket)[session.ispostmarket](#var_session.ispostmarket)

## session.ispostmarket

Returns true if the current bar is a part of the post-market, false otherwise. On non-intraday charts always returns false.

### Type

` series bool `

### See also

[session.ismarket](#var_session.ismarket)[session.ispremarket](#var_session.ispremarket)

## session.ispremarket

Returns true if the current bar is a part of the pre-market, false otherwise. On non-intraday charts always returns false.

### Type

` series bool `

### See also

[session.ismarket](#var_session.ismarket)[session.ispostmarket](#var_session.ispostmarket)

## strategy.account_currency

Returns the currency used to calculate results, which can be set in the strategy's properties.

### Type

` simple string `

### See also

[strategy](#fun_strategy)[strategy.convert_to_account](#fun_strategy.convert_to_account)[strategy.convert_to_symbol](#fun_strategy.convert_to_symbol)

## strategy.closedtrades

Number of trades, which were closed for the whole trading interval.

### Type

` series int `

### See also

[strategy.position_size](#var_strategy.position_size)[strategy.opentrades](#var_strategy.opentrades)[strategy.wintrades](#var_strategy.wintrades)[strategy.losstrades](#var_strategy.losstrades)[strategy.eventrades](#var_strategy.eventrades)

## strategy.equity

Current equity ([strategy.initial_capital](#var_strategy.initial_capital) + [strategy.netprofit](#var_strategy.netprofit) + [strategy.openprofit](#var_strategy.openprofit)).

### Type

` series float `

### See also

[strategy.netprofit](#var_strategy.netprofit)[strategy.openprofit](#var_strategy.openprofit)[strategy.position_size](#var_strategy.position_size)

## strategy.eventrades

Number of breakeven trades for the whole trading interval.

### Type

` series int `

### See also

[strategy.position_size](#var_strategy.position_size)[strategy.opentrades](#var_strategy.opentrades)[strategy.closedtrades](#var_strategy.closedtrades)[strategy.wintrades](#var_strategy.wintrades)[strategy.losstrades](#var_strategy.losstrades)

## strategy.grossloss

Total currency value of all completed losing trades.

### Type

` series float `

### See also

[strategy.netprofit](#var_strategy.netprofit)[strategy.grossprofit](#var_strategy.grossprofit)

## strategy.grossprofit

Total currency value of all completed winning trades.

### Type

` series float `

### See also

[strategy.netprofit](#var_strategy.netprofit)[strategy.grossloss](#var_strategy.grossloss)

## strategy.initial_capital

The amount of initial capital set in the strategy properties.

### Type

` series float `

### See also

[strategy](#fun_strategy)

## strategy.long

Long position entry.

### Type

` const strategy_direction `

### See also

[strategy.entry](#fun_strategy.entry)[strategy.exit](#fun_strategy.exit)[strategy.order](#fun_strategy.order)

## strategy.losstrades

Number of unprofitable trades for the whole trading interval.

### Type

` series int `

### See also

[strategy.position_size](#var_strategy.position_size)[strategy.opentrades](#var_strategy.opentrades)[strategy.closedtrades](#var_strategy.closedtrades)[strategy.wintrades](#var_strategy.wintrades)[strategy.eventrades](#var_strategy.eventrades)

## strategy.margin_liquidation_price

When margin is used in a strategy, returns the price point where a simulated margin call will occur and liquidate enough of the position to meet the margin requirements.

### Type

` series float `

### Example

```
//@version=5strategy("Margin call management", overlay = true, margin_long = 25, margin_short = 25,   default_qty_type = strategy.percent_of_equity, default_qty_value = 395)float maFast = ta.sma(close, 14)float maSlow = ta.sma(close, 28)if ta.crossover(maFast, maSlow)    strategy.entry("Long", strategy.long)if ta.crossunder(maFast, maSlow)    strategy.entry("Short", strategy.short)changePercent(v1, v2) =>     float result = (v1 - v2) * 100 / math.abs(v2)// exit when we're 10% away from a margin call, to prevent it.if math.abs(changePercent(close, strategy.margin_liquidation_price)) <= 10    strategy.close("Long")    strategy.close("Short")
```

### Remarks

The variable returns [na](#var_na) if the strategy does not use margin, i.e., the [strategy](#fun_strategy) declaration statement does not specify an argument for the `margin_long` or `margin_short` parameter.

## strategy.max_contracts_held_all

Maximum number of contracts/shares/lots/units in one trade for the whole trading interval.

### Type

` series float `

### See also

[strategy.position_size](#var_strategy.position_size)[strategy.max_contracts_held_long](#var_strategy.max_contracts_held_long)[strategy.max_contracts_held_short](#var_strategy.max_contracts_held_short)

## strategy.max_contracts_held_long

Maximum number of contracts/shares/lots/units in one long trade for the whole trading interval.

### Type

` series float `

### See also

[strategy.position_size](#var_strategy.position_size)[strategy.max_contracts_held_all](#var_strategy.max_contracts_held_all)[strategy.max_contracts_held_short](#var_strategy.max_contracts_held_short)

## strategy.max_contracts_held_short

Maximum number of contracts/shares/lots/units in one short trade for the whole trading interval.

### Type

` series float `

### See also

[strategy.position_size](#var_strategy.position_size)[strategy.max_contracts_held_all](#var_strategy.max_contracts_held_all)[strategy.max_contracts_held_long](#var_strategy.max_contracts_held_long)

## strategy.max_drawdown

Maximum equity drawdown value for the whole trading interval.

### Type

` series float `

### See also

[strategy.netprofit](#var_strategy.netprofit)[strategy.equity](#var_strategy.equity)[strategy.max_runup](#var_strategy.max_runup)

## strategy.max_runup

Maximum equity run-up value for the whole trading interval.

### Type

` series float `

### See also

[strategy.netprofit](#var_strategy.netprofit)[strategy.equity](#var_strategy.equity)[strategy.max_drawdown](#var_strategy.max_drawdown)

## strategy.netprofit

Total currency value of all completed trades.

### Type

` series float `

### See also

[strategy.openprofit](#var_strategy.openprofit)[strategy.position_size](#var_strategy.position_size)[strategy.grossprofit](#var_strategy.grossprofit)[strategy.grossloss](#var_strategy.grossloss)

## strategy.openprofit

Current unrealized profit or loss for all open positions.

### Type

` series float `

### See also

[strategy.netprofit](#var_strategy.netprofit)[strategy.position_size](#var_strategy.position_size)

## strategy.opentrades

Number of market position entries, which were not closed and remain opened. If there is no open market position, 0 is returned.

### Type

` series int `

### See also

[strategy.position_size](#var_strategy.position_size)

## strategy.position_avg_price

Average entry price of current market position. If the market position is flat, 'NaN' is returned.

### Type

` series float `

### See also

[strategy.position_size](#var_strategy.position_size)

## strategy.position_entry_name

Name of the order that initially opened current market position.

### Type

` series string `

### See also

[strategy.position_size](#var_strategy.position_size)

## strategy.position_size

Direction and size of the current market position. If the value is > 0, the market position is long. If the value is < 0, the market position is short. The absolute value is the number of contracts/shares/lots/units in trade (position size).

### Type

` series float `

### See also

[strategy.position_avg_price](#var_strategy.position_avg_price)

## strategy.short

Short position entry.

### Type

` const strategy_direction `

### See also

[strategy.entry](#fun_strategy.entry)[strategy.exit](#fun_strategy.exit)[strategy.order](#fun_strategy.order)

## strategy.wintrades

Number of profitable trades for the whole trading interval.

### Type

` series int `

### See also

[strategy.position_size](#var_strategy.position_size)[strategy.opentrades](#var_strategy.opentrades)[strategy.closedtrades](#var_strategy.closedtrades)[strategy.losstrades](#var_strategy.losstrades)[strategy.eventrades](#var_strategy.eventrades)

## syminfo.basecurrency

Base currency for the symbol. For the symbol 'BTCUSD' returns 'BTC'.

### Type

` simple string `

### See also

[syminfo.currency](#var_syminfo.currency)[syminfo.ticker](#var_syminfo.ticker)

## syminfo.country

Returns the two-letter code of the country where the symbol is traded, in the [ISO 3166-1 alpha-2](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) format, or [na](#var_na) if the exchange is not directly tied to a specific country. For example, on "NASDAQ:AAPL" it will return "US", on "LSE:AAPL" it will return "GB", and on "BITSTAMP:BTCUSD it will return [na](#var_na).

### Type

` simple string `

## syminfo.currency

Currency for the current symbol. Returns currency code: 'USD', 'EUR', etc.

### Type

` simple string `

### See also

[syminfo.basecurrency](#var_syminfo.basecurrency)[syminfo.ticker](#var_syminfo.ticker)[currency.USD](#var_currency.USD)[currency.EUR](#var_currency.EUR)

## syminfo.description

Description for the current symbol.

### Type

` simple string `

### See also

[syminfo.ticker](#var_syminfo.ticker)[syminfo.prefix](#var_syminfo.prefix)

## syminfo.industry

Returns the industry of the symbol, or [na](#var_na) if the symbol has no industry. Example: "Internet Software/Services", "Packaged software", "Integrated Oil", "Motor Vehicles", etc. These are the same values one can see in the chart's "Symbol info" window.

### Type

` simple string `

### Remarks

A sector is a broad section of the economy. An industry is a narrower classification. NASDAQ:CAT (Caterpillar, Inc.) for example, belongs to the "Producer Manufacturing" sector and the "Trucks/Construction/Farm Machinery" industry.

## syminfo.minmove

Returns a whole number used to calculate the smallest increment between a symbol's price movements ([syminfo.mintick](#var_syminfo.mintick)). It is the numerator in the [syminfo.mintick](#var_syminfo.mintick) formula: `[syminfo.minmove](#var_syminfo.minmove) / [syminfo.pricescale](#var_syminfo.pricescale) = [syminfo.mintick](#var_syminfo.mintick)`.

### Type

` simple int `

### See also

[ticker.new](#fun_ticker.new)[syminfo.ticker](#var_syminfo.ticker)[timeframe.period](#var_timeframe.period)[timeframe.multiplier](#var_timeframe.multiplier)[syminfo.root](#var_syminfo.root)

## syminfo.mintick

Min tick value for the current symbol.

### Type

` simple float `

### See also

[syminfo.pointvalue](#var_syminfo.pointvalue)

## syminfo.pointvalue

Point value for the current symbol.

### Type

` simple float `

### See also

[syminfo.mintick](#var_syminfo.mintick)

## syminfo.prefix

Prefix of current symbol name (i.e. for 'CME_EOD:TICKER' prefix is 'CME_EOD').

### Type

` simple string `

### Example

```
//@version=5indicator("syminfo.prefix")// If current chart symbol is 'BATS:MSFT' then syminfo.prefix is 'BATS'.if barstate.islastconfirmedhistory    label.new(bar_index, high, text=syminfo.prefix)
```

### See also

[syminfo.ticker](#var_syminfo.ticker)[syminfo.tickerid](#var_syminfo.tickerid)

## syminfo.pricescale

Returns a whole number used to calculate the smallest increment between a symbol's price movements ([syminfo.mintick](#var_syminfo.mintick)). It is the denominator in the [syminfo.mintick](#var_syminfo.mintick) formula: `[syminfo.minmove](#var_syminfo.minmove) / [syminfo.pricescale](#var_syminfo.pricescale) = [syminfo.mintick](#var_syminfo.mintick)`.

### Type

` simple int `

### See also

[ticker.new](#fun_ticker.new)[syminfo.ticker](#var_syminfo.ticker)[timeframe.period](#var_timeframe.period)[timeframe.multiplier](#var_timeframe.multiplier)[syminfo.root](#var_syminfo.root)

## syminfo.root

Root for derivatives like futures contract. For other symbols returns the same value as [syminfo.ticker](#var_syminfo.ticker).

### Type

` simple string `

### Example

```
//@version=5indicator("syminfo.root")// If the current chart symbol is continuous futures ('ES1!'), it would display 'ES'.if barstate.islastconfirmedhistory    label.new(bar_index, high, syminfo.root)
```

### See also

[syminfo.ticker](#var_syminfo.ticker)[syminfo.tickerid](#var_syminfo.tickerid)

## syminfo.sector

Returns the sector of the symbol, or [na](#var_na) if the symbol has no sector. Example: "Electronic Technology", "Technology services", "Energy Minerals", "Consumer Durables", etc. These are the same values one can see in the chart's "Symbol info" window.

### Type

` simple string `

### Remarks

A sector is a broad section of the economy. An industry is a narrower classification. NASDAQ:CAT (Caterpillar, Inc.) for example, belongs to the "Producer Manufacturing" sector and the "Trucks/Construction/Farm Machinery" industry.

## syminfo.session

Session type of the chart main series. Possible values are [session.regular](#var_session.regular), [session.extended](#var_session.extended).

### Type

` simple string `

### See also

[session.regular](#var_session.regular)[session.extended](#var_session.extended)

## syminfo.ticker

Symbol name without exchange prefix, e.g. 'MSFT'.

### Type

` simple string `

### See also

[syminfo.tickerid](#var_syminfo.tickerid)[timeframe.period](#var_timeframe.period)[timeframe.multiplier](#var_timeframe.multiplier)[syminfo.root](#var_syminfo.root)

## syminfo.tickerid

Returns the full form of the ticker ID representing a symbol, for use as an argument in functions with a `ticker` or `symbol` parameter. It always includes the prefix (exchange) and ticker separated by a colon ("NASDAQ:AAPL"), but it can also include other symbol data such as dividend adjustment, chart type, currency conversion, etc.

### Type

` simple string `

### Remarks

Because the value of this variable does not always use a simple "prefix:ticker" format, it is a poor candidate for use in boolean comparisons or string manipulation functions. In those contexts, run the variable's result through [ticker.standard](#fun_ticker.standard) to purify it. This will remove any extraneous information and return a ticker ID consistently formatted using the "prefix:ticker" structure.

### See also

[ticker.new](#fun_ticker.new)[syminfo.ticker](#var_syminfo.ticker)[timeframe.period](#var_timeframe.period)[timeframe.multiplier](#var_timeframe.multiplier)[syminfo.root](#var_syminfo.root)

## syminfo.timezone

Timezone of the exchange of the chart main series. Possible values see in [timestamp](#fun_timestamp).

### Type

` simple string `

### See also

[timestamp](#fun_timestamp)

## syminfo.type

Type of the current symbol. Possible values are stock, futures, index, forex, crypto, fund, dr.

### Type

` simple string `

### See also

[syminfo.ticker](#var_syminfo.ticker)

## syminfo.volumetype

Volume type of the current symbol. Possible values are: "base" for base currency, "quote" for quote currency, "tick" for the number of transactions, and "n/a" when there is no volume or its type is not specified.

### Type

` simple string `

### Remarks

Only some data feed suppliers provide information qualifying volume. As a result, the variable will return a value on some symbols only, mostly in the crypto sector.

### See also

[syminfo.type](#var_syminfo.type)

## ta.accdist

Accumulation/distribution index.

### Type

` series float `

## ta.iii

Intraday Intensity Index.

### Type

` series float `

### Example

```
//@version=5indicator("Intraday Intensity Index")plot(ta.iii, color=color.yellow)// the same on pinef_iii() =>    (2 * close - high - low) / ((high - low) * volume)plot(f_iii())
```

## ta.nvi

Negative Volume Index.

### Type

` series float `

### Example

```
//@version=5indicator("Negative Volume Index")plot(ta.nvi, color=color.yellow)// the same on pinef_nvi() =>    float ta_nvi = 1.0    float prevNvi = (nz(ta_nvi[1], 0.0) == 0.0)  ? 1.0: ta_nvi[1]    if nz(close, 0.0) == 0.0 or nz(close[1], 0.0) == 0.0        ta_nvi := prevNvi    else        ta_nvi := (volume < nz(volume[1], 0.0)) ? prevNvi + ((close - close[1]) / close[1]) * prevNvi : prevNvi    result = ta_nviplot(f_nvi())
```

## ta.obv

On Balance Volume.

### Type

` series float `

### Example

```
//@version=5indicator("On Balance Volume")plot(ta.obv, color=color.yellow)// the same on pinef_obv() =>    ta.cum(math.sign(ta.change(close)) * volume)plot(f_obv())
```

## ta.pvi

Positive Volume Index.

### Type

` series float `

### Example

```
//@version=5indicator("Positive Volume Index")plot(ta.pvi, color=color.yellow)// the same on pinef_pvi() =>    float ta_pvi = 1.0    float prevPvi = (nz(ta_pvi[1], 0.0) == 0.0)  ? 1.0: ta_pvi[1]    if nz(close, 0.0) == 0.0 or nz(close[1], 0.0) == 0.0        ta_pvi := prevPvi    else        ta_pvi := (volume > nz(volume[1], 0.0)) ? prevPvi + ((close - close[1]) / close[1]) * prevPvi : prevPvi    result = ta_pviplot(f_pvi())
```

## ta.pvt

Price-Volume Trend.

### Type

` series float `

### Example

```
//@version=5indicator("Price-Volume Trend")plot(ta.pvt, color=color.yellow)// the same on pinef_pvt() =>    ta.cum((ta.change(close) / close[1]) * volume)plot(f_pvt())
```

## ta.tr

True range. Same as tr(false). It is max(high - low, abs(high - close[1]), abs(low - close[1]))

### Type

` series float `

### See also

[ta.tr](#fun_ta.tr)[ta.atr](#fun_ta.atr)

## ta.vwap

Volume Weighted Average Price. It uses [hlc3](#var_hlc3) as its source series.

### Type

` series float `

### See also

[ta.vwap](#fun_ta.vwap)

## ta.wad

Williams Accumulation/Distribution.

### Type

` series float `

### Example

```
//@version=5indicator("Williams Accumulation/Distribution")plot(ta.wad, color=color.yellow)// the same on pinef_wad() =>    trueHigh = math.max(high, close[1])    trueLow = math.min(low, close[1])    mom = ta.change(close)    gain = (mom > 0) ? close - trueLow : (mom < 0) ? close - trueHigh : 0    ta.cum(gain)plot(f_wad())
```

## ta.wvad

Williams Variable Accumulation/Distribution.

### Type

` series float `

### Example

```
//@version=5indicator("Williams Variable Accumulation/Distribution")plot(ta.wvad, color=color.yellow)// the same on pinef_wvad() =>    (close - open) / (high - low) * volumeplot(f_wvad())
```

## table.all

Returns an array filled with all the current tables drawn by the script.

### Type

` table[] `

### Example

```
//@version=5indicator("table.all")//delete all tablestable.new(position = position.top_right, columns = 2, rows = 1, bgcolor = color.yellow, border_width = 1)a_allTables = table.allif array.size(a_allTables) > 0    for i = 0 to array.size(a_allTables) - 1        table.delete(array.get(a_allTables, i))
```

### Remarks

The array is read-only. Index zero of the array is the ID of the oldest object on the chart.

### See also

[table.new](#fun_table.new)[line.all](#var_line.all)[label.all](#var_label.all)[box.all](#var_box.all)

## time

Current bar time in UNIX format. It is the number of milliseconds that have elapsed since 00:00:00 UTC, 1 January 1970.

### Type

` series int `

### Remarks

Note that this variable returns the timestamp based on the time of the bar's open. Because of that, for overnight sessions (e.g. EURUSD, where Monday session starts on Sunday, 17:00) this variable can return time before the specified date of the trading day. For example, on EURUSD, `dayofmonth(time)` can be lower by 1 than the date of the trading day, because the bar for the current day actually opens one day prior.

### See also

[time](#fun_time)[time_close](#var_time_close)[timenow](#var_timenow)[year](#var_year)[month](#var_month)[weekofyear](#var_weekofyear)[dayofmonth](#var_dayofmonth)[dayofweek](#var_dayofweek)[hour](#var_hour)[minute](#var_minute)[second](#var_second)

## time_close

The time of the current bar's close in UNIX format. It represents the number of milliseconds elapsed since 00:00:00 UTC, 1 January 1970\. On non-standard price-based chart types (Renko, Line break, Kagi, Point & Figure, and Range), this variable returns [na](#var_na) on the chart's realtime bars.

### Type

` series int `

### See also

[time](#var_time)[timenow](#var_timenow)[year](#var_year)[month](#var_month)[weekofyear](#var_weekofyear)[dayofmonth](#var_dayofmonth)[dayofweek](#var_dayofweek)[hour](#var_hour)[minute](#var_minute)[second](#var_second)

## time_tradingday

The beginning time of the trading day the current bar belongs to, in UNIX format (the number of milliseconds that have elapsed since 00:00:00 UTC, 1 January 1970).

### Type

` series int `

### Remarks

The variable is useful for overnight sessions, where the current day's session can start on the previous calendar day (e.g., on EURUSD the Monday session will start on Sunday, 17:00). Unlike `time`, which would return the timestamp for Sunday at 17:00 for the Monday daily bar, `time_tradingday` will return the timestamp for Monday, 00:00.

When used on timeframes higher than 1D, `time_tradingday` returns the trading day of the last day inside the bar (e.g. on 1W, it will return the last trading day of the week).

### See also

[time](#var_time)[time_close](#var_time_close)

## timeframe.isdaily

Returns true if current resolution is a daily resolution, false otherwise.

### Type

` simple bool `

### See also

[timeframe.isdwm](#var_timeframe.isdwm)[timeframe.isintraday](#var_timeframe.isintraday)[timeframe.isminutes](#var_timeframe.isminutes)[timeframe.isseconds](#var_timeframe.isseconds)[timeframe.isweekly](#var_timeframe.isweekly)[timeframe.ismonthly](#var_timeframe.ismonthly)

## timeframe.isdwm

Returns true if current resolution is a daily or weekly or monthly resolution, false otherwise.

### Type

` simple bool `

### See also

[timeframe.isintraday](#var_timeframe.isintraday)[timeframe.isminutes](#var_timeframe.isminutes)[timeframe.isseconds](#var_timeframe.isseconds)[timeframe.isdaily](#var_timeframe.isdaily)[timeframe.isweekly](#var_timeframe.isweekly)[timeframe.ismonthly](#var_timeframe.ismonthly)

## timeframe.isintraday

Returns true if current resolution is an intraday (minutes or seconds) resolution, false otherwise.

### Type

` simple bool `

### See also

[timeframe.isminutes](#var_timeframe.isminutes)[timeframe.isseconds](#var_timeframe.isseconds)[timeframe.isdwm](#var_timeframe.isdwm)[timeframe.isdaily](#var_timeframe.isdaily)[timeframe.isweekly](#var_timeframe.isweekly)[timeframe.ismonthly](#var_timeframe.ismonthly)

## timeframe.isminutes

Returns true if current resolution is a minutes resolution, false otherwise.

### Type

` simple bool `

### See also

[timeframe.isdwm](#var_timeframe.isdwm)[timeframe.isintraday](#var_timeframe.isintraday)[timeframe.isseconds](#var_timeframe.isseconds)[timeframe.isdaily](#var_timeframe.isdaily)[timeframe.isweekly](#var_timeframe.isweekly)[timeframe.ismonthly](#var_timeframe.ismonthly)

## timeframe.ismonthly

Returns true if current resolution is a monthly resolution, false otherwise.

### Type

` simple bool `

### See also

[timeframe.isdwm](#var_timeframe.isdwm)[timeframe.isintraday](#var_timeframe.isintraday)[timeframe.isminutes](#var_timeframe.isminutes)[timeframe.isseconds](#var_timeframe.isseconds)[timeframe.isdaily](#var_timeframe.isdaily)[timeframe.isweekly](#var_timeframe.isweekly)

## timeframe.isseconds

Returns true if current resolution is a seconds resolution, false otherwise.

### Type

` simple bool `

### See also

[timeframe.isdwm](#var_timeframe.isdwm)[timeframe.isintraday](#var_timeframe.isintraday)[timeframe.isminutes](#var_timeframe.isminutes)[timeframe.isdaily](#var_timeframe.isdaily)[timeframe.isweekly](#var_timeframe.isweekly)[timeframe.ismonthly](#var_timeframe.ismonthly)

## timeframe.isweekly

Returns true if current resolution is a weekly resolution, false otherwise.

### Type

` simple bool `

### See also

[timeframe.isdwm](#var_timeframe.isdwm)[timeframe.isintraday](#var_timeframe.isintraday)[timeframe.isminutes](#var_timeframe.isminutes)[timeframe.isseconds](#var_timeframe.isseconds)[timeframe.isdaily](#var_timeframe.isdaily)[timeframe.ismonthly](#var_timeframe.ismonthly)

## timeframe.multiplier

Multiplier of resolution, e.g. '60' - 60, 'D' - 1, '5D' - 5, '12M' - 12.

### Type

` simple int `

### See also

[syminfo.ticker](#var_syminfo.ticker)[syminfo.tickerid](#var_syminfo.tickerid)[timeframe.period](#var_timeframe.period)

## timeframe.period

A string representation of the chart's timeframe. The returned string's format is "[

<quantity>][<units>]", where <quantity> and <units> are in some cases absent. <quantity> is the number of units, but it is absent if that number is 1\. <unit> is "S" for seconds, "D" for days, "W" for weeks, "M" for months, but it is absent for minutes. No <unit> exists for hours.</unit></unit></quantity></units></quantity></units></quantity>

The variable will return: "10S" for 10 seconds, "60" for 60 minutes, "D" for one day, "2W" for two weeks, "3M" for one quarter.

Can be used as an argument with any function containing a `timeframe` parameter.

### Type

` simple string `

### See also

[syminfo.ticker](#var_syminfo.ticker)[syminfo.tickerid](#var_syminfo.tickerid)[timeframe.multiplier](#var_timeframe.multiplier)

## timenow

Current time in UNIX format. It is the number of milliseconds that have elapsed since 00:00:00 UTC, 1 January 1970.

### Type

` series int `

### Remarks

Please note that using this variable/function can cause [indicator repainting](https://www.tradingview.com/pine-script-docs/en/v5/concepts/Repainting.html).

### See also

[timestamp](#fun_timestamp)[time](#var_time)[time_close](#var_time_close)[year](#var_year)[month](#var_month)[weekofyear](#var_weekofyear)[dayofmonth](#var_dayofmonth)[dayofweek](#var_dayofweek)[hour](#var_hour)[minute](#var_minute)[second](#var_second)

## volume

Current bar volume.

### Type

` series float `

### Remarks

Previous values may be accessed with square brackets operator [], e.g. volume[1], volume[2].

### See also

[open](#var_open)[high](#var_high)[low](#var_low)[close](#var_close)[time](#fun_time)[hl2](#var_hl2)[hlc3](#var_hlc3)[hlcc4](#var_hlcc4)[ohlc4](#var_ohlc4)

## weekofyear

Week number of current bar time in exchange timezone.

### Type

` series int `

### Remarks

Note that this variable returns the week based on the time of the bar's open. For overnight sessions (e.g. EURUSD, where Monday session starts on Sunday, 17:00) this value can be lower by 1 than the week of the trading day.

### See also

[weekofyear](#fun_weekofyear)[time](#var_time)[year](#var_year)[month](#var_month)[dayofmonth](#var_dayofmonth)[dayofweek](#var_dayofweek)[hour](#var_hour)[minute](#var_minute)[second](#var_second)

## year

Current bar year in exchange timezone.

### Type

` series int `

### Remarks

Note that this variable returns the year based on the time of the bar's open. For overnight sessions (e.g. EURUSD, where Monday session starts on Sunday, 17:00) this value can be lower by 1 than the year of the trading day.

### See also

[year](#fun_year)[time](#var_time)[month](#var_month)[weekofyear](#var_weekofyear)[dayofmonth](#var_dayofmonth)[dayofweek](#var_dayofweek)[hour](#var_hour)[minute](#var_minute)[second](#var_second)

## adjustment.dividends

Constant for dividends adjustment type (dividends adjustment is applied).

### Type

` const string `

### See also

[adjustment.none](#var_adjustment.none)[adjustment.splits](#var_adjustment.splits)[ticker.new](#fun_ticker.new)

## adjustment.none

Constant for none adjustment type (no adjustment is applied).

### Type

` const string `

### See also

[adjustment.splits](#var_adjustment.splits)[adjustment.dividends](#var_adjustment.dividends)[ticker.new](#fun_ticker.new)

## adjustment.splits

Constant for splits adjustment type (splits adjustment is applied).

### Type

` const string `

### See also

[adjustment.none](#var_adjustment.none)[adjustment.dividends](#var_adjustment.dividends)[ticker.new](#fun_ticker.new)

## alert.freq_all

A named constant for use with the `freq` parameter of the alert() function.

All function calls trigger the alert.

### Type

` const string `

### See also

[alert](#fun_alert)

## alert.freq_once_per_bar

A named constant for use with the `freq` parameter of the alert() function.

The first function call during the bar triggers the alert.

### Type

` const string `

### See also

[alert](#fun_alert)

## alert.freq_once_per_bar_close

A named constant for use with the `freq` parameter of the alert() function.

The function call triggers the alert only when it occurs during the last script iteration of the real-time bar, when it closes.

### Type

` const string `

### See also

[alert](#fun_alert)

## barmerge.gaps_off

Merge strategy for requested data. Data is merged continuously without gaps, all the gaps are filled with the previous nearest existing value.

### Type

` const barmerge_gaps `

### See also

[request.security](#fun_request.security)[barmerge.gaps_on](#var_barmerge.gaps_on)

## barmerge.gaps_on

Merge strategy for requested data. Data is merged with possible gaps ([na](#var_na) values).

### Type

` const barmerge_gaps `

### See also

[request.security](#fun_request.security)[barmerge.gaps_off](#var_barmerge.gaps_off)

## barmerge.lookahead_off

Merge strategy for the requested data position. Requested barset is merged with current barset in the order of sorting bars by their close time. This merge strategy disables effect of getting data from "future" on calculation on history.

### Type

` const barmerge_lookahead `

### See also

[request.security](#fun_request.security)[barmerge.lookahead_on](#var_barmerge.lookahead_on)

## barmerge.lookahead_on

Merge strategy for the requested data position. Requested barset is merged with current barset in the order of sorting bars by their opening time. This merge strategy can lead to undesirable effect of getting data from "future" on calculation on history. This is unacceptable in backtesting strategies, but can be useful in indicators.

### Type

` const barmerge_lookahead `

### See also

[request.security](#fun_request.security)[barmerge.lookahead_off](#var_barmerge.lookahead_off)

## color.aqua

Is a named constant for #00BCD4 color.

### Type

` const color `

### See also

[color.black](#var_color.black)[color.silver](#var_color.silver)[color.gray](#var_color.gray)[color.white](#var_color.white)[color.maroon](#var_color.maroon)[color.red](#var_color.red)[color.purple](#var_color.purple)[color.fuchsia](#var_color.fuchsia)[color.green](#var_color.green)[color.lime](#var_color.lime)[color.olive](#var_color.olive)[color.yellow](#var_color.yellow)[color.navy](#var_color.navy)[color.blue](#var_color.blue)[color.teal](#var_color.teal)[color.orange](#var_color.orange)

## color.black

Is a named constant for #363A45 color.

### Type

` const color `

### See also

[color.silver](#var_color.silver)[color.gray](#var_color.gray)[color.white](#var_color.white)[color.maroon](#var_color.maroon)[color.red](#var_color.red)[color.purple](#var_color.purple)[color.fuchsia](#var_color.fuchsia)[color.green](#var_color.green)[color.lime](#var_color.lime)[color.olive](#var_color.olive)[color.yellow](#var_color.yellow)[color.navy](#var_color.navy)[color.blue](#var_color.blue)[color.teal](#var_color.teal)[color.aqua](#var_color.aqua)[color.orange](#var_color.orange)

## color.blue

Is a named constant for #2962ff color.

### Type

` const color `

### See also

[color.black](#var_color.black)[color.silver](#var_color.silver)[color.gray](#var_color.gray)[color.white](#var_color.white)[color.maroon](#var_color.maroon)[color.red](#var_color.red)[color.purple](#var_color.purple)[color.fuchsia](#var_color.fuchsia)[color.green](#var_color.green)[color.lime](#var_color.lime)[color.olive](#var_color.olive)[color.yellow](#var_color.yellow)[color.navy](#var_color.navy)[color.teal](#var_color.teal)[color.aqua](#var_color.aqua)[color.orange](#var_color.orange)

## color.fuchsia

Is a named constant for #E040FB color.

### Type

` const color `

### See also

[color.black](#var_color.black)[color.silver](#var_color.silver)[color.gray](#var_color.gray)[color.white](#var_color.white)[color.maroon](#var_color.maroon)[color.red](#var_color.red)[color.purple](#var_color.purple)[color.green](#var_color.green)[color.lime](#var_color.lime)[color.olive](#var_color.olive)[color.yellow](#var_color.yellow)[color.navy](#var_color.navy)[color.blue](#var_color.blue)[color.teal](#var_color.teal)[color.aqua](#var_color.aqua)[color.orange](#var_color.orange)

## color.gray

Is a named constant for #787B86 color.

### Type

` const color `

### See also

[color.black](#var_color.black)[color.silver](#var_color.silver)[color.white](#var_color.white)[color.maroon](#var_color.maroon)[color.red](#var_color.red)[color.purple](#var_color.purple)[color.fuchsia](#var_color.fuchsia)[color.green](#var_color.green)[color.lime](#var_color.lime)[color.olive](#var_color.olive)[color.yellow](#var_color.yellow)[color.navy](#var_color.navy)[color.blue](#var_color.blue)[color.teal](#var_color.teal)[color.aqua](#var_color.aqua)[color.orange](#var_color.orange)

## color.green

Is a named constant for #4CAF50 color.

### Type

` const color `

### See also

[color.black](#var_color.black)[color.silver](#var_color.silver)[color.gray](#var_color.gray)[color.white](#var_color.white)[color.maroon](#var_color.maroon)[color.red](#var_color.red)[color.purple](#var_color.purple)[color.fuchsia](#var_color.fuchsia)[color.lime](#var_color.lime)[color.olive](#var_color.olive)[color.yellow](#var_color.yellow)[color.navy](#var_color.navy)[color.blue](#var_color.blue)[color.teal](#var_color.teal)[color.aqua](#var_color.aqua)[color.orange](#var_color.orange)

## color.lime

Is a named constant for #00E676 color.

### Type

` const color `

### See also

[color.black](#var_color.black)[color.silver](#var_color.silver)[color.gray](#var_color.gray)[color.white](#var_color.white)[color.maroon](#var_color.maroon)[color.red](#var_color.red)[color.purple](#var_color.purple)[color.fuchsia](#var_color.fuchsia)[color.green](#var_color.green)[color.olive](#var_color.olive)[color.yellow](#var_color.yellow)[color.navy](#var_color.navy)[color.blue](#var_color.blue)[color.teal](#var_color.teal)[color.aqua](#var_color.aqua)[color.orange](#var_color.orange)

## color.maroon

Is a named constant for #880E4F color.

### Type

` const color `

### See also

[color.black](#var_color.black)[color.silver](#var_color.silver)[color.gray](#var_color.gray)[color.white](#var_color.white)[color.red](#var_color.red)[color.purple](#var_color.purple)[color.fuchsia](#var_color.fuchsia)[color.green](#var_color.green)[color.lime](#var_color.lime)[color.olive](#var_color.olive)[color.yellow](#var_color.yellow)[color.navy](#var_color.navy)[color.blue](#var_color.blue)[color.teal](#var_color.teal)[color.aqua](#var_color.aqua)[color.orange](#var_color.orange)

## color.navy

Is a named constant for #311B92 color.

### Type

` const color `

### See also

[color.black](#var_color.black)[color.silver](#var_color.silver)[color.gray](#var_color.gray)[color.white](#var_color.white)[color.maroon](#var_color.maroon)[color.red](#var_color.red)[color.purple](#var_color.purple)[color.fuchsia](#var_color.fuchsia)[color.green](#var_color.green)[color.lime](#var_color.lime)[color.olive](#var_color.olive)[color.yellow](#var_color.yellow)[color.blue](#var_color.blue)[color.teal](#var_color.teal)[color.aqua](#var_color.aqua)[color.orange](#var_color.orange)

## color.olive

Is a named constant for #808000 color.

### Type

` const color `

### See also

[color.black](#var_color.black)[color.silver](#var_color.silver)[color.gray](#var_color.gray)[color.white](#var_color.white)[color.maroon](#var_color.maroon)[color.red](#var_color.red)[color.purple](#var_color.purple)[color.fuchsia](#var_color.fuchsia)[color.green](#var_color.green)[color.lime](#var_color.lime)[color.yellow](#var_color.yellow)[color.navy](#var_color.navy)[color.blue](#var_color.blue)[color.teal](#var_color.teal)[color.aqua](#var_color.aqua)[color.orange](#var_color.orange)

## color.orange

Is a named constant for #FF9800 color.

### Type

` const color `

### See also

[color.black](#var_color.black)[color.silver](#var_color.silver)[color.gray](#var_color.gray)[color.white](#var_color.white)[color.maroon](#var_color.maroon)[color.red](#var_color.red)[color.purple](#var_color.purple)[color.fuchsia](#var_color.fuchsia)[color.green](#var_color.green)[color.lime](#var_color.lime)[color.olive](#var_color.olive)[color.yellow](#var_color.yellow)[color.navy](#var_color.navy)[color.blue](#var_color.blue)[color.teal](#var_color.teal)[color.aqua](#var_color.aqua)

## color.purple

Is a named constant for #9C27B0 color.

### Type

` const color `

### See also

[color.black](#var_color.black)[color.silver](#var_color.silver)[color.gray](#var_color.gray)[color.white](#var_color.white)[color.maroon](#var_color.maroon)[color.red](#var_color.red)[color.fuchsia](#var_color.fuchsia)[color.green](#var_color.green)[color.lime](#var_color.lime)[color.olive](#var_color.olive)[color.yellow](#var_color.yellow)[color.navy](#var_color.navy)[color.blue](#var_color.blue)[color.teal](#var_color.teal)[color.aqua](#var_color.aqua)[color.orange](#var_color.orange)

## color.red

Is a named constant for #FF5252 color.

### Type

` const color `

### See also

[color.black](#var_color.black)[color.silver](#var_color.silver)[color.gray](#var_color.gray)[color.white](#var_color.white)[color.maroon](#var_color.maroon)[color.purple](#var_color.purple)[color.fuchsia](#var_color.fuchsia)[color.green](#var_color.green)[color.lime](#var_color.lime)[color.olive](#var_color.olive)[color.yellow](#var_color.yellow)[color.navy](#var_color.navy)[color.blue](#var_color.blue)[color.teal](#var_color.teal)[color.aqua](#var_color.aqua)[color.orange](#var_color.orange)

## color.silver

Is a named constant for #B2B5BE color.

### Type

` const color `

### See also

[color.black](#var_color.black)[color.gray](#var_color.gray)[color.white](#var_color.white)[color.maroon](#var_color.maroon)[color.red](#var_color.red)[color.purple](#var_color.purple)[color.fuchsia](#var_color.fuchsia)[color.green](#var_color.green)[color.lime](#var_color.lime)[color.olive](#var_color.olive)[color.yellow](#var_color.yellow)[color.navy](#var_color.navy)[color.blue](#var_color.blue)[color.teal](#var_color.teal)[color.aqua](#var_color.aqua)[color.orange](#var_color.orange)

## color.teal

Is a named constant for #00897B color.

### Type

` const color `

### See also

[color.black](#var_color.black)[color.silver](#var_color.silver)[color.gray](#var_color.gray)[color.white](#var_color.white)[color.maroon](#var_color.maroon)[color.red](#var_color.red)[color.purple](#var_color.purple)[color.fuchsia](#var_color.fuchsia)[color.green](#var_color.green)[color.lime](#var_color.lime)[color.olive](#var_color.olive)[color.yellow](#var_color.yellow)[color.navy](#var_color.navy)[color.blue](#var_color.blue)[color.aqua](#var_color.aqua)[color.orange](#var_color.orange)

## color.white

Is a named constant for #FFFFFF color.

### Type

` const color `

### See also

[color.black](#var_color.black)[color.silver](#var_color.silver)[color.gray](#var_color.gray)[color.maroon](#var_color.maroon)[color.red](#var_color.red)[color.purple](#var_color.purple)[color.fuchsia](#var_color.fuchsia)[color.green](#var_color.green)[color.lime](#var_color.lime)[color.olive](#var_color.olive)[color.yellow](#var_color.yellow)[color.navy](#var_color.navy)[color.blue](#var_color.blue)[color.teal](#var_color.teal)[color.aqua](#var_color.aqua)[color.orange](#var_color.orange)

## color.yellow

Is a named constant for #FFEB3B color.

### Type

` const color `

### See also

[color.black](#var_color.black)[color.silver](#var_color.silver)[color.gray](#var_color.gray)[color.white](#var_color.white)[color.maroon](#var_color.maroon)[color.red](#var_color.red)[color.purple](#var_color.purple)[color.fuchsia](#var_color.fuchsia)[color.green](#var_color.green)[color.lime](#var_color.lime)[color.olive](#var_color.olive)[color.navy](#var_color.navy)[color.blue](#var_color.blue)[color.teal](#var_color.teal)[color.aqua](#var_color.aqua)[color.orange](#var_color.orange)

## currency.AUD

Australian dollar.

### Type

` const string `

### See also

[strategy](#fun_strategy)

## currency.BTC

Bitcoin.

### Type

` const string `

### See also

[strategy](#fun_strategy)

## currency.CAD

Canadian dollar.

### Type

` const string `

### See also

[strategy](#fun_strategy)

## currency.CHF

Swiss franc.

### Type

` const string `

### See also

[strategy](#fun_strategy)

## currency.ETH

Ethereum.

### Type

` const string `

### See also

[strategy](#fun_strategy)

## currency.EUR

Euro.

### Type

` const string `

### See also

[strategy](#fun_strategy)

## currency.GBP

Pound sterling.

### Type

` const string `

### See also

[strategy](#fun_strategy)

## currency.HKD

Hong Kong dollar.

### Type

` const string `

### See also

[strategy](#fun_strategy)

## currency.INR

Indian rupee.

### Type

` const string `

### See also

[strategy](#fun_strategy)

## currency.JPY

Japanese yen.

### Type

` const string `

### See also

[strategy](#fun_strategy)

## currency.KRW

South Korean won.

### Type

` const string `

### See also

[strategy](#fun_strategy)

## currency.MYR

Malaysian ringgit.

### Type

` const string `

### See also

[strategy](#fun_strategy)

## currency.NOK

Norwegian krone.

### Type

` const string `

### See also

[strategy](#fun_strategy)

## currency.NONE

Unspecified currency.

### Type

` const string `

### See also

[strategy](#fun_strategy)

## currency.NZD

New Zealand dollar.

### Type

` const string `

### See also

[strategy](#fun_strategy)

## currency.RUB

Russian ruble.

### Type

` const string `

### See also

[strategy](#fun_strategy)

## currency.SEK

Swedish krona.

### Type

` const string `

### See also

[strategy](#fun_strategy)

## currency.SGD

Singapore dollar.

### Type

` const string `

### See also

[strategy](#fun_strategy)

## currency.TRY

Turkish lira.

### Type

` const string `

### See also

[strategy](#fun_strategy)

## currency.USD

United States dollar.

### Type

` const string `

### See also

[strategy](#fun_strategy)

## currency.USDT

Tether.

### Type

` const string `

### See also

[strategy](#fun_strategy)

## currency.ZAR

South African rand.

### Type

` const string `

### See also

[strategy](#fun_strategy)

## dayofweek.friday

Is a named constant for return value of [dayofweek](#fun_dayofweek) function and value of [dayofweek](#var_dayofweek) variable.

### Type

` const int `

### See also

[dayofweek.sunday](#var_dayofweek.sunday)[dayofweek.monday](#var_dayofweek.monday)[dayofweek.tuesday](#var_dayofweek.tuesday)[dayofweek.wednesday](#var_dayofweek.wednesday)[dayofweek.thursday](#var_dayofweek.thursday)[dayofweek.saturday](#var_dayofweek.saturday)

## dayofweek.monday

Is a named constant for return value of [dayofweek](#fun_dayofweek) function and value of [dayofweek](#var_dayofweek) variable.

### Type

` const int `

### See also

[dayofweek.sunday](#var_dayofweek.sunday)[dayofweek.tuesday](#var_dayofweek.tuesday)[dayofweek.wednesday](#var_dayofweek.wednesday)[dayofweek.thursday](#var_dayofweek.thursday)[dayofweek.friday](#var_dayofweek.friday)[dayofweek.saturday](#var_dayofweek.saturday)

## dayofweek.saturday

Is a named constant for return value of [dayofweek](#fun_dayofweek) function and value of [dayofweek](#var_dayofweek) variable.

### Type

` const int `

### See also

[dayofweek.sunday](#var_dayofweek.sunday)[dayofweek.monday](#var_dayofweek.monday)[dayofweek.tuesday](#var_dayofweek.tuesday)[dayofweek.wednesday](#var_dayofweek.wednesday)[dayofweek.thursday](#var_dayofweek.thursday)[dayofweek.friday](#var_dayofweek.friday)

## dayofweek.sunday

Is a named constant for return value of [dayofweek](#fun_dayofweek) function and value of [dayofweek](#var_dayofweek) variable.

### Type

` const int `

### See also

[dayofweek.monday](#var_dayofweek.monday)[dayofweek.tuesday](#var_dayofweek.tuesday)[dayofweek.wednesday](#var_dayofweek.wednesday)[dayofweek.thursday](#var_dayofweek.thursday)[dayofweek.friday](#var_dayofweek.friday)[dayofweek.saturday](#var_dayofweek.saturday)

## dayofweek.thursday

Is a named constant for return value of [dayofweek](#fun_dayofweek) function and value of [dayofweek](#var_dayofweek) variable.

### Type

` const int `

### See also

[dayofweek.sunday](#var_dayofweek.sunday)[dayofweek.monday](#var_dayofweek.monday)[dayofweek.tuesday](#var_dayofweek.tuesday)[dayofweek.wednesday](#var_dayofweek.wednesday)[dayofweek.friday](#var_dayofweek.friday)[dayofweek.saturday](#var_dayofweek.saturday)

## dayofweek.tuesday

Is a named constant for return value of [dayofweek](#fun_dayofweek) function and value of [dayofweek](#var_dayofweek) variable.

### Type

` const int `

### See also

[dayofweek.sunday](#var_dayofweek.sunday)[dayofweek.monday](#var_dayofweek.monday)[dayofweek.wednesday](#var_dayofweek.wednesday)[dayofweek.thursday](#var_dayofweek.thursday)[dayofweek.friday](#var_dayofweek.friday)[dayofweek.saturday](#var_dayofweek.saturday)

## dayofweek.wednesday

Is a named constant for return value of [dayofweek](#fun_dayofweek) function and value of [dayofweek](#var_dayofweek) variable.

### Type

` const int `

### See also

[dayofweek.sunday](#var_dayofweek.sunday)[dayofweek.monday](#var_dayofweek.monday)[dayofweek.tuesday](#var_dayofweek.tuesday)[dayofweek.thursday](#var_dayofweek.thursday)[dayofweek.friday](#var_dayofweek.friday)[dayofweek.saturday](#var_dayofweek.saturday)

## display.all

A named constant for use with the `display` parameter of `plot_()` and `input_()` functions. Displays plotted or input values in all possible locations.

### Type

` const plot_simple_display `

### See also

[plot](#fun_plot)[plotshape](#fun_plotshape)[plotchar](#fun_plotchar)[plotarrow](#fun_plotarrow)[plotbar](#fun_plotbar)[plotcandle](#fun_plotcandle)

## display.data_window

A named constant for use with the `display` parameter of `plot_()` and `input_()` functions. Displays plotted or input values in the Data Window, a menu accessible from the chart's right sidebar.

### Type

` const plot_display `

### See also

[plot](#fun_plot)[plotshape](#fun_plotshape)[plotchar](#fun_plotchar)[plotarrow](#fun_plotarrow)[plotbar](#fun_plotbar)[plotcandle](#fun_plotcandle)

## display.none

A named constant for use with the `display` parameter of `plot_()` and `input_()` functions. `plot_()` functions using this will not display their plotted values anywhere. However, alert template messages and [fill](#fun_fill) functions can still use the values, and they will appear in exported chart data. `input_()` functions using this constant will only display their values within the script's settings.

### Type

` const plot_simple_display `

### See also

[plot](#fun_plot)[plotshape](#fun_plotshape)[plotchar](#fun_plotchar)[plotarrow](#fun_plotarrow)[plotbar](#fun_plotbar)[plotcandle](#fun_plotcandle)

## display.pane

A named constant for use with the `display` parameter of `plot*()` functions. Displays plotted values in the chart pane used by the script.

### Type

` const plot_display `

### See also

[plot](#fun_plot)[plotshape](#fun_plotshape)[plotchar](#fun_plotchar)[plotarrow](#fun_plotarrow)[plotbar](#fun_plotbar)[plotcandle](#fun_plotcandle)

## display.price_scale

A named constant for use with the `display` parameter of `plot*()` functions. Displays the plot's label and value on the price scale if the chart's settings allow it.

### Type

` const plot_display `

### See also

[plot](#fun_plot)[plotshape](#fun_plotshape)[plotchar](#fun_plotchar)[plotarrow](#fun_plotarrow)[plotbar](#fun_plotbar)[plotcandle](#fun_plotcandle)

## display.status_line

A named constant for use with the `display` parameter of `plot_()` and `input_()` functions. Displays plotted or input values in the status line next to the script's name on the chart if the chart's settings allow it.

### Type

` const plot_display `

### See also

[plot](#fun_plot)[plotshape](#fun_plotshape)[plotchar](#fun_plotchar)[plotarrow](#fun_plotarrow)[plotbar](#fun_plotbar)[plotcandle](#fun_plotcandle)

## dividends.future_amount

Returns the payment amount of the upcoming dividend in the currency of the current instrument, or [na](#var_na) if this data isn't available.

### Type

` series float `

## dividends.future_ex_date

Returns the Ex-dividend date (Ex-date) of the current instrument's next dividend payment, or [na](#var_na) if this data isn't available. Ex-dividend date signifies when investors are no longer entitled to a payout from the most recent dividend. Only those who purchased shares before this day are entitled to the dividend payment.

### Type

` series float `

## dividends.future_pay_date

Returns the Payment date (Pay date) of the current instrument's next dividend payment, or [na](#var_na) if this data isn't available. Payment date signifies the day when eligible investors will receive the dividend payment.

### Type

` series float `

## dividends.gross

A named constant for the [request.dividends](#fun_request.dividends) function. Is used to request the dividends return on a stock before deductions.

### Type

` const string `

### See also

[request.dividends](#fun_request.dividends)

## dividends.net

A named constant for the [request.dividends](#fun_request.dividends) function. Is used to request the dividends return on a stock after deductions.

### Type

` const string `

### See also

[request.dividends](#fun_request.dividends)

## earnings.actual

A named constant for the [request.earnings](#fun_request.earnings) function. Is used to request the earnings value as it was reported.

### Type

` const string `

### See also

[request.earnings](#fun_request.earnings)

## earnings.estimate

A named constant for the [request.earnings](#fun_request.earnings) function. Is used to request the estimated earnings value.

### Type

` const string `

### See also

[request.earnings](#fun_request.earnings)

## earnings.standardized

A named constant for the [request.earnings](#fun_request.earnings) function. Is used to request the standardized earnings value.

### Type

` const string `

### See also

[request.earnings](#fun_request.earnings)

## extend.both

A named constant for [line.new](#fun_line.new) and [line.set_extend](#fun_line.set_extend) functions.

### Type

` const string `

### See also

[line.new](#fun_line.new)[line.set_extend](#fun_line.set_extend)[extend.none](#var_extend.none)[extend.left](#var_extend.left)[extend.right](#var_extend.right)

## extend.left

A named constant for [line.new](#fun_line.new) and [line.set_extend](#fun_line.set_extend) functions.

### Type

` const string `

### See also

[line.new](#fun_line.new)[line.set_extend](#fun_line.set_extend)[extend.none](#var_extend.none)[extend.right](#var_extend.right)[extend.both](#var_extend.both)

## extend.none

A named constant for [line.new](#fun_line.new) and [line.set_extend](#fun_line.set_extend) functions.

### Type

` const string `

### See also

[line.new](#fun_line.new)[line.set_extend](#fun_line.set_extend)[extend.left](#var_extend.left)[extend.right](#var_extend.right)[extend.both](#var_extend.both)

## extend.right

A named constant for [line.new](#fun_line.new) and [line.set_extend](#fun_line.set_extend) functions.

### Type

` const string `

### See also

[line.new](#fun_line.new)[line.set_extend](#fun_line.set_extend)[extend.none](#var_extend.none)[extend.left](#var_extend.left)[extend.both](#var_extend.both)

## font.family_default

Default text font for [box.new](#fun_box.new), [box.set_text_font_family](#fun_box.set_text_font_family), [label.new](#fun_label.new), [label.set_text_font_family](#fun_label.set_text_font_family), [table.cell](#fun_table.cell) and [table.cell_set_text_font_family](#fun_table.cell_set_text_font_family) functions.

### Type

` const string `

### See also

[box.new](#fun_box.new)[box.set_text_font_family](#fun_box.set_text_font_family)[label.new](#fun_label.new)[label.set_text_font_family](#fun_label.set_text_font_family)[table.cell](#fun_table.cell)[table.cell_set_text_font_family](#fun_table.cell_set_text_font_family)[font.family_monospace](#var_font.family_monospace)

## font.family_monospace

Monospace text font for [box.new](#fun_box.new), [box.set_text_font_family](#fun_box.set_text_font_family), [label.new](#fun_label.new), [label.set_text_font_family](#fun_label.set_text_font_family), [table.cell](#fun_table.cell) and [table.cell_set_text_font_family](#fun_table.cell_set_text_font_family) functions.

### Type

` const string `

### See also

[box.new](#fun_box.new)[box.set_text_font_family](#fun_box.set_text_font_family)[label.new](#fun_label.new)[label.set_text_font_family](#fun_label.set_text_font_family)[table.cell](#fun_table.cell)[table.cell_set_text_font_family](#fun_table.cell_set_text_font_family)[font.family_default](#var_font.family_default)

## format.inherit

Is a named constant for selecting the formatting of the script output values from the parent series in the [indicator](#fun_indicator) function.

### Type

` const string `

### See also

[indicator](#fun_indicator)[format.price](#var_format.price)[format.volume](#var_format.volume)[format.percent](#var_format.percent)

## format.mintick

Is a named constant to use with the [str.tostring](#fun_str.tostring) function. Passing a number to [str.tostring](#fun_str.tostring) with this argument rounds the number to the nearest value that can be divided by [syminfo.mintick](#var_syminfo.mintick), without the remainder, with ties rounding up, and returns the string version of said value with trailing zeroes.

### Type

` const string `

### See also

[indicator](#fun_indicator)[format.inherit](#var_format.inherit)[format.price](#var_format.price)[format.volume](#var_format.volume)

## format.percent

Is a named constant for selecting the formatting of the script output values as a percentage in the indicator function. It adds a percent sign after values.

### Type

` const string `

### Remarks

The default precision is 2, regardless of the precision of the chart itself. This can be changed with the 'precision' argument of the [indicator](#fun_indicator) function.

### See also

[indicator](#fun_indicator)[format.inherit](#var_format.inherit)[format.price](#var_format.price)[format.volume](#var_format.volume)

## format.price

Is a named constant for selecting the formatting of the script output values as prices in the [indicator](#fun_indicator) function.

### Type

` const string `

### Remarks

If format is format.price, default precision value is set. You can use the precision argument of indicator function to change the precision value.

### See also

[indicator](#fun_indicator)[format.inherit](#var_format.inherit)[format.volume](#var_format.volume)[format.percent](#var_format.percent)

## format.volume

Is a named constant for selecting the formatting of the script output values as volume in the [indicator](#fun_indicator) function, e.g. '5183' will be formatted as '5.183K'.

### Type

` const string `

### See also

[indicator](#fun_indicator)[format.inherit](#var_format.inherit)[format.price](#var_format.price)[format.percent](#var_format.percent)

## hline.style_dashed

Is a named constant for dashed linestyle of [hline](#fun_hline) function.

### Type

` const hline_style `

### See also

[hline.style_solid](#var_hline.style_solid)[hline.style_dotted](#var_hline.style_dotted)

## hline.style_dotted

Is a named constant for dotted linestyle of [hline](#fun_hline) function.

### Type

` const hline_style `

### See also

[hline.style_solid](#var_hline.style_solid)[hline.style_dashed](#var_hline.style_dashed)

## hline.style_solid

Is a named constant for solid linestyle of [hline](#fun_hline) function.

### Type

` const hline_style `

### See also

[hline.style_dotted](#var_hline.style_dotted)[hline.style_dashed](#var_hline.style_dashed)

## label.style_arrowdown

Label style for [label.new](#fun_label.new) and [label.set_style](#fun_label.set_style) functions.

### Type

` const string `

### See also

[label.new](#fun_label.new)[label.set_style](#fun_label.set_style)[label.set_textalign](#fun_label.set_textalign)[label.style_none](#var_label.style_none)[label.style_xcross](#var_label.style_xcross)[label.style_cross](#var_label.style_cross)[label.style_triangleup](#var_label.style_triangleup)[label.style_triangledown](#var_label.style_triangledown)[label.style_flag](#var_label.style_flag)[label.style_circle](#var_label.style_circle)[label.style_arrowup](#var_label.style_arrowup)[label.style_label_up](#var_label.style_label_up)[label.style_label_down](#var_label.style_label_down)[label.style_label_left](#var_label.style_label_left)[label.style_label_right](#var_label.style_label_right)[label.style_label_lower_left](#var_label.style_label_lower_left)[label.style_label_lower_right](#var_label.style_label_lower_right)[label.style_label_upper_left](#var_label.style_label_upper_left)[label.style_label_upper_right](#var_label.style_label_upper_right)[label.style_label_center](#var_label.style_label_center)[label.style_square](#var_label.style_square)[label.style_diamond](#var_label.style_diamond)

## label.style_arrowup

Label style for [label.new](#fun_label.new) and [label.set_style](#fun_label.set_style) functions.

### Type

` const string `

### See also

[label.new](#fun_label.new)[label.set_style](#fun_label.set_style)[label.set_textalign](#fun_label.set_textalign)[label.style_none](#var_label.style_none)[label.style_xcross](#var_label.style_xcross)[label.style_cross](#var_label.style_cross)[label.style_triangleup](#var_label.style_triangleup)[label.style_triangledown](#var_label.style_triangledown)[label.style_flag](#var_label.style_flag)[label.style_circle](#var_label.style_circle)[label.style_arrowdown](#var_label.style_arrowdown)[label.style_label_up](#var_label.style_label_up)[label.style_label_down](#var_label.style_label_down)[label.style_label_left](#var_label.style_label_left)[label.style_label_right](#var_label.style_label_right)[label.style_label_lower_left](#var_label.style_label_lower_left)[label.style_label_lower_right](#var_label.style_label_lower_right)[label.style_label_upper_left](#var_label.style_label_upper_left)[label.style_label_upper_right](#var_label.style_label_upper_right)[label.style_label_center](#var_label.style_label_center)[label.style_square](#var_label.style_square)[label.style_diamond](#var_label.style_diamond)

## label.style_circle

Label style for [label.new](#fun_label.new) and [label.set_style](#fun_label.set_style) functions.

### Type

` const string `

### See also

[label.new](#fun_label.new)[label.set_style](#fun_label.set_style)[label.set_textalign](#fun_label.set_textalign)[label.style_none](#var_label.style_none)[label.style_xcross](#var_label.style_xcross)[label.style_cross](#var_label.style_cross)[label.style_triangleup](#var_label.style_triangleup)[label.style_triangledown](#var_label.style_triangledown)[label.style_flag](#var_label.style_flag)[label.style_arrowup](#var_label.style_arrowup)[label.style_arrowdown](#var_label.style_arrowdown)[label.style_label_up](#var_label.style_label_up)[label.style_label_down](#var_label.style_label_down)[label.style_label_left](#var_label.style_label_left)[label.style_label_right](#var_label.style_label_right)[label.style_label_lower_left](#var_label.style_label_lower_left)[label.style_label_lower_right](#var_label.style_label_lower_right)[label.style_label_upper_left](#var_label.style_label_upper_left)[label.style_label_upper_right](#var_label.style_label_upper_right)[label.style_label_center](#var_label.style_label_center)[label.style_square](#var_label.style_square)[label.style_diamond](#var_label.style_diamond)

## label.style_cross

Label style for [label.new](#fun_label.new) and [label.set_style](#fun_label.set_style) functions.

### Type

` const string `

### See also

[label.new](#fun_label.new)[label.set_style](#fun_label.set_style)[label.set_textalign](#fun_label.set_textalign)[label.style_none](#var_label.style_none)[label.style_xcross](#var_label.style_xcross)[label.style_triangleup](#var_label.style_triangleup)[label.style_triangledown](#var_label.style_triangledown)[label.style_flag](#var_label.style_flag)[label.style_circle](#var_label.style_circle)[label.style_arrowup](#var_label.style_arrowup)[label.style_arrowdown](#var_label.style_arrowdown)[label.style_label_up](#var_label.style_label_up)[label.style_label_down](#var_label.style_label_down)[label.style_label_left](#var_label.style_label_left)[label.style_label_right](#var_label.style_label_right)[label.style_label_lower_left](#var_label.style_label_lower_left)[label.style_label_lower_right](#var_label.style_label_lower_right)[label.style_label_upper_left](#var_label.style_label_upper_left)[label.style_label_upper_right](#var_label.style_label_upper_right)[label.style_label_center](#var_label.style_label_center)[label.style_square](#var_label.style_square)[label.style_diamond](#var_label.style_diamond)

## label.style_diamond

Label style for [label.new](#fun_label.new) and [label.set_style](#fun_label.set_style) functions.

### Type

` const string `

### See also

[label.new](#fun_label.new)[label.set_style](#fun_label.set_style)[label.set_textalign](#fun_label.set_textalign)[label.style_none](#var_label.style_none)[label.style_xcross](#var_label.style_xcross)[label.style_cross](#var_label.style_cross)[label.style_triangleup](#var_label.style_triangleup)[label.style_triangledown](#var_label.style_triangledown)[label.style_flag](#var_label.style_flag)[label.style_circle](#var_label.style_circle)[label.style_arrowup](#var_label.style_arrowup)[label.style_arrowdown](#var_label.style_arrowdown)[label.style_label_up](#var_label.style_label_up)[label.style_label_down](#var_label.style_label_down)[label.style_label_left](#var_label.style_label_left)[label.style_label_right](#var_label.style_label_right)[label.style_label_lower_left](#var_label.style_label_lower_left)[label.style_label_lower_right](#var_label.style_label_lower_right)[label.style_label_upper_left](#var_label.style_label_upper_left)[label.style_label_upper_right](#var_label.style_label_upper_right)[label.style_label_center](#var_label.style_label_center)[label.style_square](#var_label.style_square)

## label.style_flag

Label style for [label.new](#fun_label.new) and [label.set_style](#fun_label.set_style) functions.

### Type

` const string `

### See also

[label.new](#fun_label.new)[label.set_style](#fun_label.set_style)[label.set_textalign](#fun_label.set_textalign)[label.style_none](#var_label.style_none)[label.style_xcross](#var_label.style_xcross)[label.style_cross](#var_label.style_cross)[label.style_triangleup](#var_label.style_triangleup)[label.style_triangledown](#var_label.style_triangledown)[label.style_circle](#var_label.style_circle)[label.style_arrowup](#var_label.style_arrowup)[label.style_arrowdown](#var_label.style_arrowdown)[label.style_label_up](#var_label.style_label_up)[label.style_label_down](#var_label.style_label_down)[label.style_label_left](#var_label.style_label_left)[label.style_label_right](#var_label.style_label_right)[label.style_label_lower_left](#var_label.style_label_lower_left)[label.style_label_lower_right](#var_label.style_label_lower_right)[label.style_label_upper_left](#var_label.style_label_upper_left)[label.style_label_upper_right](#var_label.style_label_upper_right)[label.style_label_center](#var_label.style_label_center)[label.style_square](#var_label.style_square)[label.style_diamond](#var_label.style_diamond)

## label.style_label_center

Label style for [label.new](#fun_label.new) and [label.set_style](#fun_label.set_style) functions.

### Type

` const string `

### See also

[label.new](#fun_label.new)[label.set_style](#fun_label.set_style)[label.set_textalign](#fun_label.set_textalign)[label.style_none](#var_label.style_none)[label.style_xcross](#var_label.style_xcross)[label.style_cross](#var_label.style_cross)[label.style_triangleup](#var_label.style_triangleup)[label.style_triangledown](#var_label.style_triangledown)[label.style_flag](#var_label.style_flag)[label.style_circle](#var_label.style_circle)[label.style_arrowup](#var_label.style_arrowup)[label.style_arrowdown](#var_label.style_arrowdown)[label.style_label_up](#var_label.style_label_up)[label.style_label_down](#var_label.style_label_down)[label.style_label_left](#var_label.style_label_left)[label.style_label_right](#var_label.style_label_right)[label.style_label_lower_left](#var_label.style_label_lower_left)[label.style_label_lower_right](#var_label.style_label_lower_right)[label.style_label_upper_left](#var_label.style_label_upper_left)[label.style_label_upper_right](#var_label.style_label_upper_right)[label.style_square](#var_label.style_square)[label.style_diamond](#var_label.style_diamond)

## label.style_label_down

Label style for [label.new](#fun_label.new) and [label.set_style](#fun_label.set_style) functions.

### Type

` const string `

### See also

[label.new](#fun_label.new)[label.set_style](#fun_label.set_style)[label.set_textalign](#fun_label.set_textalign)[label.style_none](#var_label.style_none)[label.style_xcross](#var_label.style_xcross)[label.style_cross](#var_label.style_cross)[label.style_triangleup](#var_label.style_triangleup)[label.style_triangledown](#var_label.style_triangledown)[label.style_flag](#var_label.style_flag)[label.style_circle](#var_label.style_circle)[label.style_arrowup](#var_label.style_arrowup)[label.style_arrowdown](#var_label.style_arrowdown)[label.style_label_up](#var_label.style_label_up)[label.style_label_left](#var_label.style_label_left)[label.style_label_right](#var_label.style_label_right)[label.style_label_lower_left](#var_label.style_label_lower_left)[label.style_label_lower_right](#var_label.style_label_lower_right)[label.style_label_upper_left](#var_label.style_label_upper_left)[label.style_label_upper_right](#var_label.style_label_upper_right)[label.style_label_center](#var_label.style_label_center)[label.style_square](#var_label.style_square)[label.style_diamond](#var_label.style_diamond)

## label.style_label_left

Label style for [label.new](#fun_label.new) and [label.set_style](#fun_label.set_style) functions.

### Type

` const string `

### See also

[label.new](#fun_label.new)[label.set_style](#fun_label.set_style)[label.set_textalign](#fun_label.set_textalign)[label.style_none](#var_label.style_none)[label.style_xcross](#var_label.style_xcross)[label.style_cross](#var_label.style_cross)[label.style_triangleup](#var_label.style_triangleup)[label.style_triangledown](#var_label.style_triangledown)[label.style_flag](#var_label.style_flag)[label.style_circle](#var_label.style_circle)[label.style_arrowup](#var_label.style_arrowup)[label.style_arrowdown](#var_label.style_arrowdown)[label.style_label_up](#var_label.style_label_up)[label.style_label_down](#var_label.style_label_down)[label.style_label_right](#var_label.style_label_right)[label.style_label_lower_left](#var_label.style_label_lower_left)[label.style_label_lower_right](#var_label.style_label_lower_right)[label.style_label_upper_left](#var_label.style_label_upper_left)[label.style_label_upper_right](#var_label.style_label_upper_right)[label.style_label_center](#var_label.style_label_center)[label.style_square](#var_label.style_square)[label.style_diamond](#var_label.style_diamond)

## label.style_label_lower_left

Label style for [label.new](#fun_label.new) and [label.set_style](#fun_label.set_style) functions.

### Type

` const string `

### See also

[label.new](#fun_label.new)[label.set_style](#fun_label.set_style)[label.set_textalign](#fun_label.set_textalign)[label.style_none](#var_label.style_none)[label.style_xcross](#var_label.style_xcross)[label.style_cross](#var_label.style_cross)[label.style_triangleup](#var_label.style_triangleup)[label.style_triangledown](#var_label.style_triangledown)[label.style_flag](#var_label.style_flag)[label.style_circle](#var_label.style_circle)[label.style_arrowup](#var_label.style_arrowup)[label.style_arrowdown](#var_label.style_arrowdown)[label.style_label_up](#var_label.style_label_up)[label.style_label_down](#var_label.style_label_down)[label.style_label_left](#var_label.style_label_left)[label.style_label_right](#var_label.style_label_right)[label.style_label_lower_right](#var_label.style_label_lower_right)[label.style_label_upper_left](#var_label.style_label_upper_left)[label.style_label_upper_right](#var_label.style_label_upper_right)[label.style_label_center](#var_label.style_label_center)[label.style_square](#var_label.style_square)[label.style_diamond](#var_label.style_diamond)

## label.style_label_lower_right

Label style for [label.new](#fun_label.new) and [label.set_style](#fun_label.set_style) functions.

### Type

` const string `

### See also

[label.new](#fun_label.new)[label.set_style](#fun_label.set_style)[label.set_textalign](#fun_label.set_textalign)[label.style_none](#var_label.style_none)[label.style_xcross](#var_label.style_xcross)[label.style_cross](#var_label.style_cross)[label.style_triangleup](#var_label.style_triangleup)[label.style_triangledown](#var_label.style_triangledown)[label.style_flag](#var_label.style_flag)[label.style_circle](#var_label.style_circle)[label.style_arrowup](#var_label.style_arrowup)[label.style_arrowdown](#var_label.style_arrowdown)[label.style_label_up](#var_label.style_label_up)[label.style_label_down](#var_label.style_label_down)[label.style_label_left](#var_label.style_label_left)[label.style_label_right](#var_label.style_label_right)[label.style_label_lower_left](#var_label.style_label_lower_left)[label.style_label_upper_left](#var_label.style_label_upper_left)[label.style_label_upper_right](#var_label.style_label_upper_right)[label.style_label_center](#var_label.style_label_center)[label.style_square](#var_label.style_square)[label.style_diamond](#var_label.style_diamond)

## label.style_label_right

Label style for [label.new](#fun_label.new) and [label.set_style](#fun_label.set_style) functions.

### Type

` const string `

### See also

[label.new](#fun_label.new)[label.set_style](#fun_label.set_style)[label.set_textalign](#fun_label.set_textalign)[label.style_none](#var_label.style_none)[label.style_xcross](#var_label.style_xcross)[label.style_cross](#var_label.style_cross)[label.style_triangleup](#var_label.style_triangleup)[label.style_triangledown](#var_label.style_triangledown)[label.style_flag](#var_label.style_flag)[label.style_circle](#var_label.style_circle)[label.style_arrowup](#var_label.style_arrowup)[label.style_arrowdown](#var_label.style_arrowdown)[label.style_label_up](#var_label.style_label_up)[label.style_label_down](#var_label.style_label_down)[label.style_label_left](#var_label.style_label_left)[label.style_label_lower_left](#var_label.style_label_lower_left)[label.style_label_lower_right](#var_label.style_label_lower_right)[label.style_label_upper_left](#var_label.style_label_upper_left)[label.style_label_upper_right](#var_label.style_label_upper_right)[label.style_label_center](#var_label.style_label_center)[label.style_square](#var_label.style_square)[label.style_diamond](#var_label.style_diamond)

## label.style_label_up

Label style for [label.new](#fun_label.new) and [label.set_style](#fun_label.set_style) functions.

### Type

` const string `

### See also

[label.new](#fun_label.new)[label.set_style](#fun_label.set_style)[label.set_textalign](#fun_label.set_textalign)[label.style_none](#var_label.style_none)[label.style_xcross](#var_label.style_xcross)[label.style_cross](#var_label.style_cross)[label.style_triangleup](#var_label.style_triangleup)[label.style_triangledown](#var_label.style_triangledown)[label.style_flag](#var_label.style_flag)[label.style_circle](#var_label.style_circle)[label.style_arrowup](#var_label.style_arrowup)[label.style_arrowdown](#var_label.style_arrowdown)[label.style_label_down](#var_label.style_label_down)[label.style_label_left](#var_label.style_label_left)[label.style_label_right](#var_label.style_label_right)[label.style_label_lower_left](#var_label.style_label_lower_left)[label.style_label_lower_right](#var_label.style_label_lower_right)[label.style_label_upper_left](#var_label.style_label_upper_left)[label.style_label_upper_right](#var_label.style_label_upper_right)[label.style_label_center](#var_label.style_label_center)[label.style_square](#var_label.style_square)[label.style_diamond](#var_label.style_diamond)

## label.style_label_upper_left

Label style for [label.new](#fun_label.new) and [label.set_style](#fun_label.set_style) functions.

### Type

` const string `

### See also

[label.new](#fun_label.new)[label.set_style](#fun_label.set_style)[label.set_textalign](#fun_label.set_textalign)[label.style_none](#var_label.style_none)[label.style_xcross](#var_label.style_xcross)[label.style_cross](#var_label.style_cross)[label.style_triangleup](#var_label.style_triangleup)[label.style_triangledown](#var_label.style_triangledown)[label.style_flag](#var_label.style_flag)[label.style_circle](#var_label.style_circle)[label.style_arrowup](#var_label.style_arrowup)[label.style_arrowdown](#var_label.style_arrowdown)[label.style_label_up](#var_label.style_label_up)[label.style_label_down](#var_label.style_label_down)[label.style_label_left](#var_label.style_label_left)[label.style_label_right](#var_label.style_label_right)[label.style_label_lower_left](#var_label.style_label_lower_left)[label.style_label_lower_right](#var_label.style_label_lower_right)[label.style_label_upper_right](#var_label.style_label_upper_right)[label.style_label_center](#var_label.style_label_center)[label.style_square](#var_label.style_square)[label.style_diamond](#var_label.style_diamond)

## label.style_label_upper_right

Label style for [label.new](#fun_label.new) and [label.set_style](#fun_label.set_style) functions.

### Type

` const string `

### See also

[label.new](#fun_label.new)[label.set_style](#fun_label.set_style)[label.set_textalign](#fun_label.set_textalign)[label.style_none](#var_label.style_none)[label.style_xcross](#var_label.style_xcross)[label.style_cross](#var_label.style_cross)[label.style_triangleup](#var_label.style_triangleup)[label.style_triangledown](#var_label.style_triangledown)[label.style_flag](#var_label.style_flag)[label.style_circle](#var_label.style_circle)[label.style_arrowup](#var_label.style_arrowup)[label.style_arrowdown](#var_label.style_arrowdown)[label.style_label_up](#var_label.style_label_up)[label.style_label_down](#var_label.style_label_down)[label.style_label_left](#var_label.style_label_left)[label.style_label_right](#var_label.style_label_right)[label.style_label_lower_left](#var_label.style_label_lower_left)[label.style_label_lower_right](#var_label.style_label_lower_right)[label.style_label_upper_left](#var_label.style_label_upper_left)[label.style_label_center](#var_label.style_label_center)[label.style_square](#var_label.style_square)[label.style_diamond](#var_label.style_diamond)

## label.style_none

Label style for [label.new](#fun_label.new) and [label.set_style](#fun_label.set_style) functions.

### Type

` const string `

### See also

[label.new](#fun_label.new)[label.set_style](#fun_label.set_style)[label.set_textalign](#fun_label.set_textalign)[label.style_xcross](#var_label.style_xcross)[label.style_cross](#var_label.style_cross)[label.style_triangleup](#var_label.style_triangleup)[label.style_triangledown](#var_label.style_triangledown)[label.style_flag](#var_label.style_flag)[label.style_circle](#var_label.style_circle)[label.style_arrowup](#var_label.style_arrowup)[label.style_arrowdown](#var_label.style_arrowdown)[label.style_label_up](#var_label.style_label_up)[label.style_label_down](#var_label.style_label_down)[label.style_label_left](#var_label.style_label_left)[label.style_label_right](#var_label.style_label_right)[label.style_label_center](#var_label.style_label_center)[label.style_square](#var_label.style_square)[label.style_diamond](#var_label.style_diamond)

## label.style_square

Label style for [label.new](#fun_label.new) and [label.set_style](#fun_label.set_style) functions.

### Type

` const string `

### See also

[label.new](#fun_label.new)[label.set_style](#fun_label.set_style)[label.set_textalign](#fun_label.set_textalign)[label.style_none](#var_label.style_none)[label.style_xcross](#var_label.style_xcross)[label.style_cross](#var_label.style_cross)[label.style_triangleup](#var_label.style_triangleup)[label.style_triangledown](#var_label.style_triangledown)[label.style_flag](#var_label.style_flag)[label.style_circle](#var_label.style_circle)[label.style_arrowup](#var_label.style_arrowup)[label.style_arrowdown](#var_label.style_arrowdown)[label.style_label_up](#var_label.style_label_up)[label.style_label_down](#var_label.style_label_down)[label.style_label_left](#var_label.style_label_left)[label.style_label_right](#var_label.style_label_right)[label.style_label_lower_left](#var_label.style_label_lower_left)[label.style_label_lower_right](#var_label.style_label_lower_right)[label.style_label_upper_left](#var_label.style_label_upper_left)[label.style_label_upper_right](#var_label.style_label_upper_right)[label.style_label_center](#var_label.style_label_center)[label.style_diamond](#var_label.style_diamond)

## label.style_text_outline

Label style for [label.new](#fun_label.new) and [label.set_style](#fun_label.set_style) functions.

### Type

` const string `

### See also

[label.new](#fun_label.new)[label.set_style](#fun_label.set_style)[label.set_textalign](#fun_label.set_textalign)[label.style_none](#var_label.style_none)[label.style_xcross](#var_label.style_xcross)[label.style_cross](#var_label.style_cross)[label.style_triangleup](#var_label.style_triangleup)[label.style_triangledown](#var_label.style_triangledown)[label.style_flag](#var_label.style_flag)[label.style_circle](#var_label.style_circle)[label.style_arrowup](#var_label.style_arrowup)[label.style_arrowdown](#var_label.style_arrowdown)[label.style_label_up](#var_label.style_label_up)[label.style_label_down](#var_label.style_label_down)[label.style_label_left](#var_label.style_label_left)[label.style_label_right](#var_label.style_label_right)[label.style_label_lower_left](#var_label.style_label_lower_left)[label.style_label_lower_right](#var_label.style_label_lower_right)[label.style_label_upper_left](#var_label.style_label_upper_left)[label.style_label_upper_right](#var_label.style_label_upper_right)[label.style_label_center](#var_label.style_label_center)[label.style_square](#var_label.style_square)[label.style_diamond](#var_label.style_diamond)

## label.style_triangledown

Label style for [label.new](#fun_label.new) and [label.set_style](#fun_label.set_style) functions.

### Type

` const string `

### See also

[label.new](#fun_label.new)[label.set_style](#fun_label.set_style)[label.set_textalign](#fun_label.set_textalign)[label.style_none](#var_label.style_none)[label.style_xcross](#var_label.style_xcross)[label.style_cross](#var_label.style_cross)[label.style_triangleup](#var_label.style_triangleup)[label.style_flag](#var_label.style_flag)[label.style_circle](#var_label.style_circle)[label.style_arrowup](#var_label.style_arrowup)[label.style_arrowdown](#var_label.style_arrowdown)[label.style_label_up](#var_label.style_label_up)[label.style_label_down](#var_label.style_label_down)[label.style_label_left](#var_label.style_label_left)[label.style_label_right](#var_label.style_label_right)[label.style_label_lower_left](#var_label.style_label_lower_left)[label.style_label_lower_right](#var_label.style_label_lower_right)[label.style_label_upper_left](#var_label.style_label_upper_left)[label.style_label_upper_right](#var_label.style_label_upper_right)[label.style_label_center](#var_label.style_label_center)[label.style_square](#var_label.style_square)[label.style_diamond](#var_label.style_diamond)

## label.style_triangleup

Label style for [label.new](#fun_label.new) and [label.set_style](#fun_label.set_style) functions.

### Type

` const string `

### See also

[label.new](#fun_label.new)[label.set_style](#fun_label.set_style)[label.set_textalign](#fun_label.set_textalign)[label.style_none](#var_label.style_none)[label.style_xcross](#var_label.style_xcross)[label.style_cross](#var_label.style_cross)[label.style_triangledown](#var_label.style_triangledown)[label.style_flag](#var_label.style_flag)[label.style_circle](#var_label.style_circle)[label.style_arrowup](#var_label.style_arrowup)[label.style_arrowdown](#var_label.style_arrowdown)[label.style_label_up](#var_label.style_label_up)[label.style_label_down](#var_label.style_label_down)[label.style_label_left](#var_label.style_label_left)[label.style_label_right](#var_label.style_label_right)[label.style_label_lower_left](#var_label.style_label_lower_left)[label.style_label_lower_right](#var_label.style_label_lower_right)[label.style_label_upper_left](#var_label.style_label_upper_left)[label.style_label_upper_right](#var_label.style_label_upper_right)[label.style_label_center](#var_label.style_label_center)[label.style_square](#var_label.style_square)[label.style_diamond](#var_label.style_diamond)

## label.style_xcross

Label style for [label.new](#fun_label.new) and [label.set_style](#fun_label.set_style) functions.

### Type

` const string `

### See also

[label.new](#fun_label.new)[label.set_style](#fun_label.set_style)[label.set_textalign](#fun_label.set_textalign)[label.style_none](#var_label.style_none)[label.style_cross](#var_label.style_cross)[label.style_triangleup](#var_label.style_triangleup)[label.style_triangledown](#var_label.style_triangledown)[label.style_flag](#var_label.style_flag)[label.style_circle](#var_label.style_circle)[label.style_arrowup](#var_label.style_arrowup)[label.style_arrowdown](#var_label.style_arrowdown)[label.style_label_up](#var_label.style_label_up)[label.style_label_down](#var_label.style_label_down)[label.style_label_left](#var_label.style_label_left)[label.style_label_right](#var_label.style_label_right)[label.style_label_center](#var_label.style_label_center)[label.style_square](#var_label.style_square)[label.style_diamond](#var_label.style_diamond)

## line.style_arrow_both

Line style for [line.new](#fun_line.new) and [line.set_style](#fun_line.set_style) functions. Solid line with arrows on both points.

### Type

` const string `

### See also

[line.new](#fun_line.new)[line.set_style](#fun_line.set_style)[line.style_solid](#var_line.style_solid)[line.style_dotted](#var_line.style_dotted)[line.style_dashed](#var_line.style_dashed)[line.style_arrow_left](#var_line.style_arrow_left)[line.style_arrow_right](#var_line.style_arrow_right)

## line.style_arrow_left

Line style for [line.new](#fun_line.new) and [line.set_style](#fun_line.set_style) functions. Solid line with arrow on the first point.

### Type

` const string `

### See also

[line.new](#fun_line.new)[line.set_style](#fun_line.set_style)[line.style_solid](#var_line.style_solid)[line.style_dotted](#var_line.style_dotted)[line.style_dashed](#var_line.style_dashed)[line.style_arrow_right](#var_line.style_arrow_right)[line.style_arrow_both](#var_line.style_arrow_both)

## line.style_arrow_right

Line style for [line.new](#fun_line.new) and [line.set_style](#fun_line.set_style) functions. Solid line with arrow on the second point.

### Type

` const string `

### See also

[line.new](#fun_line.new)[line.set_style](#fun_line.set_style)[line.style_solid](#var_line.style_solid)[line.style_dotted](#var_line.style_dotted)[line.style_dashed](#var_line.style_dashed)[line.style_arrow_left](#var_line.style_arrow_left)[line.style_arrow_both](#var_line.style_arrow_both)

## line.style_dashed

Line style for [line.new](#fun_line.new) and [line.set_style](#fun_line.set_style) functions.

### Type

` const string `

### See also

[line.new](#fun_line.new)[line.set_style](#fun_line.set_style)[line.style_solid](#var_line.style_solid)[line.style_dotted](#var_line.style_dotted)[line.style_arrow_left](#var_line.style_arrow_left)[line.style_arrow_right](#var_line.style_arrow_right)[line.style_arrow_both](#var_line.style_arrow_both)

## line.style_dotted

Line style for [line.new](#fun_line.new) and [line.set_style](#fun_line.set_style) functions.

### Type

` const string `

### See also

[line.new](#fun_line.new)[line.set_style](#fun_line.set_style)[line.style_solid](#var_line.style_solid)[line.style_dashed](#var_line.style_dashed)[line.style_arrow_left](#var_line.style_arrow_left)[line.style_arrow_right](#var_line.style_arrow_right)[line.style_arrow_both](#var_line.style_arrow_both)

## line.style_solid

Line style for [line.new](#fun_line.new) and [line.set_style](#fun_line.set_style) functions.

### Type

` const string `

### See also

[line.new](#fun_line.new)[line.set_style](#fun_line.set_style)[line.style_dotted](#var_line.style_dotted)[line.style_dashed](#var_line.style_dashed)[line.style_arrow_left](#var_line.style_arrow_left)[line.style_arrow_right](#var_line.style_arrow_right)[line.style_arrow_both](#var_line.style_arrow_both)

## location.abovebar

Location value for [plotshape](#fun_plotshape), [plotchar](#fun_plotchar) functions. Shape is plotted above main series bars.

### Type

` const string `

### See also

[plotshape](#fun_plotshape)[plotchar](#fun_plotchar)[location.belowbar](#var_location.belowbar)[location.top](#var_location.top)[location.bottom](#var_location.bottom)[location.absolute](#var_location.absolute)

## location.absolute

Location value for [plotshape](#fun_plotshape), [plotchar](#fun_plotchar) functions. Shape is plotted on chart using indicator value as a price coordinate.

### Type

` const string `

### See also

[plotshape](#fun_plotshape)[plotchar](#fun_plotchar)[location.abovebar](#var_location.abovebar)[location.belowbar](#var_location.belowbar)[location.top](#var_location.top)[location.bottom](#var_location.bottom)

## location.belowbar

Location value for [plotshape](#fun_plotshape), [plotchar](#fun_plotchar) functions. Shape is plotted below main series bars.

### Type

` const string `

### See also

[plotshape](#fun_plotshape)[plotchar](#fun_plotchar)[location.abovebar](#var_location.abovebar)[location.top](#var_location.top)[location.bottom](#var_location.bottom)[location.absolute](#var_location.absolute)

## location.bottom

Location value for [plotshape](#fun_plotshape), [plotchar](#fun_plotchar) functions. Shape is plotted near the bottom chart border.

### Type

` const string `

### See also

[plotshape](#fun_plotshape)[plotchar](#fun_plotchar)[location.abovebar](#var_location.abovebar)[location.belowbar](#var_location.belowbar)[location.top](#var_location.top)[location.absolute](#var_location.absolute)

## location.top

Location value for [plotshape](#fun_plotshape), [plotchar](#fun_plotchar) functions. Shape is plotted near the top chart border.

### Type

` const string `

### See also

[plotshape](#fun_plotshape)[plotchar](#fun_plotchar)[location.abovebar](#var_location.abovebar)[location.belowbar](#var_location.belowbar)[location.bottom](#var_location.bottom)[location.absolute](#var_location.absolute)

## math.e

Is a named constant for [Euler's number](https://en.wikipedia.org/wiki/E_(mathematical_constant)). It is equal to 2.7182818284590452.

### Type

` const float `

### See also

[math.phi](#var_math.phi)[math.pi](#var_math.pi)[math.rphi](#var_math.rphi)

## math.phi

Is a named constant for the [golden ratio](https://en.wikipedia.org/wiki/Golden_ratio). It is equal to 1.6180339887498948.

### Type

` const float `

### See also

[math.e](#var_math.e)[math.pi](#var_math.pi)[math.rphi](#var_math.rphi)

## math.pi

Is a named constant for [Archimedes' constant](https://en.wikipedia.org/wiki/Pi). It is equal to 3.1415926535897932.

### Type

` const float `

### See also

[math.e](#var_math.e)[math.phi](#var_math.phi)[math.rphi](#var_math.rphi)

## math.rphi

Is a named constant for the [golden ratio conjugate](https://en.wikipedia.org/wiki/Golden_ratio#Golden_ratio_conjugate). It is equal to 0.6180339887498948.

### Type

` const float `

### See also

[math.e](#var_math.e)[math.pi](#var_math.pi)[math.phi](#var_math.phi)

## order.ascending

Determines the sort order of the array from the smallest to the largest value.

### Type

` const sort_order `

### See also

[array.new_float](#fun_array.new_float)[array.sort](#fun_array.sort)

## order.descending

Determines the sort order of the array from the largest to the smallest value.

### Type

` const sort_order `

### See also

[array.new_float](#fun_array.new_float)[array.sort](#fun_array.sort)

## plot.style_area

A named constant for the 'Area' style, to be used as an argument for the `style` parameter in the [plot](#fun_plot) function.

### Type

` const plot_style `

### See also

[plot](#fun_plot)[plot.style_steplinebr](#var_plot.style_steplinebr)[plot.style_line](#var_plot.style_line)[plot.style_linebr](#var_plot.style_linebr)[plot.style_stepline](#var_plot.style_stepline)[plot.style_stepline_diamond](#var_plot.style_stepline_diamond)[plot.style_histogram](#var_plot.style_histogram)[plot.style_areabr](#var_plot.style_areabr)[plot.style_cross](#var_plot.style_cross)[plot.style_columns](#var_plot.style_columns)[plot.style_circles](#var_plot.style_circles)

## plot.style_areabr

A named constant for the 'Area With Breaks' style, to be used as an argument for the `style` parameter in the [plot](#fun_plot) function. Similar to [plot.style_area](#var_plot.style_area), except the gaps in the data are not filled.

### Type

` const plot_style `

### See also

[plot](#fun_plot)[plot.style_steplinebr](#var_plot.style_steplinebr)[plot.style_line](#var_plot.style_line)[plot.style_linebr](#var_plot.style_linebr)[plot.style_stepline](#var_plot.style_stepline)[plot.style_stepline_diamond](#var_plot.style_stepline_diamond)[plot.style_histogram](#var_plot.style_histogram)[plot.style_cross](#var_plot.style_cross)[plot.style_area](#var_plot.style_area)[plot.style_columns](#var_plot.style_columns)[plot.style_circles](#var_plot.style_circles)

## plot.style_circles

A named constant for the 'Circles' style, to be used as an argument for the `style` parameter in the [plot](#fun_plot) function.

### Type

` const plot_style `

### See also

[plot](#fun_plot)[plot.style_steplinebr](#var_plot.style_steplinebr)[plot.style_line](#var_plot.style_line)[plot.style_linebr](#var_plot.style_linebr)[plot.style_stepline](#var_plot.style_stepline)[plot.style_stepline_diamond](#var_plot.style_stepline_diamond)[plot.style_histogram](#var_plot.style_histogram)[plot.style_cross](#var_plot.style_cross)[plot.style_area](#var_plot.style_area)[plot.style_areabr](#var_plot.style_areabr)[plot.style_columns](#var_plot.style_columns)

## plot.style_columns

A named constant for the 'Columns' style, to be used as an argument for the `style` parameter in the [plot](#fun_plot) function.

### Type

` const plot_style `

### See also

[plot](#fun_plot)[plot.style_steplinebr](#var_plot.style_steplinebr)[plot.style_line](#var_plot.style_line)[plot.style_linebr](#var_plot.style_linebr)[plot.style_stepline](#var_plot.style_stepline)[plot.style_stepline_diamond](#var_plot.style_stepline_diamond)[plot.style_histogram](#var_plot.style_histogram)[plot.style_cross](#var_plot.style_cross)[plot.style_area](#var_plot.style_area)[plot.style_areabr](#var_plot.style_areabr)[plot.style_circles](#var_plot.style_circles)

## plot.style_cross

A named constant for the 'Cross' style, to be used as an argument for the `style` parameter in the [plot](#fun_plot) function.

### Type

` const plot_style `

### See also

[plot](#fun_plot)[plot.style_steplinebr](#var_plot.style_steplinebr)[plot.style_line](#var_plot.style_line)[plot.style_linebr](#var_plot.style_linebr)[plot.style_stepline](#var_plot.style_stepline)[plot.style_stepline_diamond](#var_plot.style_stepline_diamond)[plot.style_histogram](#var_plot.style_histogram)[plot.style_area](#var_plot.style_area)[plot.style_areabr](#var_plot.style_areabr)[plot.style_columns](#var_plot.style_columns)[plot.style_circles](#var_plot.style_circles)

## plot.style_histogram

A named constant for the 'Histogram' style, to be used as an argument for the `style` parameter in the [plot](#fun_plot) function.

### Type

` const plot_style `

### See also

[plot](#fun_plot)[plot.style_steplinebr](#var_plot.style_steplinebr)[plot.style_line](#var_plot.style_line)[plot.style_linebr](#var_plot.style_linebr)[plot.style_stepline](#var_plot.style_stepline)[plot.style_stepline_diamond](#var_plot.style_stepline_diamond)[plot.style_cross](#var_plot.style_cross)[plot.style_area](#var_plot.style_area)[plot.style_areabr](#var_plot.style_areabr)[plot.style_columns](#var_plot.style_columns)[plot.style_circles](#var_plot.style_circles)

## plot.style_line

A named constant for the 'Line' style, to be used as an argument for the `style` parameter in the [plot](#fun_plot) function.

### Type

` const plot_style `

### See also

[plot](#fun_plot)[plot.style_steplinebr](#var_plot.style_steplinebr)[plot.style_linebr](#var_plot.style_linebr)[plot.style_stepline](#var_plot.style_stepline)[plot.style_stepline_diamond](#var_plot.style_stepline_diamond)[plot.style_histogram](#var_plot.style_histogram)[plot.style_cross](#var_plot.style_cross)[plot.style_area](#var_plot.style_area)[plot.style_areabr](#var_plot.style_areabr)[plot.style_columns](#var_plot.style_columns)[plot.style_circles](#var_plot.style_circles)

## plot.style_linebr

A named constant for the 'Line With Breaks' style, to be used as an argument for the `style` parameter in the [plot](#fun_plot) function. Similar to [plot.style_line](#var_plot.style_line), except the gaps in the data are not filled.

### Type

` const plot_style `

### See also

[plot](#fun_plot)[plot.style_steplinebr](#var_plot.style_steplinebr)[plot.style_line](#var_plot.style_line)[plot.style_stepline](#var_plot.style_stepline)[plot.style_stepline_diamond](#var_plot.style_stepline_diamond)[plot.style_histogram](#var_plot.style_histogram)[plot.style_cross](#var_plot.style_cross)[plot.style_area](#var_plot.style_area)[plot.style_areabr](#var_plot.style_areabr)[plot.style_columns](#var_plot.style_columns)[plot.style_circles](#var_plot.style_circles)

## plot.style_stepline

A named constant for the 'Step Line' style, to be used as an argument for the `style` parameter in the [plot](#fun_plot) function.

### Type

` const plot_style `

### See also

[plot](#fun_plot)[plot.style_line](#var_plot.style_line)[plot.style_steplinebr](#var_plot.style_steplinebr)[plot.style_stepline_diamond](#var_plot.style_stepline_diamond)[plot.style_linebr](#var_plot.style_linebr)[plot.style_histogram](#var_plot.style_histogram)[plot.style_cross](#var_plot.style_cross)[plot.style_area](#var_plot.style_area)[plot.style_areabr](#var_plot.style_areabr)[plot.style_columns](#var_plot.style_columns)[plot.style_circles](#var_plot.style_circles)

## plot.style_stepline_diamond

A named constant for the 'Step Line With Diamonds' style, to be used as an argument for the `style` parameter in the [plot](#fun_plot) function. Similar to [plot.style_stepline](#var_plot.style_stepline), except the data changes are also marked with the Diamond shapes.

### Type

` const plot_style `

### See also

[plot](#fun_plot)[plot.style_steplinebr](#var_plot.style_steplinebr)[plot.style_line](#var_plot.style_line)[plot.style_linebr](#var_plot.style_linebr)[plot.style_histogram](#var_plot.style_histogram)[plot.style_cross](#var_plot.style_cross)[plot.style_area](#var_plot.style_area)[plot.style_areabr](#var_plot.style_areabr)[plot.style_columns](#var_plot.style_columns)[plot.style_circles](#var_plot.style_circles)

## plot.style_steplinebr

A named constant for the 'Step line with Breaks' style, to be used as an argument for the `style` parameter in the [plot](#fun_plot) function.

### Type

` const plot_style `

### See also

[plot](#fun_plot)[plot.style_circles](#var_plot.style_circles)[plot.style_line](#var_plot.style_line)[plot.style_linebr](#var_plot.style_linebr)[plot.style_stepline](#var_plot.style_stepline)[plot.style_stepline_diamond](#var_plot.style_stepline_diamond)[plot.style_histogram](#var_plot.style_histogram)[plot.style_cross](#var_plot.style_cross)[plot.style_area](#var_plot.style_area)[plot.style_areabr](#var_plot.style_areabr)[plot.style_columns](#var_plot.style_columns)

## position.bottom_center

Table position is used in [table.new](#fun_table.new), [table.cell](#fun_table.cell) functions.

Binds the table to the bottom edge in the center.

### Type

` const string `

### See also

[table.new](#fun_table.new)[table.cell](#fun_table.cell)[table.set_position](#fun_table.set_position)[position.top_left](#var_position.top_left)[position.top_center](#var_position.top_center)[position.top_right](#var_position.top_right)[position.middle_left](#var_position.middle_left)[position.middle_center](#var_position.middle_center)[position.middle_right](#var_position.middle_right)[position.bottom_left](#var_position.bottom_left)

## position.bottom_left

Table position is used in [table.new](#fun_table.new), [table.cell](#fun_table.cell) functions.

Binds the table to the bottom left of the screen.

### Type

` const string `

### See also

[table.new](#fun_table.new)[table.cell](#fun_table.cell)[table.set_position](#fun_table.set_position)[position.top_left](#var_position.top_left)[position.top_center](#var_position.top_center)[position.top_right](#var_position.top_right)[position.middle_left](#var_position.middle_left)[position.middle_center](#var_position.middle_center)[position.middle_right](#var_position.middle_right)[position.bottom_center](#var_position.bottom_center)

## position.bottom_right

Table position is used in [table.new](#fun_table.new), [table.cell](#fun_table.cell) functions.

Binds the table to the bottom right of the screen.

### Type

` const string `

### See also

[table.new](#fun_table.new)[table.cell](#fun_table.cell)[table.set_position](#fun_table.set_position)[position.top_left](#var_position.top_left)[position.top_center](#var_position.top_center)[position.top_right](#var_position.top_right)[position.middle_left](#var_position.middle_left)[position.middle_center](#var_position.middle_center)[position.middle_right](#var_position.middle_right)[position.bottom_left](#var_position.bottom_left)[position.bottom_center](#var_position.bottom_center)

## position.middle_center

Table position is used in [table.new](#fun_table.new), [table.cell](#fun_table.cell) functions.

Binds the table to the center of the screen.

### Type

` const string `

### See also

[table.new](#fun_table.new)[table.cell](#fun_table.cell)[table.set_position](#fun_table.set_position)[position.top_left](#var_position.top_left)[position.top_center](#var_position.top_center)[position.top_right](#var_position.top_right)[position.middle_left](#var_position.middle_left)[position.middle_right](#var_position.middle_right)[position.bottom_left](#var_position.bottom_left)[position.bottom_center](#var_position.bottom_center)

## position.middle_left

Table position is used in [table.new](#fun_table.new), [table.cell](#fun_table.cell) functions.

Binds the table to the left side of the screen.

### Type

` const string `

### See also

[table.new](#fun_table.new)[table.cell](#fun_table.cell)[table.set_position](#fun_table.set_position)[position.top_left](#var_position.top_left)[position.top_center](#var_position.top_center)[position.top_right](#var_position.top_right)[position.middle_center](#var_position.middle_center)[position.middle_right](#var_position.middle_right)[position.bottom_left](#var_position.bottom_left)[position.bottom_center](#var_position.bottom_center)

## position.middle_right

Table position is used in [table.new](#fun_table.new), [table.cell](#fun_table.cell) functions.

Binds the table to the right side of the screen.

### Type

` const string `

### See also

[table.new](#fun_table.new)[table.cell](#fun_table.cell)[table.set_position](#fun_table.set_position)[position.top_left](#var_position.top_left)[position.top_center](#var_position.top_center)[position.top_right](#var_position.top_right)[position.middle_left](#var_position.middle_left)[position.middle_center](#var_position.middle_center)[position.bottom_left](#var_position.bottom_left)[position.bottom_center](#var_position.bottom_center)

## position.top_center

Table position is used in [table.new](#fun_table.new), [table.cell](#fun_table.cell) functions.

Binds the table to the top edge in the center.

### Type

` const string `

### See also

[table.new](#fun_table.new)[table.cell](#fun_table.cell)[table.set_position](#fun_table.set_position)[position.top_left](#var_position.top_left)[position.top_right](#var_position.top_right)[position.middle_left](#var_position.middle_left)[position.middle_center](#var_position.middle_center)[position.middle_right](#var_position.middle_right)[position.bottom_left](#var_position.bottom_left)[position.bottom_center](#var_position.bottom_center)

## position.top_left

Table position is used in [table.new](#fun_table.new), [table.cell](#fun_table.cell) functions.

Binds the table to the upper-left edge.

### Type

` const string `

### See also

[table.new](#fun_table.new)[table.cell](#fun_table.cell)[table.set_position](#fun_table.set_position)[position.top_center](#var_position.top_center)[position.top_right](#var_position.top_right)[position.middle_left](#var_position.middle_left)[position.middle_center](#var_position.middle_center)[position.middle_right](#var_position.middle_right)[position.bottom_left](#var_position.bottom_left)[position.bottom_center](#var_position.bottom_center)

## position.top_right

Table position is used in [table.new](#fun_table.new), [table.cell](#fun_table.cell) functions.

Binds the table to the upper-right edge.

### Type

` const string `

### See also

[table.new](#fun_table.new)[table.cell](#fun_table.cell)[table.set_position](#fun_table.set_position)[position.top_left](#var_position.top_left)[position.top_center](#var_position.top_center)[position.middle_left](#var_position.middle_left)[position.middle_center](#var_position.middle_center)[position.middle_right](#var_position.middle_right)[position.bottom_left](#var_position.bottom_left)[position.bottom_center](#var_position.bottom_center)

## scale.left

Scale value for [indicator](#fun_indicator) function. Indicator is added to the left price scale.

### Type

` const scale_type `

### See also

[indicator](#fun_indicator)

## scale.none

Scale value for [indicator](#fun_indicator) function. Indicator is added in 'No Scale' mode. Can be used only with 'overlay=true'.

### Type

` const scale_type `

### See also

[indicator](#fun_indicator)

## scale.right

Scale value for [indicator](#fun_indicator) function. Indicator is added to the right price scale.

### Type

` const scale_type `

### See also

[indicator](#fun_indicator)

## session.extended

Constant for extended session type (with extended hours data).

### Type

` const string `

### See also

[session.regular](#var_session.regular)[syminfo.session](#var_syminfo.session)

## session.regular

Constant for regular session type (no extended hours data).

### Type

` const string `

### See also

[session.extended](#var_session.extended)[syminfo.session](#var_syminfo.session)

## shape.arrowdown

Shape style for [plotshape](#fun_plotshape) function.

### Type

` const string `

### See also

[plotshape](#fun_plotshape)

## shape.arrowup

Shape style for [plotshape](#fun_plotshape) function.

### Type

` const string `

### See also

[plotshape](#fun_plotshape)

## shape.circle

Shape style for [plotshape](#fun_plotshape) function.

### Type

` const string `

### See also

[plotshape](#fun_plotshape)

## shape.cross

Shape style for [plotshape](#fun_plotshape) function.

### Type

` const string `

### See also

[plotshape](#fun_plotshape)

## shape.diamond

Shape style for [plotshape](#fun_plotshape) function.

### Type

` const string `

### See also

[plotshape](#fun_plotshape)

## shape.flag

Shape style for [plotshape](#fun_plotshape) function.

### Type

` const string `

### See also

[plotshape](#fun_plotshape)

## shape.labeldown

Shape style for [plotshape](#fun_plotshape) function.

### Type

` const string `

### See also

[plotshape](#fun_plotshape)

## shape.labelup

Shape style for [plotshape](#fun_plotshape) function.

### Type

` const string `

### See also

[plotshape](#fun_plotshape)

## shape.square

Shape style for [plotshape](#fun_plotshape) function.

### Type

` const string `

### See also

[plotshape](#fun_plotshape)

## shape.triangledown

Shape style for [plotshape](#fun_plotshape) function.

### Type

` const string `

### See also

[plotshape](#fun_plotshape)

## shape.triangleup

Shape style for [plotshape](#fun_plotshape) function.

### Type

` const string `

### See also

[plotshape](#fun_plotshape)

## shape.xcross

Shape style for [plotshape](#fun_plotshape) function.

### Type

` const string `

### See also

[plotshape](#fun_plotshape)

## size.auto

Size value for [plotshape](#fun_plotshape), [plotchar](#fun_plotchar) functions. The size of the shape automatically adapts to the size of the bars.

### Type

` const string `

### See also

[plotshape](#fun_plotshape)[plotchar](#fun_plotchar)[label.set_size](#fun_label.set_size)[size.tiny](#var_size.tiny)[size.small](#var_size.small)[size.normal](#var_size.normal)[size.large](#var_size.large)[size.huge](#var_size.huge)

## size.huge

Size value for [plotshape](#fun_plotshape), [plotchar](#fun_plotchar) functions. The size of the shape constantly huge.

### Type

` const string `

### See also

[plotshape](#fun_plotshape)[plotchar](#fun_plotchar)[label.set_size](#fun_label.set_size)[size.auto](#var_size.auto)[size.tiny](#var_size.tiny)[size.small](#var_size.small)[size.normal](#var_size.normal)[size.large](#var_size.large)

## size.large

Size value for [plotshape](#fun_plotshape), [plotchar](#fun_plotchar) functions. The size of the shape constantly large.

### Type

` const string `

### See also

[plotshape](#fun_plotshape)[plotchar](#fun_plotchar)[label.set_size](#fun_label.set_size)[size.auto](#var_size.auto)[size.tiny](#var_size.tiny)[size.small](#var_size.small)[size.normal](#var_size.normal)[size.huge](#var_size.huge)

## size.normal

Size value for [plotshape](#fun_plotshape), [plotchar](#fun_plotchar) functions. The size of the shape constantly normal.

### Type

` const string `

### See also

[plotshape](#fun_plotshape)[plotchar](#fun_plotchar)[label.set_size](#fun_label.set_size)[size.auto](#var_size.auto)[size.tiny](#var_size.tiny)[size.small](#var_size.small)[size.large](#var_size.large)[size.huge](#var_size.huge)

## size.small

Size value for [plotshape](#fun_plotshape), [plotchar](#fun_plotchar) functions. The size of the shape constantly small.

### Type

` const string `

### See also

[plotshape](#fun_plotshape)[plotchar](#fun_plotchar)[label.set_size](#fun_label.set_size)[size.auto](#var_size.auto)[size.tiny](#var_size.tiny)[size.normal](#var_size.normal)[size.large](#var_size.large)[size.huge](#var_size.huge)

## size.tiny

Size value for [plotshape](#fun_plotshape), [plotchar](#fun_plotchar) functions. The size of the shape constantly tiny.

### Type

` const string `

### See also

[plotshape](#fun_plotshape)[plotchar](#fun_plotchar)[label.set_size](#fun_label.set_size)[size.auto](#var_size.auto)[size.small](#var_size.small)[size.normal](#var_size.normal)[size.large](#var_size.large)[size.huge](#var_size.huge)

## splits.denominator

A named constant for the [request.splits](#fun_request.splits) function. Is used to request the denominator (the number below the line in a fraction) of a splits.

### Type

` const string `

### See also

[request.splits](#fun_request.splits)

## splits.numerator

A named constant for the [request.splits](#fun_request.splits) function. Is used to request the numerator (the number above the line in a fraction) of a splits.

### Type

` const string `

### See also

[request.splits](#fun_request.splits)

## strategy.cash

This is one of the arguments that can be supplied to the `default_qty_type` parameter in the [strategy](#fun_strategy) declaration statement. It is only relevant when no value is used for the 'qty' parameter in [strategy.entry](#fun_strategy.entry) or [strategy.order](#fun_strategy.order) function calls. It specifies that an amount of cash in the `strategy.account_currency` will be used to enter trades.

### Type

` const string `

### Example

```
//@version=5strategy("strategy.cash", overlay = true, default_qty_value = 50, default_qty_type = strategy.cash, initial_capital = 1000000)if bar_index == 0    // As ‘qty’ is not defined, the previously defined values for the `default_qty_type` and `default_qty_value` parameters are used to enter trades, namely 50 units of cash in the currency of `strategy.account_currency`.    // `qty` is calculated as (default_qty_value)/(close price). If current price is $5, then qty = 50/5 = 10\.    strategy.entry("EN", strategy.long)if bar_index == 2    strategy.close("EN")
```

### See also

[strategy](#fun_strategy)

## strategy.commission.cash_per_contract

Commission type for an order. Money displayed in the account currency per contract.

### Type

` const string `

### See also

[strategy](#fun_strategy)

## strategy.commission.cash_per_order

Commission type for an order. Money displayed in the account currency per order.

### Type

` const string `

### See also

[strategy](#fun_strategy)

## strategy.commission.percent

Commission type for an order. A percentage of the cash volume of order.

### Type

` const string `

### See also

[strategy](#fun_strategy)

## strategy.direction.all

It allows strategy to open both long and short positions.

### Type

` const string `

### See also

[strategy.risk.allow_entry_in](#fun_strategy.risk.allow_entry_in)

## strategy.direction.long

It allows strategy to open only long positions.

### Type

` const string `

### See also

[strategy.risk.allow_entry_in](#fun_strategy.risk.allow_entry_in)

## strategy.direction.short

It allows strategy to open only short positions.

### Type

` const string `

### See also

[strategy.risk.allow_entry_in](#fun_strategy.risk.allow_entry_in)

## strategy.fixed

This is one of the arguments that can be supplied to the `default_qty_type` parameter in the [strategy](#fun_strategy) declaration statement. It is only relevant when no value is used for the 'qty' parameter in [strategy.entry](#fun_strategy.entry) or [strategy.order](#fun_strategy.order) function calls. It specifies that a number of contracts/shares/lots will be used to enter trades.

### Type

` const string `

### Example

```
//@version=5strategy("strategy.fixed", overlay = true, default_qty_value = 50, default_qty_type = strategy.fixed, initial_capital = 1000000)if bar_index == 0    // As ‘qty’ is not defined, the previously defined values for the `default_qty_type` and `default_qty_value` parameters are used to enter trades, namely 50 contracts.    // qty = 50    strategy.entry("EN", strategy.long)if bar_index == 2    strategy.close("EN")
```

### See also

[strategy](#fun_strategy)

## strategy.oca.cancel

OCA type value for strategy's functions. The parameter determines that an order should belong to an OCO group, where as soon as an order is filled, all other orders of the same group are cancelled. Note: if more than 1 guaranteed-to-be-executed orders of the same OCA group are placed at once, all those orders are filled.

### Type

` const string `

### See also

[strategy.entry](#fun_strategy.entry)[strategy.exit](#fun_strategy.exit)[strategy.order](#fun_strategy.order)

## strategy.oca.none

OCA type value for strategy's functions. The parameter determines that an order should not belong to any particular OCO group.

### Type

` const string `

### See also

[strategy.entry](#fun_strategy.entry)[strategy.exit](#fun_strategy.exit)[strategy.order](#fun_strategy.order)

## strategy.oca.reduce

OCA type value for strategy's functions. The parameter determines that an order should belong to an OCO group, where if X number of contracts of an order is filled, number of contracts for each other order of the same OCO group is decreased by X. Note: if more than 1 guaranteed-to-be-executed orders of the same OCA group are placed at once, all those orders are filled.

### Type

` const string `

### See also

[strategy.entry](#fun_strategy.entry)[strategy.exit](#fun_strategy.exit)[strategy.order](#fun_strategy.order)

## strategy.percent_of_equity

This is one of the arguments that can be supplied to the `default_qty_type` parameter in the [strategy](#fun_strategy) declaration statement. It is only relevant when no value is used for the 'qty' parameter in [strategy.entry](#fun_strategy.entry) or [strategy.order](#fun_strategy.order) function calls. It specifies that a percentage (0-100) of equity will be used to enter trades.

### Type

` const string `

### Example

```
//@version=5strategy("strategy.percent_of_equity", overlay = false, default_qty_value = 100, default_qty_type = strategy.percent_of_equity, initial_capital = 1000000)// As ‘qty’ is not defined, the previously defined values for the `default_qty_type` and `default_qty_value` parameters are used to enter trades, namely 100% of available equity.if bar_index == 0    strategy.entry("EN", strategy.long)if bar_index == 2    strategy.close("EN")plot(strategy.equity) // The ‘qty’ parameter is set to 10\. Entering position with fixed size of 10 contracts and entry market price = (10 * close).if bar_index == 4    strategy.entry("EN", strategy.long, qty = 10)if bar_index == 6    strategy.close("EN")
```

### See also

[strategy](#fun_strategy)

## text.align_bottom

Vertical text alignment for [box.new](#fun_box.new), [box.set_text_valign](#fun_box.set_text_valign), [table.cell](#fun_table.cell) and [table.cell_set_text_valign](#fun_table.cell_set_text_valign) functions.

### Type

` const string `

### See also

[table.cell](#fun_table.cell)[table.cell_set_text_valign](#fun_table.cell_set_text_valign)[text.align_center](#var_text.align_center)[text.align_left](#var_text.align_left)[text.align_right](#var_text.align_right)

## text.align_center

Text alignment for [box.new](#fun_box.new), [box.set_text_halign](#fun_box.set_text_halign), [box.set_text_valign](#fun_box.set_text_valign), [label.new](#fun_label.new) and [label.set_textalign](#fun_label.set_textalign) functions.

### Type

` const string `

### See also

[label.new](#fun_label.new)[label.set_style](#fun_label.set_style)[text.align_left](#var_text.align_left)[text.align_right](#var_text.align_right)

## text.align_left

Horizontal text alignment for [box.new](#fun_box.new), [box.set_text_halign](#fun_box.set_text_halign), [label.new](#fun_label.new) and [label.set_textalign](#fun_label.set_textalign) functions.

### Type

` const string `

### See also

[label.new](#fun_label.new)[label.set_style](#fun_label.set_style)[text.align_center](#var_text.align_center)[text.align_right](#var_text.align_right)

## text.align_right

Horizontal text alignment for [box.new](#fun_box.new), [box.set_text_halign](#fun_box.set_text_halign), [label.new](#fun_label.new) and [label.set_textalign](#fun_label.set_textalign) functions.

### Type

` const string `

### See also

[label.new](#fun_label.new)[label.set_style](#fun_label.set_style)[text.align_center](#var_text.align_center)[text.align_left](#var_text.align_left)

## text.align_top

Vertical text alignment for [box.new](#fun_box.new), [box.set_text_valign](#fun_box.set_text_valign), [table.cell](#fun_table.cell) and [table.cell_set_text_valign](#fun_table.cell_set_text_valign) functions.

### Type

` const string `

### See also

[table.cell](#fun_table.cell)[table.cell_set_text_valign](#fun_table.cell_set_text_valign)[text.align_center](#var_text.align_center)[text.align_left](#var_text.align_left)[text.align_right](#var_text.align_right)

## text.wrap_auto

Automatic wrapping mode for [box.new](#fun_box.new) and [box.set_text_wrap](#fun_box.set_text_wrap) functions.

### Type

` const string `

### See also

[box.new](#fun_box.new)[box.set_text](#fun_box.set_text)[box.set_text_wrap](#fun_box.set_text_wrap)

## text.wrap_none

Disabled wrapping mode for [box.new](#fun_box.new) and [box.set_text_wrap](#fun_box.set_text_wrap) functions.

### Type

` const string `

### See also

[box.new](#fun_box.new)[box.set_text](#fun_box.set_text)[box.set_text_wrap](#fun_box.set_text_wrap)

## xloc.bar_index

A named constant that specifies the algorithm of interpretation of x-value in functions [line.new](#fun_line.new) and [label.new](#fun_label.new). If xloc = [xloc.bar_index](#var_xloc.bar_index), value of x is a bar index.

### Type

` const string `

### See also

[line.new](#fun_line.new)[label.new](#fun_label.new)[line.set_xloc](#fun_line.set_xloc)[label.set_xloc](#fun_label.set_xloc)[xloc.bar_time](#var_xloc.bar_time)

## xloc.bar_time

A named constant that specifies the algorithm of interpretation of x-value in functions [line.new](#fun_line.new) and [label.new](#fun_label.new). If xloc = [xloc.bar_time](#var_xloc.bar_time), value of x is a bar UNIX time.

### Type

` const string `

### See also

[line.new](#fun_line.new)[label.new](#fun_label.new)[line.set_xloc](#fun_line.set_xloc)[label.set_xloc](#fun_label.set_xloc)[xloc.bar_index](#var_xloc.bar_index)

## yloc.abovebar

A named constant that specifies the algorithm of interpretation of y-value in function [label.new](#fun_label.new).

### Type

` const string `

### See also

[label.new](#fun_label.new)[label.set_yloc](#fun_label.set_yloc)[yloc.price](#var_yloc.price)[yloc.belowbar](#var_yloc.belowbar)

## yloc.belowbar

A named constant that specifies the algorithm of interpretation of y-value in function [label.new](#fun_label.new).

### Type

` const string `

### See also

[label.new](#fun_label.new)[label.set_yloc](#fun_label.set_yloc)[yloc.price](#var_yloc.price)[yloc.abovebar](#var_yloc.abovebar)

## yloc.price

A named constant that specifies the algorithm of interpretation of y-value in function [label.new](#fun_label.new).

### Type

` const string `

### See also

[label.new](#fun_label.new)[label.set_yloc](#fun_label.set_yloc)[yloc.abovebar](#var_yloc.abovebar)[yloc.belowbar](#var_yloc.belowbar)

## Keywords

## and

Logical AND. Applicable to boolean expressions.

### Syntax

expr1 and expr2

### Returns

Boolean value, or series of boolean values.

## export

Used in libraries to prefix the declaration of functions or user-defined type definitions that will be available from other scripts importing the library.

### Example

```
//@version=5//@description Library of debugging functions.library("Debugging_library", overlay = true)//@function Displays a string as a table cell for debugging purposes.//@param txt String to display.//@returns Void.export print(string txt) =>     var table t = table.new(position.middle_right, 1, 1)    table.cell(t, 0, 0, txt, bgcolor = color.yellow)// Using the function from inside the library to show an example on the published chart.// This has no impact on scripts using the library.print("Library Test")
```

### Remarks

Each library must have at least one exported function or user-defined type (UDT).

Exported functions cannot use variables from the global scope if they are arrays, mutable variables (reassigned with `:=`), or variables of 'input' form.

Exported functions cannot use `request.*()` functions.

Exported functions must explicitly declare each parameter's type and all parameters must be used in the function's body. By default, all arguments passed to exported functions are of the [series](#op_series) form, unless they are explicitly specified as [simple](#op_simple) in the function's signature.

The @description, @function, @param, @type, @field, and @returns compiler annotations are used to automatically generate the library's description and release notes, and in the Pine Script™ Editor's tooltips.

### See also

[library](#fun_library)[import](#op_import)[simple](#op_simple)[series](#op_series)[type](#op_type)

## false

Literal representing a [bool](#op_bool) value, and result of a comparison operation.

### Remarks

See the User Manual for [comparison operators](https://www.tradingview.com/pine-script-docs/en/v5/language/Operators.html#comparison-operators) and [logical operators](https://www.tradingview.com/pine-script-docs/en/v5/language/Operators.html#logical-operators).

### See also

[bool](#op_bool)

## for

The 'for' structure allows the repeated execution of a number of statements:

### Syntax

[var_declaration =] for counter = from_num to to_num [by step_num] tements | continue | break urn_expression

**var_declaration** - An optional variable declaration that will be assigned the value of the loop's return_expression.

**counter** - A variable holding the value of the loop's counter, which is incremented/decremented by 1 or by the step_num value on each iteration of the loop.

**from_num** - The starting value of the counter. "series int/float" values/expressions are allowed.

**to_num** - The end value of the counter. When the counter becomes greater than to_num (or less than to_num in cases where from_num > to_num) the loop is broken. "series int/float" values/expressions are allowed, but they are evaluated only on the loop's first iteration.

**step_num** - The increment/decrement value of the counter. It is optional. The default value is +1 or -1, depending on which of from_num or to_num is the greatest. When a value is used, the counter is also incremented/decremented depending on which of from_num or to_num is the greatest, so the +/- sign of step_num is optional.

**statements | continue | break** - Any number of statements, or the 'continue' or 'break' keywords, indented by 4 spaces or a tab.

**return_expression** - The loop's return value which is assigned to the variable in var_declaration if one is present. If the loop exits because of a 'continue' or 'break' keyword, the loop's return value is that of the last variable assigned a value before the loop's exit.

**continue** - A keyword that can only be used in loops. It causes the next iteration of the loop to be executed.

**break** - A keyword that exits the loop.

### Example

```
//@version=5indicator("for")// Here, we count the quantity of bars in a given 'lookback' length which closed above the current bar's closeqtyOfHigherCloses(lookback) =>    int result = 0    for i = 1 to lookback        if close[i] > close            result += 1    resultplot(qtyOfHigherCloses(14))
```

### Example

```
//@version=5indicator("`for` loop with a step")a = array.from(0, 1, 2, 3, 4, 5, 6, 7, 8, 9)sum = 0.0for i = 0 to 9 by 5    // Because the step is set to 5, we are adding only the first (0) and the sixth (5) value from the array `a`.    sum += array.get(a, i)plot(sum)
```

### See also

[for...in](#op_for...in)[while](#op_while)

## for...in

The `for...in` structure allows the repeated execution of a number of statements for each element in an array. It can be used with either one argument: `array_element`, or with two: `\[index, array\_element\]`. The second form doesn't affect the functionality of the loop. It tracks the current iteration's index in the tuple's first variable.

### Syntax

[var_declaration =] for array_element in array_id tements | continue | break urn_expression

[var_declaration =] for [index, array_element] in array_id tements | continue | break urn_expression

**var_declaration** - An optional variable declaration that will be assigned the value of the loop's `return_expression`.

**index** - An optional variable that tracks the current iteration's index. Indexing starts at 0\. The variable is immutable in the loop's body. When used, it must be included in a tuple also containing `array_element`.

**array_element** - A variable containing each successive array element to be processed in the loop. The variable is immutable in the loop's body.

**array_id** - The ID of the array over which the loop is iterated.

**statements | continue | break** - Any number of statements, or the 'continue' or 'break' keywords, indented by 4 spaces or a tab.

**return_expression** - The loop's return value assigned to the variable in `var_declaration`, if one is present. If the loop exits because of a 'continue' or 'break' keyword, the loop's return value is that of the last variable assigned a value before the loop's exit.

**continue** - A keyword that can only be used in loops. It causes the next iteration of the loop to be executed.

**break** - A keyword that exits the loop.

It is allowed to modify the array's elements or its size inside the loop.

Here, we use the single-argument form of `for...in` to determine on each bar how many of the bar's OHLC values are greater than the SMA of 'close' values:

### Example

```
//@version=5indicator("for...in")// Here we determine on each bar how many of the bar's OHLC values are greater than the SMA of 'close' valuesfloat[] ohlcValues = array.from(open, high, low, close)qtyGreaterThan(value, array) =>    int result = 0    for currentElement in array        if currentElement > value            result += 1        resultplot(qtyGreaterThan(ta.sma(close, 20), ohlcValues))
```

Here, we use the two-argument form of [for...in](#op_for...in) to set the values of our `isPos` array to `true` when their corresponding value in our `valuesArray` array is positive:

### Example

```
//@version=5indicator("for...in")var valuesArray = array.from(4, -8, 11, 78, -16, 34, 7, 99, 0, 55)var isPos = array.new_bool(10, false)for [index, value] in valuesArray    if value > 0        array.set(isPos, index, true)if barstate.islastconfirmedhistory    label.new(bar_index, high, str.tostring(isPos))
```

Iterate through matrix rows as arrays.

### Example

```
//@version=5indicator("`for ... in` matrix Example")// Create a 2x3 matrix with values `4`.matrix1 = matrix.new<int>(2, 3, 4)sum = 0.0// Loop through every row of the matrix.for rowArray in matrix1    // Sum values of the every row     sum += array.sum(rowArray)plot(sum)
```

### See also

[for](#op_for)[while](#op_while)[array.sum](#fun_array.sum)[array.min](#fun_array.min)[array.max](#fun_array.max)

## if

If statement defines what block of statements must be executed when conditions of the expression are satisfied.

To have access to and use the if statement, one should specify the version >= 2 of Pine Script™ language in the very first line of code, for example: //@version=5

The 4th version of Pine Script™ Language allows you to use "else if" syntax.

General code form:

### Syntax

var_declarationX = if condition _decl_then0 _decl_then1 _decl_thenN else if [optional block] _decl_else0 _decl_else1 _decl_elseN else _decl_else0 _decl_else1 _decl_elseN urn_expression_else

where

**var_declarationX** -- this variable gets the value of the if statement

**condition** -- if the condition is true, the logic from the block 'then' (var_decl_then0, var_decl_then1, etc.) is used.

If the condition is false, the logic from the block 'else' (var_decl_else0, var_decl_else1, etc.) is used.

**return_expression_then**, **return_expression_else** -- the last expression from the block then or from the block else will return the final value of the statement. If declaration of the variable is in the end, its value will be the result.

The type of returning value of the if statement depends on return_expression_then and return_expression_else type (their types must match: it is not possible to return an integer value from then, while you have a string value in else block).

### Example

```
//@version=5indicator("if")// This code compilesx = if close > open    closeelse    open// This code doesn’t compile// y = if close > open//     close// else//     "open"plot(x)
```

It is possible to omit the `else` block. In this case if the condition is false, an "empty" value (na, false, or "") will be assigned to the var_declarationX variable:

### Example

```
//@version=5indicator("if")x = if close > open    close// If current close > current open, then x = close.// Otherwise the x = na.plot(x)
```

It is possible to use either multiple "else if" blocks or none at all. The blocks "then", "else if", "else" are shifted by four spaces:

### Example

```
//@version=5indicator("if")x = if open > close    5else if high > low    closeelse    openplot(x)
```

It is possible to ignore the resulting value of an `if` statement ("var_declarationX=" can be omitted). It may be useful if you need the side effect of the expression, for example in strategy trading:

### Example

```
//@version=5strategy("if")if (ta.crossover(high, low))    strategy.entry("BBandLE", strategy.long, stop=low, oca_name="BollingerBands", oca_type=strategy.oca.cancel, comment="BBandLE")else    strategy.cancel(id="BBandLE")
```

If statements can include each other:

### Example

```
//@version=5indicator("if")float x = naif close > open    if close > close[1]        x := close    else        x := close[1]else    x := openplot(x)
```

## import

Used to load an external [library](#fun_library) into a script and bind its functions to a namespace. The importing script can be an indicator, a strategy, or another library. A library must be published (privately or publicly) before it can be imported.

### Syntax

import {username}/{libraryName}/{libraryVersion} as {alias}

Arguments

username (literal string) User name of the library's author.

libraryName (literal string) Name of the imported library, which corresponds to the `title` argument used by the author in his library script.

libraryVersion (literal int) Version number of the imported library.

alias (literal string) Namespace used to refer to the library's functions. Optional. The default is the libraryName string.

### Example

```
//@version=5indicator("num_methods import")// Import the first version of the username’s "num_methods" library and assign it to the "m" namespace",import username/num_methods/1 as m// Call the “sinh()” function from the imported libraryy = m.sinh(3.14)// Plot value returned by the "sinh()" function",plot(y)
```

### Remarks

Using an alias that replaces a built-in namespace such as math. _or strategy._ is allowed, but if the library contains function names that shadow Pine Script™'s built-in functions, the built-ins will become unavailable. The same version of a library can only be imported once. Aliases must be distinct for each imported library. When calling library functions, casting their arguments to types other than their declared type is not allowed.

### See also

[library](#fun_library)[export](#op_export)

## method

This keyword is used to prefix a function declaration, indicating it can then be invoked using dot notation by appending its name to a variable of the type of its first parameter and omitting that first parameter. Alternatively, functions declared as methods can also be invoked like normal user-defined functions. In that case, an argument must be supplied for its first parameter.

The first parameter of a method declaration must be explicitly typified.

### Syntax

[export] method

<functionname>(<paramtype>
  <paramname> [= <defaultvalue>], …) =&gt;
          nctionBlock&gt;</defaultvalue></paramname>
</paramtype></functionname>

### Example

```
//@version=5indicator("")var prices = array.new<float>()//@function Pushes a new value into the array and removes the first one if the resulting array is greater than `maxSize`. Can be used as a method.method maintainArray(array<float> id, maxSize, value) =>    id.push(value)    if id.size() > maxSize        id.shift()prices.maintainArray(50, close)// The method can also be called like a function, without using dot notation.// In this case an argument must be supplied for its first parameter.// maintainArray(prices, 50, close)// This calls the `array.avg()` built-in using dot notation with the `prices` array.// It is possible because built-in functions belonging to some namespaces that are a special Pine type// can be invoked with method notation when the function's first parameter is an ID of that type.// Those namespaces are: `array`, `matrix`, `line`, `linefill`, `label`, `box`, and `table`.plot(prices.avg())
```

## not

Logical negation (NOT). Applicable to boolean expressions.

### Syntax

not expr1

### Returns

Boolean value, or series of boolean values.

## or

Logical OR. Applicable to boolean expressions.

### Syntax

expr1 or expr2

### Returns

Boolean value, or series of boolean values.

## switch

The switch operator transfers control to one of the several statements, depending on the values of a condition and expressions.

### Syntax

[variable_declaration = ] switch expression ue1 => local_block ue2 => local_block default_local_block

[variable_declaration = ] switch lean_expression1 => local_block lean_expression2 => local_block default_local_block

Switch with an expression:

### Example

```
//@version=5indicator("Switch using an expression")string i_maType = input.string("EMA", "MA type", options = ["EMA", "SMA", "RMA", "WMA"])float ma = switch i_maType    "EMA" => ta.ema(close, 10)    "SMA" => ta.sma(close, 10)    "RMA" => ta.rma(close, 10)    // Default used when the three first cases do not match.    => ta.wma(close, 10)plot(ma)
```

Switch without an expression:

### Example

```
//@version=5strategy("Switch without an expression", overlay = true)bool longCondition  = ta.crossover( ta.sma(close, 14), ta.sma(close, 28))bool shortCondition = ta.crossunder(ta.sma(close, 14), ta.sma(close, 28))switch    longCondition  => strategy.entry("Long ID", strategy.long)    shortCondition => strategy.entry("Short ID", strategy.short)
```

### Returns

The value of the last expression in the local block of statements that is executed.

### Remarks

Only one of the `local_block` instances or the `default_local_block` can be executed. The `default_local_block` is introduced with the `=>` token alone and is only executed when none of the preceding blocks are executed. If the result of the `switch` statement is assigned to a variable and a `default_local_block` is not specified, the statement returns `na` if no `local_block` is executed. When assigning the result of the `switch` statement to a variable, all `local_block` instances must return the same type of value.

### See also

[if](#op_if)[?:](#op_?:)

## true

Literal representing one of the values a [bool](#op_bool) variable can hold, or an expression can evaluate to when it uses comparison or logical operators.

### Remarks

See the User Manual for [comparison operators](https://www.tradingview.com/pine-script-docs/en/v5/language/Operators.html#comparison-operators) and [logical operators](https://www.tradingview.com/pine-script-docs/en/v5/language/Operators.html#logical-operators).

### See also

[bool](#op_bool)

## type

This keyword allows the declaration of user-defined types (UDT) from which scripts can instantiate objects. UDTs are composite types that contain an arbitrary number of fields of any built-in or user-defined type, including the defined UDT itself. The syntax to define a UDT is:

### Syntax

[export ]type

<udt_identifier>
          arip ]<field\_type>
  <field\_name> [= <value>]
             Once a UDT is defined, scripts can instantiate objects from it with the `UDT_identifier.new()` construct. When creating a new type instance, the fields of the resulting object will initialize with the default values from the UDT's definition. Any type fields without specified defaults will initialize as <a href="#var_na">na</a>. Alternatively, users can pass initial values as arguments in the <code>*.new()</code> method to override the type's defaults. For example, `newFooObject = foo.new(x = true)` assigns a new `foo` object to the `newFooObject` variable with its `x` field initialized using a value of <a href="#op_true">true</a>.</value></field\_name>
</field\_type></udt_identifier>

Field declarations can include the [varip](#op_varip) keyword, in which case the field values persist between successive script iterations on the same bar.

For more information see the User Manual's sections on [defining UDTs](https://www.tradingview.com/pine-script-docs/en/v5/language/Type_system.html#user-defined-types) and [using objects](https://www.tradingview.com/pine-script-docs/en/v5/language/Objects.html).

Libraries can export UDTs. See the[Libraries](https://www.tradingview.com/pine-script-docs/en/v5/concepts/Libraries.html#user-defined-types-and-objects) page of our User Manual to learn more.

### Example

```
//@version=5indicator("Multi Time Period Chart", overlay = true)timeframeInput = input.timeframe("1D")type bar    float o = open    float h = high    float l = low    float c = close    int   t = timedrawBox(bar b, right) =>    bar s = bar.new()    color boxColor = b.c >= b.o ? color.green : color.red    box.new(b.t, b.h, right, b.l, boxColor, xloc = xloc.bar_time, bgcolor = color.new(boxColor, 90))updateBox(box boxId, bar b) =>    color boxColor = b.c >= b.o ? color.green : color.red    box.set_border_color(boxId, boxColor)    box.set_bgcolor(boxId, color.new(boxColor, 90))    box.set_top(boxId, b.h)    box.set_bottom(boxId, b.l)    box.set_right(boxId, time)secBar = request.security(syminfo.tickerid, timeframeInput, bar.new())if not na(secBar)    // To avoid a runtime error, only process data when an object exists.    if not barstate.islast        if timeframe.change(timeframeInput)            // On historical bars, draw a new box in the past when the HTF closes.            drawBox(secBar, time[1])    else        var box lastBox = na        if na(lastBox) or timeframe.change(timeframeInput)            // On the last bar, only draw a new current box the first time we get there or when HTF changes.            lastBox := drawBox(secBar, time)        else            // On other chart updates, use setters to modify the current box.            updateBox(lastBox, secBar)
```

## var

**var** is the keyword used for assigning and one-time initializing of the variable.

Normally, a syntax of assignment of variables, which doesn't include the keyword var, results in the value of the variable being overwritten with every update of the data. Contrary to that, when assigning variables with the keyword var, they can "keep the state" despite the data updating, only changing it when conditions within if-expressions are met.

### Syntax

var variable_name = expression

where:

**variable_name** - any name of the user's variable that's allowed in Pine Script™ (can contain capital and lowercase Latin characters, numbers, and underscores (_), but can't start with a number).

**expression** - any arithmetic expression, just as with defining a regular variable. The expression will be calculated and assigned to a variable once.

### Example

```
//@version=5indicator("Var keyword example")var a = closevar b = 0.0var c = 0.0var green_bars_count = 0if close > open    var x = close    b := x    green_bars_count := green_bars_count + 1    if green_bars_count >= 10        var y = close        c := yplot(a)plot(b)plot(c)
```

The variable 'a' keeps the closing price of the first bar for each bar in the series.

The variable 'b' keeps the closing price of the first "green" bar in the series.

The variable 'c' keeps the closing price of the tenth "green" bar in the series.

## varip

**varip** (var intrabar persist) is the keyword used for the assignment and one-time initialization of a variable or a field of a user-defined [type](#op_type). It's similar to the [var](#op_var) keyword, but variables and fields declared with [varip](#op_varip) retain their values between executions of the script on the same bar.

### Syntax

varip [

<variable\_type> ]<variable\_name> = <expression>
</expression></variable\_name></variable\_type>

[export ]type

<udt_identifier>
          ip <field\_type>
  <field\_name> [= <value>]</value></field\_name>
</field\_type></udt_identifier>

where:

**variable_type** - An optional fundamental type ([int](#op_int), [float](#op_float), [bool](#op_bool), [color](#op_color), [string](#op_string)) or a user-defined type, or an array or matrix of one of those types. Special types are not compatible with this keyword.

**variable_name** - A [valid identifier](https://www.tradingview.com/pine-script-docs/en/v5/language/Identifiers.html). The variable can also be an object created from a UDT.

**expression** - Any arithmetic expression, just as when defining a regular variable. The expression will be calculated and assigned to the variable only once, on the first bar.

**UDT_identifier, field_type, field_name, value** - Constructs related to user-defined types as described in the [type](#op_type) section.

### Example

```
//@version=5indicator("varip")varip int v = -1v := v + 1plot(v)
```

With [var](#op_var), `v` would equal the value of the [bar_index](#var_bar_index). On historical bars, where the script calculates only once per chart bar, the value of `v` is the same as with [var](#op_var). However, on realtime bars, the script will evaluate the expression on each new chart update, producing a different result.

### Example

```
//@version=5indicator("varip with types")type barData    int index = -1    varip int ticks = -1var currBar = barData.new()currBar.index += 1currBar.ticks += 1// Will be equal to bar_index on all barsplot(currBar.index)// In real time, will increment per every tick on the chartplot(currBar.ticks)
```

The same [+=](#op_+=) operation applied to both the `index` and `ticks` fields results in different real-time values because `ticks` increases on every chart update, while `index` only does so once per bar. Note how the `currBar` object does not use the [varip](#op_varip) keyword. The `ticks` field of the object can increment on every tick, but the reference itself is defined once and then stays unchanged. If we were to declare `currBar` using [varip](#op_varip), the behavior of `index` would remain unchanged because while the reference to the type instance would persist between chart updates, the `index` field of the object would not.

### Remarks

When using [varip](#op_varip) to declare variables in strategies that may execute more than once per historical chart bar, the values of such variables are preserved across successive iterations of the script on the same bar.

The effect of [varip](#op_varip) eliminates the [rollback](https://www.tradingview.com/pine-script-docs/en/v5/language/Execution_model.html#calculation-based-on-realtime-bars) of variables before each successive execution of a script on the same bar.

## while

The `while` statement allows the conditional iteration of a local code block.

### Syntax

variable_declaration = while boolean_expression tinue ak urn_expression

where:

**variable_declaration** - An optional variable declaration. The `return expression` can provide the initialization value for this variable.

**boolean_expression** - when true, the local block of the `while` statement is executed. When false, execution of the script resumes after the `while` statement.

**continue** - The `continue` keyword causes the loop to branch to its next iteration.

**break** - The `break` keyword causes the loop to terminate. The script's execution resumes after the `while` statement.

**return_expression** - An optional line providing the `while` statement's returning value.

### Example

```
//@version=5indicator("while")// This is a simple example of calculating a factorial using a while loop.int i_n = input.int(10, "Factorial Size", minval=0)int counter   = i_nint factorial = 1while counter > 0    factorial := factorial * counter    counter   := counter - 1plot(factorial)
```

### Remarks

The local code block after the initial `while` line must be indented with four spaces or a tab. For the `while` loop to terminate, the boolean expression following `while` must eventually become false, or a `break` must be executed.

## Types

## array

Keyword used to explicitly declare the "array" type of a variable or a parameter. Array objects (or IDs) can be created with the [array.new

<type>
</type>](#fun_array.new<type)

, [array.from](#fun_array.from) function.

### Example

```
//@version=5indicator("array", overlay=true)array<float> a = naa := array.new<float>(1, close)plot(array.get(a, 0))
```

### Remarks

Array objects are always of "series" form.

### See also

[var](#op_var)[line](#op_line)[label](#op_label)[table](#op_table)[box](#op_box)[array.new

<type>
</type>](#fun_array.new<type)

[array.from](#fun_array.from)

## bool

Keyword used to explicitly declare the "bool" (boolean) type of a variable or a parameter. "Bool" variables can have values [true](#op_true), [false](#op_false) or [na](#var_na).

### Example

```
//@version=5indicator("bool")bool b = true    // Same as `b = true`b := naplot(b ? open : close)
```

### Remarks

Explicitly mentioning the type in a variable declaration is optional, except when it is initialized with [na](#var_na). Learn more about Pine Script™ types in the User Manual page on the [Type System](https://www.tradingview.com/pine-script-docs/en/v5/language/Type_system.html).

### See also

[var](#op_var)[varip](#op_varip)[int](#op_int)[float](#op_float)[color](#op_color)[string](#op_string)[true](#op_true)[false](#op_false)

## box

Keyword used to explicitly declare the "box" type of a variable or a parameter. Box objects (or IDs) can be created with the [box.new](#fun_box.new) function.

### Example

```
//@version=5indicator("box")// Empty `box1` box ID.var box box1 = na// `box` type is unnecessary because `box.new()` returns a "box" type.var box2 = box.new(na, na, na, na)box3 = box.new(time, open, time + 60 * 60 * 24, close, xloc=xloc.bar_time)
```

### Remarks

Box objects are always of "series" form.

### See also

[var](#op_var)[line](#op_line)[label](#op_label)[table](#op_table)[box.new](#fun_box.new)

## chart.point

Keyword to explicitly declare the type of a variable or parameter as `chart.point`. Scripts can produce `chart.point` instances using the [chart.point.from_time](#fun_chart.point.from_time), [chart.point.from_index](#fun_chart.point.from_index), and [chart.point.now](#fun_chart.point.now) functions.

Fields

index (series int) The x-coordinate of the point, expressed as a bar index value.

time (series float) The x-coordinate of the point, expressed as a UNIX time value.

price (series float) The y-coordinate of the point.

## color

Keyword used to explicitly declare the "color" type of a variable or a parameter.

### Example

```
//@version=5indicator("color", overlay = true)color textColor = color.green   color labelColor = #FF000080  // Red color (FF0000) with 50% transparency (80 which is half of FF).if barstate.islastconfirmedhistory    label.new(bar_index, high, text = "Label", color = labelColor, textcolor = textColor)// When declaring variables with color literals, built-in constants(color.green) or functions (color.new(), color.rgb()), the "color" keyword for the type can be omitted.c = color.rgb(0,255,0,0)plot(close, color = c)
```

### Remarks

Color literals have the following format: #RRGGBB or #RRGGBBAA. The letter pairs represent 00 to FF hexadecimal values (0 to 255 in decimal) where RR, GG and BB pairs are the values for the color's red, green and blue components. AA is an optional value for the color's transparency (or alpha component) where 00 is invisible and FF opaque. When no AA pair is supplied, FF is used. The hexadecimal letters can be upper or lower case.

Explicitly mentioning the type in a variable declaration is optional, except when it is initialized with [na](#var_na). Learn more about Pine Script™ types in the User Manual page on the [Type System](https://www.tradingview.com/pine-script-docs/en/v5/language/Type_system.html).

### See also

[var](#op_var)[varip](#op_varip)[int](#op_int)[float](#op_float)[string](#op_string)[color.rgb](#fun_color.rgb)[color.new](#fun_color.new)

## float

Keyword used to explicitly declare the "float" (floating point) type of a variable or a parameter.

### Example

```
//@version=5indicator("float")float f = 3.14    // Same as `f = 3.14`f := naplot(f)
```

### Remarks

Explicitly mentioning the type in a variable declaration is optional, except when it is initialized with [na](#var_na). Learn more about Pine Script™ types in the User Manual page on the [Type System](https://www.tradingview.com/pine-script-docs/en/v5/language/Type_system.html).

### See also

[var](#op_var)[varip](#op_varip)[int](#op_int)[bool](#op_bool)[color](#op_color)[string](#op_string)

## int

Keyword used to explicitly declare the "int" (integer) type of a variable or a parameter.

### Example

```
//@version=5indicator("int")int i = 14    // Same as `i = 14`i := naplot(i)
```

### Remarks

Explicitly mentioning the type in a variable declaration is optional, except when it is initialized with [na](#var_na). Learn more about Pine Script™ types in the User Manual page on the [Type System](https://www.tradingview.com/pine-script-docs/en/v5/language/Type_system.html).

### See also

[var](#op_var)[varip](#op_varip)[float](#op_float)[bool](#op_bool)[color](#op_color)[string](#op_string)

## label

Keyword used to explicitly declare the "label" type of a variable or a parameter. Label objects (or IDs) can be created with the [label.new](#fun_label.new) function.

### Example

```
//@version=5indicator("label")// Empty `label1` label ID.var label label1 = na// `label` type is unnecessary because `label.new()` returns "label" type.var label2 = label.new(na, na, na)if barstate.islastconfirmedhistory    label3 = label.new(bar_index, high, text = "label3 text")
```

### Remarks

Label objects are always of "series" form.

### See also

[var](#op_var)[line](#op_line)[box](#op_box)[label.new](#fun_label.new)

## line

Keyword used to explicitly declare the "line" type of a variable or a parameter. Line objects (or IDs) can be created with the [line.new](#fun_line.new) function.

### Example

```
//@version=5indicator("line")// Empty `line1` line ID.var line line1 = na// `line` type is unnecessary because `line.new()` returns "line" type.var line2 = line.new(na, na, na, na)line3 = line.new(bar_index - 1, high, bar_index, high, extend = extend.right)
```

### Remarks

Line objects are always of "series" form.

### See also

[var](#op_var)[label](#op_label)[box](#op_box)[line.new](#fun_line.new)

## linefill

Keyword used to explicitly declare the "linefill" type of a variable or a parameter. Linefill objects (or IDs) can be created with the [linefill.new](#fun_linefill.new) function.

### Example

```
//@version=5indicator("linefill", overlay=true)// Empty `linefill1` line ID.var linefill linefill1 = na// `linefill` type is unnecessary because `linefill.new()` returns "linefill" type.var linefill2 = linefill.new(na, na, na)if barstate.islastconfirmedhistory    line1 = line.new(bar_index - 10, high+1, bar_index, high+1, extend = extend.right)    line2 = line.new(bar_index - 10, low+1, bar_index, low+1, extend = extend.right)    linefill3 = linefill.new(line1, line2, color = color.new(color.green, 80))
```

### Remarks

Linefill objects are always of "series" form.

### See also

[var](#op_var)[line](#op_line)[label](#op_label)[table](#op_table)[box](#op_box)[linefill.new](#fun_linefill.new)

## map

Keyword used to explicitly declare the "map" type of a variable or a parameter. Map objects (or IDs) can be created with the [map.new

<type,type>
</type,type>](#fun_map.new<type,type)

 function.

### Example

```
//@version=5indicator("map", overlay=true)map<int, float> a = naa := map.new<int, float>()a.put(bar_index, close)label.new(bar_index, a.get(bar_index), "Current close")
```

### Remarks

Map objects are always of [series](https://www.tradingview.com/pine-script-docs/en/v5/language/Type_system.html#series) form.

### See also

[map.new

<type,type>
</type,type>](#fun_map.new<type,type)

## matrix

Keyword used to explicitly declare the "matrix" type of a variable or a parameter. Matrix objects (or IDs) can be created with the [matrix.new

<type>
</type>](#fun_matrix.new<type)

 function.

### Example

```
//@version=5indicator("matrix example")// Create `m1` matrix of `int` type.matrix<int> m1 = matrix.new<int>(2, 3, 0)// `matrix<int>` is unnecessary because the `matrix.new<int>()` function returns an `int` type matrix object.m2 = matrix.new<int>(2, 3, 0)// Display matrix using a label.if barstate.islastconfirmedhistory    label.new(bar_index, high, str.tostring(m2))
```

### Remarks

Matrix objects are always of "series" form.

### See also

[var](#op_var)[matrix.new

<type>
</type>](#fun_matrix.new<type)

[array](#op_array)

## series

**series** is a keyword that can be used in a library's exported functions to specify the type form required for a function's arguments. Explicit use of the `series` keyword is usually unnecessary because all arguments of exported functions are automatically converted to the "series" form by default.

### Syntax

export

<functionname>([[series] <type>] <arg1>[ = <default_value>])</default_value></arg1></type></functionname>

### Example

```
//@version=5//@description Library of debugging functions.library("Debugging_library", overlay = true)export smaCustom(series float source, series int length) =>    ta.sma(source, length)
```

## simple

**simple** is a keyword that can be used in a library's exported functions to specify the type form required for a function's arguments. By default, all arguments of exported functions are automatically converted into the "series" type form. In some cases, this would make arguments unusable with those of built-in functions that do not support the "series" form. For these cases, the `simple` keyword can be used instead.

### Syntax

export

<functionname>([[simple] <type>] <arg1>[ = <default_value>])</default_value></arg1></type></functionname>

### Example

```
//@version=5//@description Library of debugging functions.library("Debugging_library", overlay = true)export emaWrong(float source, int length) =>    // By default, both `source` and `length` will expect values of the `series` type form: `series float` for `source`, `series int` for `length`.    // This function will not compile because `ema()` does not support a "series int" argument for `length`. A "simple int" is required.    ta.ema(source, length)export emaRight(float source, simple int length) =>    // This function requires an argument of "simple int" type for its `length` parameter.    ta.ema(source, length)
```

## string

Keyword used to explicitly declare the "string" type of a variable or a parameter.

### Example

```
//@version=5indicator("string")string s = "Hello World!"    // Same as `s = "Hello world!"`// string s = na // same as "" plot(na, title=s)
```

### Remarks

Explicitly mentioning the type in a variable declaration is optional, except when it is initialized with [na](#var_na). Learn more about Pine Script™ types in the User Manual page on the [Type System](https://www.tradingview.com/pine-script-docs/en/v5/language/Type_system.html).

### See also

[var](#op_var)[varip](#op_varip)[int](#op_int)[float](#op_float)[bool](#op_bool)[str.tostring](#fun_str.tostring)[str.format](#fun_str.format)

## table

Keyword used to explicitly declare the "table" type of a variable or a parameter. Table objects (or IDs) can be created with the [table.new](#fun_table.new) function.

### Example

```
//@version=5indicator("table")// Empty `table1` table ID.var table table1 = na// `table` type is unnecessary because `table.new()` returns "table" type.var table2 = table.new(position.top_left, na, na)if barstate.islastconfirmedhistory    var table3 = table.new(position = position.top_right, columns = 1, rows = 1, bgcolor = color.yellow, border_width = 1)    table.cell(table_id = table3, column = 0, row = 0, text = "table3 text")
```

### Remarks

Table objects are always of "series" form.

### See also

[var](#op_var)[line](#op_line)[label](#op_label)[box](#op_box)[table.new](#fun_table.new)

## Operators

## -

Subtraction or unary minus. Applicable to numerical expressions.

### Syntax

expr1 - expr2

### Returns

Returns integer or float value, or series of values:

Binary `-` returns expr1 minus expr2.

Unary `-` returns the negation of expr.

### Remarks

You may use arithmetic operators with numbers as well as with series variables. In case of usage with series the operators are applied elementwise.

## -=

Subtraction assignment. Applicable to numerical expressions.

### Syntax

expr1 -= expr2

### Example

```
//@version=5indicator("-=")// Equals to expr1 = expr1 - expr2.a = 2b = 3a -= b// Result: a = -1.plot(a)
```

### Returns

Integer or float value, or series of values.

## !=

Not equal to. Applicable to expressions of any type.

### Syntax

expr1 != expr2

### Returns

Boolean value, or series of boolean values.

## ?:

Ternary conditional operator.

### Syntax

expr1 ? expr2 : expr3

### Example

```
//@version=5indicator("?:")// Draw circles at the bars where open crosses closes2 = ta.cross(open, close) ? math.avg(open,close) : naplot(s2, style=plot.style_circles, linewidth=2, color=color.red)// Combination of ?: operators for 'switch'-like logicc = timeframe.isintraday ? color.red : timeframe.isdaily ? color.green : timeframe.isweekly ? color.blue : color.grayplot(hl2, color=c)
```

### Returns

expr2 if expr1 is evaluated to true, expr3 otherwise. Zero value (0 and also NaN, +Infinity, -Infinity) is considered to be false, any other value is true.

### Remarks

Use [na](#var_na) for 'else' branch if you do not need it.

You can combine two or more [?:](#op_?:) operators to achieve the equivalent of a 'switch'-like statement (see examples above).

You may use arithmetic operators with numbers as well as with series variables. In case of usage with series the operators are applied elementwise.

### See also

[na](#var_na)

## []

Series subscript. Provides access to previous values of series expr1\. expr2 is the number of bars back, and must be numerical. Floats will be rounded down.

### Syntax

expr1[expr2]

### Example

```
//@version=5indicator("[]")// [] can be used to "save" variable value between barsa = 0.0 // declare `a`a := a[1] // immediately set current value to the same as previous. `na` in the beginning of historyif high == low // if some condition - change `a` value to another    a := lowplot(a)
```

### Returns

A series of values.

### See also

[math.floor](#fun_math.floor)

## *

Multiplication. Applicable to numerical expressions.

### Syntax

expr1 * expr2

### Returns

Integer or float value, or series of values.

## *=

Multiplication assignment. Applicable to numerical expressions.

### Syntax

expr1 *= expr2

### Example

```
//@version=5indicator("*=")// Equals to expr1 = expr1 * expr2.a = 2b = 3a *= b// Result: a = 6.plot(a)
```

### Returns

Integer or float value, or series of values.

## /

Division. Applicable to numerical expressions.

### Syntax

expr1 / expr2

### Returns

Integer or float value, or series of values.

## /=

Division assignment. Applicable to numerical expressions.

### Syntax

expr1 /= expr2

### Example

```
//@version=5indicator("/=")// Equals to expr1 = expr1 / expr2.a = 3b = 3a /= b// Result: a = 1.plot(a)
```

### Returns

Integer or float value, or series of values.

## %

Modulo (integer remainder). Applicable to numerical expressions.

### Syntax

expr1 % expr2

### Returns

Integer or float value, or series of values.

### Remarks

In Pine Script™, when the integer remainder is calculated, the quotient is truncated, i.e. rounded towards the lowest absolute value. The resulting value will have the same sign as the dividend.

Example: -1 % 9 = -1 - 9 _truncate(-1/9) = -1 - 9_ truncate(-0.111) = -1 - 9 * 0 = -1.

## %=

Modulo assignment. Applicable to numerical expressions.

### Syntax

expr1 %= expr2

### Example

```
//@version=5indicator("%=")// Equals to expr1 = expr1 % expr2.a = 3b = 3a %= b// Result: a = 0.plot(a)
```

### Returns

Integer or float value, or series of values.

## +

Addition or unary plus. Applicable to numerical expressions or strings.

### Syntax

expr1 + expr2

### Returns

Binary `+` for strings returns concatenation of expr1 and expr2

For numbers returns integer or float value, or series of values:

Binary `+` returns expr1 plus expr2.

Unary `+` returns expr (does nothing added just for the symmetry with the unary - operator).

### Remarks

You may use arithmetic operators with numbers as well as with series variables. In case of usage with series the operators are applied elementwise.

## +=

Addition assignment. Applicable to numerical expressions or strings.

### Syntax

expr1 += expr2

### Example

```
//@version=5indicator("+=")// Equals to expr1 = expr1 + expr2.a = 2b = 3a += b// Result: a = 5.plot(a)
```

### Returns

For strings returns concatenation of expr1 and expr2\. For numbers returns integer or float value, or series of values.

### Remarks

You may use arithmetic operators with numbers as well as with series variables. In case of usage with series the operators are applied elementwise.

## <

Less than. Applicable to numerical expressions.

### Syntax

expr1 < expr2

### Returns

Boolean value, or series of boolean values.

## <=

Less than or equal to. Applicable to numerical expressions.

### Syntax

expr1 <= expr2

### Returns

Boolean value, or series of boolean values.

## ==

Equal to. Applicable to expressions of any type.

### Syntax

expr1 == expr2

### Returns

Boolean value, or series of boolean values.

## =>

The '=>' operator is used in user-defined function declarations and in [switch](#op_switch) statements.

The function declaration syntax is:

### Syntax

<identifier>([<parameter\_name>[=<default\_value>]], ...) =&gt;
          cal_block&gt;
          nction_result&gt;</default\_value></parameter\_name></identifier>

A

<local_block> is zero or more Pine Script™ statements.</local_block>

The

<function_result> is a variable, an expression, or a tuple.</function_result>

### Example

```
//@version=5indicator("=>")// single-line functionf1(x, y) => x + y// multi-line functionf2(x, y) =>     sum = x + y    sumChange = ta.change(sum, 10)    // Function automatically returns the last expression used in itplot(f1(30, 8) + f2(1, 3))
```

### Remarks

You can learn more about user-defined functions in the User Manual's pages on [Declaring functions](https://www.tradingview.com/pine-script-docs/en/v5/language/User-defined_functions.html) and [Libraries](https://www.tradingview.com/pine-script-docs/en/v5/concepts/Libraries.html).

## >

Greater than. Applicable to numerical expressions.

### Syntax

expr1 > expr2

### Returns

Boolean value, or series of boolean values.

## >=

Greater than or equal to. Applicable to numerical expressions.

### Syntax

expr1 >= expr2

### Returns

Boolean value, or series of boolean values.
