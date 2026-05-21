# Monitoring Stack with Prometheus, Grafana, Node Exporter & Blackbox Exporter

## Overview
A complete Docker Compose monitoring stack for observing a sample stress application using:
 - Docker
 - Prometheus
 - Grafana
 - Node Exporter
 - Blackbox Exporter

## Features
- Monitor application uptime and health
- Collect host machine metrics
- Visualize metrics in Grafana dashboards
- Perform HTTP endpoint probing using Blackbox Exporter
- Fully containerized with Docker Compose


## Project Structure
```
.
├── docker-compose.yml
├── prometheus.yml
├── blackbox.yml
└── README.md
```

## Docker Compose Configuration

The stack includes the following services:
| Service             | Port | Purpose            |
| ------------------- | ---- | ------------------ |
| stress-app          | 8085 | Sample application |
| Prometheus          | 9090 | Metrics collection |
| Grafana             | 3000 | Visualization      |
| Node Exporter       | 9100 | Host metrics       |
| Blackbox Exporter   | 9115 | Endpoint probing   |


## Prerequisites

Install:

Docker
Docker Compose

Verify installation:
```
docker --version
docker compose version
```

## Running the Stack

Clone the repository:
```
git clone https://github.com/Kosisochi1/server_monitoring.git
cd server_monitoring
```

Start services:

```
docker compose up -d
```

Check running containers:

```
docker ps
```

## Access Services


| Service           | URL                                            |
| ----------------- | ---------------------------------------------- |
| Stress App        | [http://localhost:8085](http://localhost:8085) |
| Prometheus        | [http://localhost:9090](http://localhost:9090) |
| Grafana           | [http://localhost:3000](http://localhost:3000) |
| Blackbox Exporter | [http://localhost:9115](http://localhost:9115) |

## Prometheus Configuration

Your Prometheus configuration scrapes:
- Prometheus internal metrics
- Node Exporter metrics
- Blackbox HTTP probe metrics

## Grafana Setup

Default credentials:
```
Username: admin
Password: admin
```

After login:

- Add Prometheus as a datasource
- URL:
  ```
  http://prometheus:9090
  ```
- Import dashboards from Grafana Dashboard Library

  Recommended dashboards:



| Dashboard          | ID   |
| ------------------ | ---- |
| Node Exporter Full | 1860 |
| Blackbox Exporter  | 7587 |


## Stopping the Stack
```
docker compose down
```
Remove volumes:

```
docker compose down -v
```

## Troubleshooting
Check container names:
```
docker ps
```
Check service log
```
docker logs <service_name>
```

## References
- Prometheus Documentation
- Grafana Documentation
- Blackbox Exporter
- Node Exporter


Author
Emmanuel Ezeoyiri



  
  
