## Monitoring

Used grafana and prometheus

curl -X POST localhost:9090/-/reload

http://localhost:3001/metrics
http://localhost:8080/metrics

Lembrando que

lado esquerdo é a porta da minha maquina e lado direito é a porta do meu container

https://app.diagrams.net/
https://play.grafana.org/d/000000012/grafana-play-home?orgId=1

ver logs no docker : docker logs -f

Ver as metricas :
backend: http://localhost:8081/metrics
worker: http://localhost:3001/metrics
prometheus: http://localhost:9090/metrics
grafana: http://localhost:3010/metrics

qdo tem um bucket na metrica, preciso usar algo de histagram, não consigo utilizar um "sum"
histogram_quantile(0.5, rate(flask_http_request_duration_seconds_bucket{status="200"[30s]}))
