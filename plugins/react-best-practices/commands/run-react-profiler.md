---
name: run-react-profiler
description: Run React DevTools profiler and generate a render performance report identifying slow components.
---

# Run React Profiler

Profile component render performance and identify bottlenecks.

## Steps

1. Build app with profiling enabled (`REACT_APP_PROFILE=true`)
2. Run automated interaction scripts to trigger renders
3. Collect React DevTools profiler data
4. Identify components with highest render time
5. Find components rendering more than expected
6. Generate report with flame graph summary
7. Suggest memoization targets based on render frequency and cost
