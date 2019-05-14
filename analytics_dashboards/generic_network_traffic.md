# Network traffic dashboard

### Use case:
Compare the traffic I/O on network devices separated per interface

### Navigation:
1. Choose Service (NOTE: Filter is set to .*traffic.*)
2. Select Hosts to comare
3. Filter for interface (Note: Filter applies to '(.*)_.*' )
3. Filter for traffic type ie. Bandwith, Discards (Note: Filter applies to '.*_(.*)' )

### Import 

Import .json file into grafana

### Integration in monitoring

Define Action link in NetEye 3.

../../grafana/d/eVKCQCiZk/network-traffic?orgId=1&var-Host=$HOSTNAME$&var-Service=$SERVICEDESC$&var-performanceLabel=All

- With Pnp4nagios splash preview schreen:
../../grafana/d/eVKCQCiZk/network-traffic?orgId=1&var-Host=$HOSTNAME$&var-Service=$SERVICEDESC$&var-performanceLabel=All' target='pnp' class='tips' rel='/pnp4nagios/index.php/popup?host=$HOSTNAME$&srv=$SERVICEDESC$

