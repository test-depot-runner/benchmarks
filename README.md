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
* __Run:__ Thu Jan 01 2026 02:29:10 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| node-http                | v20.19.6 | ✗      | 170352.0   | 5.44         | 30.38         |
| polka                    | 0.5.2    | ✓      | 166278.4   | 5.52         | 29.65         |
| connect                  | 3.7.0    | ✗      | 166112.0   | 5.53         | 29.62         |
| fastify                  | 5.6.2    | ✓      | 163939.2   | 5.60         | 29.39         |
| restana                  | v5.1.0   | ✓      | 156505.6   | 5.89         | 27.91         |
| micro                    | 10.0.1   | ✗      | 156416.0   | 5.88         | 27.89         |
| connect-router           | 2.2.0    | ✓      | 154905.6   | 5.92         | 27.63         |
| adonisjs                 | 7.7.0    | ✓      | 143427.2   | 6.48         | 25.58         |
| whatwg-node-server       | 0.10.17  | ✗      | 142963.2   | 6.60         | 25.50         |
| hono                     | 4.11.3   | ✓      | 139120.0   | 6.82         | 22.82         |
| 0http                    | 4.3.0    | ✓      | 135827.2   | 6.88         | 24.22         |
| koa                      | 3.1.1    | ✗      | 123817.6   | 7.64         | 22.08         |
| restify                  | 11.1.0   | ✓      | 122628.8   | 7.68         | 22.10         |
| h3                       | 1.15.4   | ✗      | 116110.4   | 8.12         | 20.71         |
| h3-router                | 1.15.4   | ✓      | 113644.8   | 8.30         | 20.27         |
| microrouter              | 3.1.3    | ✓      | 113347.2   | 8.34         | 20.21         |
| koa-router               | 14.0.0   | ✓      | 112697.6   | 8.32         | 20.10         |
| hapi                     | 21.4.4   | ✓      | 110321.6   | 8.49         | 19.67         |
| srvx                     | 0.9.8    | ✗      | 71212.8    | 13.57        | 13.85         |
| fastify-big-json         | 5.6.2    | ✓      | 29898.0    | 32.94        | 344.00        |
| express                  | 5.2.1    | ✓      | 27824.0    | 35.43        | 4.96          |
| express-with-middlewares | 5.2.1    | ✓      | 24609.2    | 40.12        | 9.15          |
| trpc-router              | 11.8.1   | ✓      | 16150.4    | 61.38        | 3.56          |
