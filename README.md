# Elastic-ECS-SIEM
Configs and snippets for Elastic SIEM / ECS

_Fork of Dain's work from https://github.com/dainperkins/Elastic-ECS-SIEM/_
## Overview
If you happened to see the Elastic SIEM / ECS Webinar this is the spot where I'll 
be dropping various configs, code chunks, links, etc. for Elastic ECS SIEM integration
with various network / security logging formats.

### ASA
This folder contains a quick logstash config to parse out local ASA Login Messages, ecs
compliant and integrates wiht Elastic SIEM functionality.

### Meraki
This folder contains Logstash pipelines for handling Meraki syslogs, as well as logstash
configs for pulling asset information from the Meraki Dashboard API, an enrichment policy, 
and an Elastic ingest pipeline for handling geoip, asn, and meraki asset enrichment for
observers (when Meraki devices are reporting as observers) and hosts (for e.g. 1x login)
etc.)

Some day I'll add some dashboards.

Theres also a logstash directory that I'll put snippets in, currently (Thanks Derek) theres
a ruby implementastion of the general network community_id processor.

### Meraki/elasticsearch/no-logstash-ingest-pipelines folder
This folder contains:

> ingest pipelines that assume no logstash in the data pipeline thus making it optional and doing the heavylifting of also conditional structuring of incoming meraki syslogs to ECS format. Testing setup included Meraki => Filebeat(UDP Input) => Elasticsearch (ingest-pipelines)

> sample data set that was used during the development of pipeline
