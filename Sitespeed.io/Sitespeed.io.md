
**`Sitespeed.io`** is basically the sweet spot for _free + accurate + CLI-first_ performance auditing.

# When `Sitespeed.io` shines
✔ Client-side only testing  
✔ Detect useless requests  
✔ Visualize request storms  
✔ Compare runs over time  
✔ No backend access needed



# Run a basic audit
```sh
docker run --rm -v "$(pwd)":/sitespeed.io sitespeedio/sitespeed.io https://example.com
```
- `--rm` → removes container after finish
- `-v "$(pwd)":/sitespeed.io` → mounts current folder to save reports
- The report will appear in `./sitespeed-result/` inside your current folder

# Add multiple iterations for stable metrics
```sh
docker run --rm -v "$(pwd)":/sitespeed.io sitespeedio/sitespeed.io \
https://example.com \
--browsertime.iterations 5
```
Repeats test 5 times and averages metrics. Reduces noise.

# Throttle network (simulate realistic speed)
```sh
docker run --rm -v "$(pwd)":/sitespeed.io sitespeedio/sitespeed.io \
https://example.com \
--browsertime.iterations 5 \
--connectivity.profile cable
```
Other built-in profiles: `3GFast`, `3GSlow`, `DSL`, `native`.

# Capture video & waterfalls
```sh
docker run --rm -v "$(pwd)":/sitespeed.io sitespeedio/sitespeed.io \
https://example.com \
--browsertime.iterations 3 \
--connectivity.profile cable \
--video \
--html.showAllWaterfallSummary
```
- `--video` → records page load visually
- `--html.showAllWaterfallSummary` → full request waterfall summary in HTML report

# Save reports to a custom folder
```sh
docker run --rm -v "$(pwd)":/sitespeed.io sitespeedio/sitespeed.io \
https://example.com \
--outputFolder my-audit-report
```
All reports (HTML, JSON, HAR, screenshots) will be in `my-audit-report/`.


