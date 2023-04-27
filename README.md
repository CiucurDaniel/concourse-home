# Concourse fast start 

Update compose to latest version
```bash
curl -O https://concourse-ci.org/docker-compose.yml > docker-compose.yml
```

```
docker-compose up -d
```

> Refference: https://concourse-ci.org/quick-start.html




```conf
<source>
  @type syslog
  port 514
  bind 0.0.0.0
  tag system
</source>

<match system.**>
  @type file
  path /var/log/fluent/concourse
</match>
```

## Set a demo pipeline

```
./fly.exe login -u test -p test -t main -c http://localhost:8080/
./fly.exe -t main set-pipeline -p hello -c simple-pipeline.yaml
```