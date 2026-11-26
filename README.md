# Price change tracker

A static, browser-only metrics dashboard using synthetic demo data. No business records, file uploads or database connections are included.

## Explore the dashboard

- Opens with the last completed calendar month (Asia/Kolkata timezone), with synthetic charts already populated. Choose any date range or use **Last completed month** to return.
- Compact filters and metric choices are always visible.
- Choose daily or weekly aggregation.
- Open a dimension menu, search/select values, then click **Apply filters**. Active filters appear as badges.
- Enable comparison, add control rules, and click **Apply control**. Rules use AND across dimensions and OR across values; comparison is the remaining filtered population.
- Switch between activity metrics and take rates/fees, with Overall, Variable and Per Order FVF.
- Set an optional price-change date, choose fitted/zero/indexed axes with rounded ticks and adaptive YoY scales, and hover to inspect CY, LY, YoY and control values.
- Export displayed metrics or expand exact-value tables.

Weekly rates use ratios of summed amounts. Net fee is gross fee minus credits. Fee and sales reporting dates differ, so take rates are period ratios, not matched-transaction rates. Overall FVF overlaps its components. LY uses the same calendar dates one year earlier. Missing values remain gaps. Control comparisons are descriptive, not causal.

## Hosting

The app is entirely contained in `index.html`; no build, backend or external libraries are required. GitHub Pages serves the root of `main`. Its Content Security Policy blocks outbound data connections. Only synthetic data belongs in this public repository.
