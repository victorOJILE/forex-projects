# Detect trend or bias

## Bullish scenario
Check previous day (PD) if:
- current (current candle or daily candle) closed higher than PD "high" - 50%
- current closed higher than PD "close" - 25%
- diff between the current day "open" and "high" is greater than "open" and "low" - 25%

• If current and PD is <= 25%, add both together.

A result >= 50% gives us a bias

# Get untested swings OB data
```
// save UNTESTED buy-side LQ swings OB data
let buySideLQ = [
 high: ...,
 OBZoneLowestPrice: ...
];

// save untested sell-side LQ swings OB data
let sellSideLQ = [
 low: ...,
 OBZoneHighestPrice: ...
];
```

# Check for entry signal
Check the 1H TF for LQ sweep, 30M TF for most recent OB (zone) test
On the 15M/5M TF, look for a hammer / engulfing candles / check the slope of the HLC/3 values, of candles after LQ sweep for a change from < 0 to >= 0
Enter when one of these is true

