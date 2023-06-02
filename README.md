# grafana-loki
Exploring grafana-loki log aggregation system

### Components
1. [`Promtail`](https://grafana.com/docs/loki/latest/clients/promtail/#promtail) is the agent responsible for sending logs to grafana Loki
  - The pattern here is to add it as sidecar container to fetch the logs via shared volume but it can also be deployed as DaemonSet
2. [`Grafana Loki`](https://grafana.com/oss/loki/) is like Prometheus but for logs and is used to index the logs by labels or tags
  - Can be reached via `grafana-loki.grafana-loki:3100`
3. [`Grafana`](https://grafana.com/) For providing the UI through which Loki queries can be executed

### Counter App
- Used to generate a new log every 30 seconds and promtail is configured to fetch the logs from `/var/log`

---

### Useful Resources
- [Meet Grafana LOKI, a Log Aggregation System for EVERYTHING](https://www.youtube.com/watch?v=h_GGd7HfKQ8)
- [Logging Architecture - Streaming sidecar container ](https://kubernetes.io/docs/concepts/cluster-administration/logging/#streaming-sidecar-container)
- [Deploy Promtail as a Sidecar to you Main App](https://t-velmachos.hashnode.dev/deploy-promtail-as-a-sidecar-to-you-main-app)