<div align="center"> <a href="https://fastify.dev/">
    <img
      src="https://github.com/fastify/graphics/raw/HEAD/fastify-landscape-outlined.svg"
      width="650"
      height="auto"
    />
  </a>
</div>

<div align="center">

[![CI](https://github.com/fastify/fastify/actions/workflows/ci.yml/badge.svg?branch=main)](https://github.com/fastify/fastify/actions/workflows/ci.yml)
[![Package Manager
CI](https://github.com/fastify/fastify/actions/workflows/package-manager-ci.yml/badge.svg?branch=main)](https://github.com/fastify/fastify/actions/workflows/package-manager-ci.yml)
[![Web
site](https://github.com/fastify/fastify/actions/workflows/website.yml/badge.svg?branch=main)](https://github.com/fastify/fastify/actions/workflows/website.yml)
[![neostandard javascript style](https://img.shields.io/badge/code_style-neostandard-brightgreen?style=flat)](https://github.com/neostandard/neostandard)
[![CII Best Practices](https://bestpractices.coreinfrastructure.org/projects/7585/badge)](https://bestpractices.coreinfrastructure.org/projects/7585)

</div>

<div align="center">

[![NPM
version](https://img.shields.io/npm/v/fastify.svg?style=flat)](https://www.npmjs.com/package/fastify)
[![NPM
downloads](https://img.shields.io/npm/dm/fastify.svg?style=flat)](https://www.npmjs.com/package/fastify)
[![Security Responsible
Disclosure](https://img.shields.io/badge/Security-Responsible%20Disclosure-yellow.svg)](https://github.com/fastify/fastify/blob/main/SECURITY.md)
[![Discord](https://img.shields.io/discord/725613461949906985)](https://discord.gg/fastify)
[![Contribute with Gitpod](https://img.shields.io/badge/Contribute%20with-Gitpod-908a85?logo=gitpod&color=blue)](https://gitpod.io/#https://github.com/fastify/fastify)
![Open Collective backers and sponsors](https://img.shields.io/opencollective/all/fastify)

</div>

<br />

# TL;DR

* [Fastify](https://github.com/fastify/fastify) is a fast and low overhead web framework for Node.js.
* This package shows how fast it is compared to other JS frameworks: these benchmarks do not pretend to represent a real-world scenario, but they give a **good indication of the framework overhead**.
* The benchmarks are run automatically on GitHub actions, which means they run on virtual hardware that can suffer from the "noisy neighbor" effect; this means that the results can vary.
* For metrics (cold-start) see [metrics.md](./METRICS.md)

# Requirements

To be included in this list, the framework should captivate users' interest. We have identified the following minimal requirements:
- **Ensure active usage**: a minimum of 500 downloads per week
- **Maintain an active repository** with at least one event (comment, issue, PR) in the last month
- The framework must use the **Node.js** HTTP module

# Usage

Clone this repo. Then

```
node ./benchmark [arguments (optional)]
```

#### Arguments

* `-h`: Help on how to use the tool.
* `bench`:  Benchmark one or more modules.
* `compare`: Get comparative data for your benchmarks.

> Create benchmark before comparing; `benchmark bench`

> You may also compare all test results, at once, in a single table; `benchmark compare -t`

> You can also extend the comparison table with percentage values based on fastest result; `benchmark compare -p`
# Benchmarks

* __Machine:__ linux x64 | 2 vCPUs | 7.6GB Mem
* __Node:__ `v20.19.6`
* __Run:__ Mon Dec 22 2025 14:38:25 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| node-http                | v20.19.6 | ✗      | 166883.2   | 5.54         | 29.76         |
| polka                    | 0.5.2    | ✓      | 164307.2   | 5.60         | 29.30         |
| connect                  | 3.7.0    | ✗      | 159155.2   | 5.78         | 28.38         |
| fastify                  | 5.6.2    | ✓      | 158537.6   | 5.80         | 28.42         |
| connect-router           | 2.2.0    | ✓      | 152985.6   | 6.03         | 27.28         |
| micro                    | 10.0.1   | ✗      | 151488.0   | 6.08         | 27.01         |
| restana                  | v5.1.0   | ✓      | 149875.2   | 6.18         | 26.73         |
| adonisjs                 | 7.7.0    | ✓      | 137924.0   | 6.79         | 24.60         |
| whatwg-node-server       | 0.10.17  | ✗      | 137562.4   | 6.82         | 24.53         |
| hono                     | 4.11.1   | ✓      | 134482.4   | 6.96         | 22.06         |
| restify                  | 11.1.0   | ✓      | 124014.4   | 7.56         | 22.35         |
| koa                      | 3.1.1    | ✗      | 118710.4   | 7.97         | 21.17         |
| 0http                    | 4.3.0    | ✓      | 114569.6   | 8.23         | 20.43         |
| koa-router               | 14.0.0   | ✓      | 110340.8   | 8.53         | 19.68         |
| microrouter              | 3.1.3    | ✓      | 109638.4   | 8.61         | 19.55         |
| hapi                     | 21.4.4   | ✓      | 106561.6   | 8.86         | 19.00         |
| h3                       | 1.15.4   | ✗      | 102812.8   | 9.23         | 18.34         |
| h3-router                | 1.15.4   | ✓      | 98763.2    | 9.63         | 17.61         |
| srvx                     | 0.9.8    | ✗      | 72620.8    | 13.26        | 14.13         |
| fastify-big-json         | 5.6.2    | ✓      | 28177.2    | 35.00        | 324.22        |
| express                  | 5.2.1    | ✓      | 25509.6    | 38.69        | 4.55          |
| express-with-middlewares | 5.2.1    | ✓      | 23137.6    | 42.71        | 8.61          |
| trpc-router              | 11.8.1   | ✓      | 14445.2    | 68.70        | 3.18          |
