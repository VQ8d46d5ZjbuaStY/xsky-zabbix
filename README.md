# Template Storage XSKY XMS by HTTP

## Overview

For Zabbix version: 4.4 and higher

This Zabbix Template includes discovery rules, item prototypes, trigger prototypes and graphs, Zabbix will periodically gather resource metrics from HTTP/HTTPS REST API, convert metrics into JSON object, automatically create resource metrics by discovery rules, and send triggers based on the trigger rules.

This template was tested on:

* XSKY SDS, V4

## Setup

1. Open XSKY SDS console ```http://<admin-ip>:8056``` in browser, and click ```Access Token``` in the right-top ```Gear``` menu.
2. Create an access token with Permission ```Observer``` for Zabbix.
3. Copy the access token in notebook, and set it in Macros of Zabbix Template.

## Zabbix configuration

No specific Zabbix configuration is required.

### Macros used

|Name|Description|Default|
|----|----|----|
|{$XMS_ACCESS_TOKEN}|XMS Access Token||
|{$XMS_API_IP}|XMS API Admin IP Address||
|{$XMS_API_PORT}|XMS API Port|8051|
|{$XMS_BUCKET_ALLOCATED_OBJECTS.MAX.WARN}|XMS Bucket Allocated Objects|80|
|{$XMS_BUCKET_ALLOCATED_SIZE.MAX.WARN}|Max Warn Percentage of XMS Bucket Allocated Size|80|
|{$XMS_OSDS_IO_UTIL.MAX.WARN}|Max Warn Percentage of XMS OSDS IO Util|90|
|{$XMS_OSDS_USED_BYTE.MAX.DISASTER}|Max Disaster Percentage of XMS OSDS Used Byte|85|
|{$XMS_OSDS_USED_BYTE.MAX.WARN}|Max Warn Percentage of XMS OSDS Used_Byte|80|
|{$XMS_OS_USER_ALLOCATED_OBJECTS.MAX.WARN}|Max Warn Percentage of XMS OS User Allocated Objects|80|
|{$XMS_OS_USER_ALLOCATED_SIZE.MAX.WARN}|Max Warn Percentage of XMS OS_User Allocated Size|80|
|{$XMS_POOL_DATA_KBYTE.MAX.DISASTER}|Max Disaster Percentage of XMS Pool Data kbyte|90|
|{$XMS_POOL_DATA_KBYTE.MAX.HIGH}|Max High Percentage of XMS Pool Data kbyte|85|
|{$XMS_POOL_DATA_KBYTE.MAX.WARN}|Max Warn Percentage of XMS Pool Data kbyte|80|
|{$XMS_S3_LOAD_BALANCER_ACTIVE_CONNECTIONS.WARN}|Max Warn Value of XMS S3 Load Balancer Active Connections|1024|
|{$XMS_S3_LOAD_BALANCER_CPU_UTIL.WARN}|Max Warn Percentage of XMS S3 Load Balancer CPU Util|80|
|{$XMS_S3_LOAD_BALANCER_MEM_USAGE_PERCENT.WARN}|Max Warn Percentage of XMS S3 Load Balancer MEM Usage|80|

### Template links

There are no template links in this template.

### Discovery rules

|Name|Description|Type|Key and additional info|
|---|---|---|---|
|XMS Disk (Cache) Discovery|Hardware Disks in Storage Cluster|HTTP agent|xms.hosts.disk_cache.discovery|
|XMS Host Discovery|Hosts in Storage Cluster|HTTP agent|xms.hosts.discovery|
|XMS Network Interfaces Discovery|Network interfaces in Storage Cluster|HTTP agent|xms.hosts.network_interfaces.discovery|
|XMS NFS-Gateways Discovery|NFS Gateways in Storage Cluster|HTTP agent|xms.os_nfs_gateways.discovery|
|XMS OS-Bucket Discovery|Object Storage Buckets in Storage Cluster|HTTP agent|xms.os_buckets.discovery|
|XMS OS-User Discovery|Object Storage Users in Storage Cluster|HTTP agent|xms.os_users.discovery|
|XMS OS-Zones Discovery|Object Storage Zones in Storage Cluster|HTTP agent|xms.os_zones.discovery|
|XMS OSD Discovery|OSDs in Storage Cluster|HTTP agent|xms.host.osds.discovery|
|XMS POOL Discovery|Storage Pools|HTTP agent|xms.pools.discovery|
|XMS S3 Load Balancer Discovery|S3 Load Balancers in Storage Cluster|HTTP agent|xms.os_s3_load_balancers.discovery|
|XMS Services Discovery|Host Services in Storage Cluster|HTTP agent|xms.hosts.services.discovery|

### Items collected

|Name|Description|Type|Key and additional info|
|---|---|---|---|
|XMS Cache Disks|Hardware Cache Disks|HTTP agent|xms.hosts.disk_cache.get|
|XMS Cluster|Cluster Overview|HTTP agent|xms.cluster.get|
|XMS Cluster: XMS Cluster Version|SDS Cluster Version|Dependent item|xms.cluster.version|
|XMS Cluster Stats|Cluster Stats|HTTP agent|xms.cluster.stats.get|
|XMS Cluster Stats: XMS Cluster Os Bucket Num|Object Storage Bucket Num|Dependent item|xms.cluster.stats.os_bucket_num|
|XMS Hosts|Storage Hosts|HTTP agent|xms.hosts.get|
|XMS Network Interfaces|Network Interfaces in Storage Cluster|HTTP agent|xms.hosts.network_interfaces.get|
|XMS OS-Buckets|Object Storage Buckets in Storage Cluster|HTTP agent|xms.os_buckets.get|
|XMS OS-NFS-Gateways|Object Storage NFS Gateways in Storage Cluster|HTTP agent|xms.os_nfs_gateways.get|
|XMS OS-S3_Load_Balancer|Object Storage S3 Load Balancers in Storage Cluster|HTTP agent|xms.os_s3_load_balancer.get|
|XMS OS-Users|Object Storage Users in Storage Cluster|HTTP agent|xms.os_users.get|
|XMS OS-Zones|Object Storage Zones in Storage Cluster|HTTP agent|xms.os_zone.get|
|XMS OSDs|OSDs in Storage Cluster|HTTP agent|xms.hosts.osds.get|
|XMS Pools|Storage Pools|HTTP agent|xms.pools.get|
|XMS Services|Host Services in Storage Cluster|HTTP agent|xms.hosts.services.get|


## Feedback

Please report any issues with the template at https://support.zabbix.com
