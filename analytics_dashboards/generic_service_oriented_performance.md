# Service oriented performance dashboard

### Use case:
Compare the same service metrics among different hosts.

### Navigation:
1. Choose Service (i.e. CPU, Diskspace, etc)
2. Select Hosts to comare
3. Filter for performance label (i.e. load 5, load 15, Disk c:, Disk e:)

### Import 

Import .json file into grafana

### Integration in monitoring

Define Action link in NetEye 3.

../../grafana/d/mzCCxf_mz/service-oriented-performance-comparision?orgId=1&var-Host=$HOSTNAME$&var-Service=$SERVICEDESC$&var-performanceLabel=All

- With Pnp4nagios splash preview schreen:
../../grafana/d/mzCCxf_mz/service-oriented-performance-comparision?orgId=1&var-Host=$HOSTNAME$&var-Service=$SERVICEDESC$&var-performanceLabel=All' target='pnp' class='tips' rel='/pnp4nagios/index.php/popup?host=$HOSTNAME$&srv=$SERVICEDESC$

