
# Install chaosexporter-prometheus-grafana stack for visualizing Litmus metrics

- The Kubernetes resources used as part of this exercise are installed into litmus namespace & use the Litmus Service Account. Refer: <a href="https://docs.litmuschaos.io/docs/faq-general/#what-are-the-permissions-required-to-run-litmus-chaos-experiments">FAQ</a>.

  To install litmus infra components:

  `kubectl apply -f https://litmuschaos.github.io/litmus/litmus-operator-v1.6.1.yaml`



## Step 1:

- Install Chaos Exporter  
    `$ kubectl apply -f https://raw.githubusercontent.com/litmuschaos/chaos-exporter/master/deploy/chaos-exporter.yaml`

## Step 2:

- Install Prometheus to use chaos exporter service:
    `$ kubectl apply -f ./utils/prometheus-manifests.yaml`

## Step 3:

- After this, use Grafana to visualize Kubernetes Events send by Prometheus
    `$ kubectl apply -f ./litmus-grafana.yaml`

## Step 4:

- Head over to Grafana, to see the metrics by using Prometheus as a sink and view the chaos exporter.

## Images for Reference:

![](https://github.com/litmuschaos/chaos-observability/blob/master/images/litmus-prometheus-metrics.png)
