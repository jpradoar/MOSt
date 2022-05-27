
# Grafana Loki

### Add helm repo
  helm repo add grafana https://grafana.github.io/helm-charts

### Update repo
  helm repo update

### Deploy Loki stack (you can select true/false to enable or not each service)
  helm install loki-stack grafana/loki-stack --create-namespace --namespace loki-stack --set promtail.enabled=true,loki.persistence.enabled=true,grafana.enabled=false,fluent-bit.enabled=true,loki.persistence.size=500Gi  
