# Price change tracker

A static, browser-only metrics dashboard. Open `index.html` or visit the GitHub Pages site. The initial view uses synthetic demo data; no business records or database connection are included.

## Features

- Daily and Monday–Sunday weekly aggregation
- CY, calendar-aligned LY and YoY trends
- Fitted, zero-based and indexed chart axes
- Manual price-change date with pre/post and mixed-week labels
- Dimension filters and multi-dimension control groups
- Exact values and displayed-metric CSV downloads

## Load your own CSV

Use Sales CSV and Listings CSV. Files stay in browser memory; they are not uploaded, and reloading the page clears them. The page's Content Security Policy blocks outbound data connections. Maximum input size is 100 MB per file.

Sales requires `cal_dt,gmv,si`.

Listings requires `cal_dt,item_count,new_item_count,ended_item_count,item_price_sum,priced_item_count`.

Dates use `YYYY-MM-DD`. Include corresponding prior-year dates for LY/YoY. Empty or NULL metrics remain unknown rather than becoming zero. Optional dimension columns enable filtering and control groups. A dimension must be present in both files when both sources are loaded:

`site_name,item_site_id,rev_rollup,bsns_vrtcl_name,fcsd_vrtcl_name,category_group,lstg_cndtn,asp_buckets,active_cbt_flag,sp_flag,managed_seller_flag,top_seller_flag,store_type,b2c_c2c,price_change_yn`

Control rules use AND across dimensions and OR across selected values. Comparison is the remaining rows within the selected filters. This is a descriptive comparison, not a causal estimate.

Weekly active listings are daily averages; flow metrics are sums. ASP and average listing price use ratios of sums. Missing dates produce gaps. The manual event date changes the display without modifying inputs.

## Hosting

The entire app is in `index.html`; no build, backend, external libraries or database credentials are needed. GitHub Pages serves the root of `main`. Publish only the demo/CSV edition; local business CSV files do not belong in this repository.
