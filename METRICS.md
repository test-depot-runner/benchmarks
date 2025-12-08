# Metrics
* __Machine:__ linux x64 | 4 vCPUs | 15.6GB Mem
* __Node:__ `v20.19.6`
* __Run:__ Mon Dec 08 2025 11:12:46 GMT+0000 (Coordinated Universal Time)
* __Method:__ `npm run metrics` (samples: 5)
* __startup:__ time elapsed to setup the application
* __listen:__ time elapsed until the http server is ready to accept requests (cold start)

| | startup(ms) | listen(ms) |
|-| -       | -      |
| 1-startup-routes-schema.cjs | 95.91 | 131.11 |
| 1-startup-routes.cjs | 96.87 | 107.03 |
| 10-startup-routes-schema.cjs | 96.86 | 134.75 |
| 10-startup-routes.cjs | 98.63 | 110.70 |
| 100-startup-routes-schema.cjs | 108.01 | 148.19 |
| 100-startup-routes.cjs | 111.15 | 132.94 |
| 1000-startup-routes-schema.cjs | 276.85 | 381.19 |
| 1000-startup-routes.cjs | 262.09 | 376.56 |
| 10000-startup-routes-schema.cjs | 4910.50 | 5187.80 |
| 10000-startup-routes.cjs | 4534.24 | 5846.98 |
| startup-listen.cjs | 99.19 | 110.18 |
