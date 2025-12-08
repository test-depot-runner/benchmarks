# Metrics
* __Machine:__ linux x64 | 8 vCPUs | 30.4GB Mem
* __Node:__ `v20.19.6`
* __Run:__ Mon Dec 08 2025 11:32:14 GMT+0000 (Coordinated Universal Time)
* __Method:__ `npm run metrics` (samples: 5)
* __startup:__ time elapsed to setup the application
* __listen:__ time elapsed until the http server is ready to accept requests (cold start)

| | startup(ms) | listen(ms) |
|-| -       | -      |
| 1-startup-routes-schema.cjs | 49.28 | 68.55 |
| 1-startup-routes.cjs | 48.63 | 54.99 |
| 10-startup-routes-schema.cjs | 50.21 | 70.12 |
| 10-startup-routes.cjs | 49.75 | 56.89 |
| 100-startup-routes-schema.cjs | 53.80 | 75.69 |
| 100-startup-routes.cjs | 52.95 | 63.33 |
| 1000-startup-routes-schema.cjs | 124.93 | 171.89 |
| 1000-startup-routes.cjs | 122.63 | 177.65 |
| 10000-startup-routes-schema.cjs | 2024.98 | 2196.47 |
| 10000-startup-routes.cjs | 1926.93 | 2705.14 |
| startup-listen.cjs | 48.80 | 55.43 |
