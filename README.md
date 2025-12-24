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

* __Machine:__ linux x64 | 4 vCPUs | 15.3GB Mem
* __Node:__ `v20.19.6`
* __Run:__ Wed Dec 24 2025 17:05:28 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| node-http                | v20.19.6 | ✗      | 169148.8   | 5.46         | 30.16         |
| polka                    | 0.5.2    | ✓      | 167795.2   | 5.50         | 29.92         |
| fastify                  | 5.6.2    | ✓      | 166377.6   | 5.55         | 29.83         |
| connect                  | 3.7.0    | ✗      | 160902.4   | 5.69         | 28.69         |
| micro                    | 10.0.1   | ✗      | 155699.2   | 5.92         | 27.77         |
| connect-router           | 2.2.0    | ✓      | 147776.0   | 6.24         | 26.35         |
| adonisjs                 | 7.7.0    | ✓      | 141190.4   | 6.58         | 25.18         |
| whatwg-node-server       | 0.10.17  | ✗      | 140944.0   | 6.71         | 25.13         |
| hono                     | 4.11.1   | ✓      | 137449.6   | 6.89         | 22.54         |
| 0http                    | 4.3.0    | ✓      | 134300.8   | 6.96         | 23.95         |
| restana                  | v5.1.0   | ✓      | 130166.4   | 7.18         | 23.21         |
| restify                  | 11.1.0   | ✓      | 123491.2   | 7.60         | 22.26         |
| koa                      | 3.1.1    | ✗      | 121603.2   | 7.84         | 21.69         |
| h3                       | 1.15.4   | ✗      | 114995.2   | 8.20         | 20.51         |
| microrouter              | 3.1.3    | ✓      | 112771.2   | 8.44         | 20.11         |
| koa-router               | 14.0.0   | ✓      | 111265.6   | 8.44         | 19.84         |
| h3-router                | 1.15.4   | ✓      | 110635.2   | 8.54         | 19.73         |
| hapi                     | 21.4.4   | ✓      | 109844.8   | 8.55         | 19.59         |
| srvx                     | 0.9.8    | ✗      | 69657.6    | 13.89        | 13.55         |
| fastify-big-json         | 5.6.2    | ✓      | 29592.0    | 33.28        | 340.46        |
| express                  | 5.2.1    | ✓      | 27190.4    | 36.27        | 4.85          |
| express-with-middlewares | 5.2.1    | ✓      | 24440.4    | 40.40        | 9.09          |
| trpc-router              | 11.8.1   | ✓      | 15796.0    | 62.76        | 3.48          |
