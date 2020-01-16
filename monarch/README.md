# Queries

Get all Services not beeing assigned to any host:
```
select N.* from service_names N
WHERE N.servicename_id NOT IN (SELECT servicename_id FROM `services`)
AND N.deleted = 0
```


Get all commands not beeing assigned to any host template or service:
```
select C.* from commands C
WHERE type = "check" 
AND C.command_id NOT IN (SELECT check_command FROM `host_templates` WHERE check_command > 0) 
AND C.command_id NOT IN (SELECT check_command FROM `services` WHERE check_command > 0) 
```
