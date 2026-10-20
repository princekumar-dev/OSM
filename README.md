<div align="center">

# OSM — OpenRouteService (Study Snapshot)

### Running a self-hosted OpenStreetMap routing engine locally

[![Java](https://img.shields.io/badge/Java-21-ED8B00?style=flat-square&logo=openjdk&logoColor=white)](https://openjdk.org)
[![Spring Boot](https://img.shields.io/badge/Spring_Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white)](https://spring.io/projects/spring-boot)
[![Maven](https://img.shields.io/badge/Apache-Maven-C71A36?style=flat-square&logo=apachemaven&logoColor=white)](https://maven.apache.org)
[![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)](https://www.docker.com)
[![OpenStreetMap](https://img.shields.io/badge/Data-OpenStreetMap-7EBC6F?style=flat-square&logo=openstreetmap&logoColor=white)](https://www.openstreetmap.org)
[![License](https://img.shields.io/badge/License-Apache_2.0-blue?style=flat-square)](LICENSE)

</div>

---

## ⚠️ About This Repository

This repository contains an **unmodified snapshot of [OpenRouteService](https://github.com/GIScience/openrouteservice) v9.9.0** — the open-source routing engine built by **GIScience / Heidelberg Institute for Geoinformation Technology**.

**All code here belongs to the upstream authors** (see [NOTICE.md](NOTICE.md) and the [Apache 2.0 LICENSE](LICENSE)). This copy is kept for:

- 📖 **Studying** a production-grade Java/Spring Boot routing engine (graph handling, REST API design, Docker packaging)
- 🖥️ **Running a local routing API** on OpenStreetMap data for experiments in my other projects
- 🧪 **Testing** directions, isochrones, and matrix endpoints offline

> **Active development happens upstream** — for the latest version, issues, and contributions, use **[GIScience/openrouteservice](https://github.com/GIScience/openrouteservice)** and the [official docs](https://giscience.github.io/openrouteservice/).

## 🗺️ What Is OpenRouteService?

A highly customizable, performant routing service written in Java, built on a forked GraphHopper 4.0, consuming free geographic data from **OpenStreetMap**. It provides:

| Service | What it gives you |
|---------|-------------------|
| **Directions** | Turn-by-turn routes for driving, cycling, walking, wheelchair & more |
| **Isochrones** | Areas of reachability from a location (e.g. "10 minutes away") |
| **Matrix** | Time/distance between many origin–destination pairs |
| **Snapping** | Nearest point on the road network for any coordinate |
| **Export** | The underlying routing graph per transport mode |
| **Health / Status** | Instance monitoring (self-hosted only) |

## 🚀 Quick Start (Docker)

```bash
# Clone with LFS files (elevation data etc.)
git lfs install
git clone https://github.com/princekumar-dev/OSM.git
cd OSM

# Start the routing API
docker compose up -d
```

The API becomes available on `http://localhost:8080/ors/v2/directions/...` — see the [API reference](https://giscience.github.io/openrouteservice/api-reference/) for endpoints and parameters.

> 📦 Large test/geometry files are tracked with **Git LFS** — run `git lfs pull` if a build complains about missing binaries.

## 🧱 Repository Layout (upstream)

```
OSM/
├── ors-api/               # REST API layer (Spring Boot)
├── ors-engine/            # Core OSM routing engine
├── ors-benchmark/         # Performance testing
├── ors-test-scenarios/    # Integration tests
├── ors-report-aggregation/
├── docs/                  # VitePress documentation site
├── Dockerfile · docker-compose.yml
└── pom.xml                # Maven build (multi-module)
```

## 🙏 Attribution

- **Project:** [OpenRouteService](https://github.com/GIScience/openrouteservice) by **GIScience**
- **License:** [Apache License 2.0](LICENSE) — see [NOTICE.md](NOTICE.md) for third-party notices
- **Data:** © [OpenStreetMap](https://www.openstreetmap.org/copyright) contributors (ODbL)

*This snapshot was recorded for personal study; consider ⭐-ing the [upstream repo](https://github.com/GIScience/openrouteservice) if you find it useful.*
