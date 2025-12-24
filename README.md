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
* __Run:__ Wed Dec 24 2025 09:08:59 GMT+0000 (Coordinated Universal Time)
* __Method:__ `autocannon -c 100 -d 40 -p 10 localhost:3000` (two rounds; one to warm-up, one to measure)

|                          | Version  | Router | Requests/s | Latency (ms) | Throughput/Mb |
| :--                      | --:      | --:    | :-:        | --:          | --:           |
| node-http                | v20.19.6 | ✗      | 169724.8   | 5.43         | 30.27         |
| connect                  | 3.7.0    | ✗      | 168691.2   | 5.48         | 30.08         |
| polka                    | 0.5.2    | ✓      | 167510.4   | 5.52         | 29.87         |
| fastify                  | 5.6.2    | ✓      | 163990.4   | 5.60         | 29.40         |
| micro                    | 10.0.1   | ✗      | 156172.8   | 5.89         | 27.85         |
| connect-router           | 2.2.0    | ✓      | 155664.0   | 5.92         | 27.76         |
| adonisjs                 | 7.7.0    | ✓      | 144124.8   | 6.34         | 25.70         |
| whatwg-node-server       | 0.10.17  | ✗      | 143808.0   | 6.56         | 25.64         |
| hono                     | 4.11.1   | ✓      | 138220.8   | 6.84         | 22.68         |
| 0http                    | 4.3.0    | ✓      | 135368.8   | 6.89         | 24.14         |
| restana                  | v5.1.0   | ✓      | 128256.0   | 7.29         | 22.87         |
| koa                      | 3.1.1    | ✗      | 123145.6   | 7.71         | 21.96         |
| restify                  | 11.1.0   | ✓      | 122136.0   | 7.75         | 22.02         |
| h3                       | 1.15.4   | ✗      | 119305.6   | 7.89         | 21.27         |
| h3-router                | 1.15.4   | ✓      | 116980.8   | 8.05         | 20.86         |
| microrouter              | 3.1.3    | ✓      | 113451.2   | 8.40         | 20.23         |
| koa-router               | 14.0.0   | ✓      | 113278.4   | 8.29         | 20.20         |
| hapi                     | 21.4.4   | ✓      | 109508.8   | 8.57         | 19.53         |
| srvx                     | 0.9.8    | ✗      | 70792.0    | 13.66        | 13.77         |
| fastify-big-json         | 5.6.2    | ✓      | 29464.4    | 33.43        | 339.02        |
| express                  | 5.2.1    | ✓      | 27714.4    | 35.56        | 4.94          |
| express-with-middlewares | 5.2.1    | ✓      | 24520.4    | 40.26        | 9.12          |
| trpc-router              | 11.8.1   | ✓      | 16005.4    | 61.95        | 3.53          |
