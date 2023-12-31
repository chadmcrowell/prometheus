# Prometheus Learning Resources

the [prometheus github page](https://github.com/prometheus/prometheus)

- [Official Prometheus Operator docs](https://prometheus-operator.dev/docs/kube/exposing-prometheus-alertmanager-grafana-ingress/)
- The [official Prometheus documentation](https://prometheus.io/docs/introduction/overview/) includes an introduction to Prometheus and its concepts, reference documentation, user guides, and best practices recommendations
- The [_Robust Perception_ blog](https://www.robustperception.io/blog) and the [PromLabs blog](https://promlabs.com/blog) cover a wide range of Prometheus use cases, implementation details, and gotchas.
- For getting usage or development help, see the [project's Community page](https://prometheus.io/community/) with pointers to the mailing lists and IRC channels for users and developers.
- [Runbooks for alerts shipped with kube-prometheus project](https://runbooks.prometheus-operator.dev/)
- [Metric and Label Naming](https://prometheus.io/docs/practices/naming)
- [Guidelines for instrucmenting your code](https://prometheus.io/docs/practices/instrumentation)
- [Consoles and Dashboards](https://prometheus.io/docs/practices/consoles/)
- [Alerting - Prometheus Docs](https://prometheus.io/docs/practices/alerting)
- [When to use Pushgateway](https://prometheus.io/docs/practices/pushing)
- [Prometheus Alert Rules - Awesome Prometheus](https://samber.github.io/awesome-prometheus-alerts/)

## Install Prometheus Operator
```bash
# add helm repo
helm repo add prometheus-community https://prometheus-community.github.io/helm-charts

# update helm repos
helm repo update

# create monitoring namespace
k create ns monitoring

# install prometheus helm chart
helm install monitoring prometheus-community/kube-prometheus-stack -n monitoring

k -n monitoring get sts # prometheus and alertmanager

k -n monitoring get deploy # kube-state-metrics, prom operator, and grafana

k -n monitoring get cm # prom rules

k -n monitoring get secret # certificates, user & pass

k -n monitoring get crd # probes, etc.
```

## Inspecting Prometheus Stack
- [Containers running Prometheus in a statefulSet - including prometheus rules, configuration reloader, etc.](https://github.com/chadmcrowell/prometheus/blob/922e5446487b861b1e6f1fd6dc89c2f2f3048030/prom.yaml#L52C2-L52C2)
- [Alertmanager Container - which contains the configuration for alerts](https://github.com/chadmcrowell/prometheus/blob/9399433e5039140e736e56954d71ab5df0b0b7a8/alertmanager.yaml#L47)


## Add Alert Rules to Prometheus




## Change Prometheus Configuration
