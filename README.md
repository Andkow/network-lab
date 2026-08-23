# network-lab

Containerlab-based network engineering lab: BGP/EVPN fabrics, gNMI telemetry,
and lossless-fabric experimentation.

## Environment
Ubuntu Server 24.04, Docker CE, containerlab 0.79.0.

## Topologies
- `topologies/hello/` — two FRR nodes, eBGP between AS 65001/65002, loopback advertisement.

## Roadmap
- SR Linux CLOS fabric with gNMI telemetry (gnmic → Prometheus → Grafana)
- NetBox as source of truth, with topology generation from device inventory
- RoCEv2: PFC/ECN behaviour on ConnectX-4, DCQCN counter analysis
