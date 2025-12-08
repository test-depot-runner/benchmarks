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

* __Machine:__ linux x64 | 8 vCPUs | 30.4GB Mem
* __Node:__ `v20.19.6`
* __Run:__ Mon Dec 08 2025 12:03:08 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| node-http                | v20.19.6 | ✗      | 152105.6   | 6.06         | 27.13         |
| polka                    | 0.5.2    | ✓      | 149580.8   | 6.15         | 26.68         |
| connect                  | 3.7.0    | ✗      | 149366.4   | 6.14         | 26.64         |
| fastify                  | 5.6.2    | ✓      | 148492.8   | 6.19         | 26.62         |
| micro                    | 10.0.1   | ✗      | 139724.8   | 6.73         | 24.92         |
| connect-router           | 2.2.0    | ✓      | 138412.8   | 6.86         | 24.68         |
| adonisjs                 | 7.7.0    | ✓      | 129008.0   | 7.23         | 23.01         |
| whatwg-node-server       | 0.10.17  | ✗      | 128915.2   | 7.21         | 22.99         |
| 0http                    | 4.3.0    | ✓      | 124140.8   | 7.55         | 22.14         |
| hono                     | 4.10.7   | ✓      | 123790.4   | 7.50         | 20.31         |
| h3                       | 1.15.4   | ✗      | 119984.0   | 7.83         | 21.40         |
| restana                  | v5.1.0   | ✓      | 117307.2   | 8.03         | 20.92         |
| restify                  | 11.1.0   | ✓      | 111364.8   | 8.47         | 20.07         |
| koa                      | 3.1.1    | ✗      | 111035.2   | 8.46         | 19.80         |
| h3-router                | 1.15.4   | ✓      | 106243.2   | 8.92         | 18.95         |
| microrouter              | 3.1.3    | ✓      | 102798.4   | 9.13         | 18.33         |
| koa-router               | 14.0.0   | ✓      | 101201.6   | 9.36         | 18.05         |
| hapi                     | 21.4.4   | ✓      | 100715.2   | 9.47         | 17.96         |
| srvx                     | 0.9.7    | ✗      | 63259.2    | 15.31        | 12.31         |
| fastify-big-json         | 5.6.2    | ✓      | 26214.8    | 37.63        | 301.61        |
| express                  | 5.2.1    | ✓      | 25818.8    | 38.22        | 4.60          |
| express-with-middlewares | 5.2.1    | ✓      | 22416.4    | 44.09        | 8.34          |
| trpc-router              | 11.7.2   | ✓      | 17128.3    | 57.84        | 3.77          |
