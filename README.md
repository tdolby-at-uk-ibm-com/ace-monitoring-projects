# ace-monitoring-projects
Flows with monitoring

Designed to produce monitoring events from a flow.

# v10

Deploy the BAR file; run mqsichangeflowmonitoring monitoringTestBroker -e default -j -c active

/opt/mqm/samp/bin/amqssub should work for viewing published data but might need to be recompiled with a larger GET buffer.

# v12

Deploy the BAR file; run mqsichangeflowmonitoring  v12MonitoringTestBroker -e default --all-flows --all-applications -c active

Alternatively, add
```
Monitoring:
  MessageFlow:
    publicationOn: 'active'         # choose 1 of : active|inactive, default inactive
    eventFormat: 'WMB'              # choose 1 of : MonitoringEventV2|WMB
```
to node.conf.yaml or server.conf.yaml.

The v12 command adds flow-specific overrides for each flow, and so flows deployed after the command was issued will not
have monitoring events enabled.
