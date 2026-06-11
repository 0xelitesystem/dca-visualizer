# DCA Visualizer

Compare deploying a fixed amount of capital all at once against spreading it across several months, on a price path you control. The tool runs entirely in your browser, computes both outcomes side by side, and charts the price path with each dollar-cost-averaging buy marked. Nothing is sent anywhere.

**Live demo:** https://0xelitesystem.github.io/dca-visualizer/

**Not financial advice.** The price paths here are deterministic illustrations, not forecasts. Real markets do not follow these curves. This is a teaching tool for understanding the mechanics of lump sum versus DCA, not a basis for any investment decision.

## What it does

The DCA Visualizer answers one question: given a chosen price path, would lump-sum deployment or dollar-cost averaging have ended ahead, and by how much. It builds the price path from your inputs, simulates both strategies month by month, and reports the final value of each plus the difference in dollars and percent.

Lump sum buys every unit at the month-0 price. Dollar-cost averaging splits the capital into equal monthly tranches, buys at each month's price, and earns an optional cash yield on the balance still waiting to be deployed.

## How to use it

1. Open `index.html` in any modern browser, or visit the GitHub Pages site.
2. Enter total capital, the number of months to spread over, the starting unit price, an annual drift, and a cash yield for idle funds.
3. Pick a path shape: steady climb, early dip, late pullback, or choppy sideways.
4. Read the two final values and the verdict line. Adjust any input to see the outcome change live.

## Inputs and outputs

| Input | Meaning |
| --- | --- |
| Total capital | The full amount deployed under both strategies |
| Spread over (months) | How many monthly tranches DCA uses |
| Starting unit price | Price at month 0 |
| Annual drift | The yearly trend baked into the path before the shape is applied |
| Cash yield | Annual rate earned on capital still waiting in the DCA strategy |
| Path shape | A deterministic curve applied on top of the drift |

Outputs are the lump-sum final value, the DCA final value, units acquired by each, and which strategy finished ahead.

## Method and assumptions

The path is `startingPrice * (1 + monthlyDrift)^month`, multiplied by a deterministic shape factor. DCA invests `capital / months` each month at that month's price, with idle cash compounding at the monthly cash rate. Final value is measured at the end of the deployment window. There are no fees, taxes, or dividends. The model is intentionally simple so the lump-versus-DCA mechanic is visible rather than buried.

## Privacy

Runs fully client side. No analytics, no network calls, no storage. View source to confirm.

## Related tools

- [position-sizing-calculator](https://github.com/0xelitesystem/position-sizing-calculator)
- [breakeven-runway-calculator](https://github.com/0xelitesystem/breakeven-runway-calculator)
- [dividend-compounding-calculator](https://github.com/0xelitesystem/dividend-compounding-calculator)

## License

MIT. Copyright 0xelitesystem 2026.
