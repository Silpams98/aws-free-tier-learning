
===============
Agent (v7.81.3)
===============
  Status date: 2026-07-31 09:42:37.558 UTC (1785490957558)
  Agent start: 2026-07-31 09:42:09.457 UTC (1785490929457)
  Pid: 3471
  Go Version: go1.26.5
  Python Version: unused
  Build arch: amd64
  Agent flavor: agent
  FIPS Mode: not available
  Log Level: info
  Configuration lib used: nodetreemodel

  Paths
  =====
    Config File: /etc/datadog-agent/datadog.yaml
    conf.d: /etc/datadog-agent/conf.d
    checks.d: /etc/datadog-agent/checks.d

========
Hostname
========

  ccrid: arn:aws:ec2:us-east-1:364769971052:instance/i-05d29e48c84998ec1
  ec2-hostname: ip-172-31-26-192.ec2.internal
  host_aliases: [i-05d29e48c84998ec1]
  hostname: i-05d29e48c84998ec1
  hostname-resolution-version: 1
  instance-id: i-05d29e48c84998ec1
  legacy-resolution-hostname: ip-172-31-26-192.ec2.internal
  socket-fqdn: ip-172-31-26-192.ec2.internal.
  socket-hostname: ip-172-31-26-192.ec2.internal
  hostname provider: aws
  unused hostname providers:
    'hostname' configuration/environment: hostname is empty
    'hostname_file' configuration/environment: 'hostname_file' configuration is not enabled
    aws: Unable to determine hostname from EC2: status code 401 trying to GET http://169.254.169.254/latest/meta-data/instance-id
    azure: azure_hostname_style is set to 'os'
    container: the agent is not containerized
    fargate: agent is not running in sidecar mode
    fqdn: 'hostname_fqdn' configuration is not enabled
    gce: unable to retrieve hostname from GCE: GCE metadata API error: status code 401 trying to GET http://169.254.169.254/computeMetadata/v1/instance/hostname


Host Info
=========
  bootTime: 2026-07-31 09:12:15 UTC (1785489135000)
  hostId: ec244cf7-b97c-082b-8251-a75a2d491299
  kernelArch: x86_64
  kernelVersion: 6.18.38-76.139.amzn2023.x86_64
  os: linux
  platform: amazon
  platformFamily: rhel
  platformVersion: 2023.12.20260727
  procs: 112
  uptime: 29m55s


======
Clocks
======

NTP offset: 5µs
Intake offset: -134.855ms

========
Metadata
========

  agent_startup_time_ms: 1785490929896
  agent_version: 7.81.3
  auto_instrumentation_modes: []
  feature_auto_instrumentation_enabled: false
  feature_otlp_enabled: false
  flavor: agent
  hostname_source: aws
  infrastructure_mode: full
  install_method_installer_version: install_script-1.46.0
  install_method_tool: install_script
  install_method_tool_version: install_script_agent7
  package_version: 7.81.3

=================
HA Agent Metadata
=================


=========
Collector
=========


  Running Checks
  ==============

    cloud_hostinfo
    --------------
      Instance ID: cloud_hostinfo [OK]
      Configuration Source: file:/etc/datadog-agent/conf.d/cloud_hostinfo.d/conf.yaml.default[0]
      Total Runs: 2
      Metric Samples: Last Run: 0, Total: 0
      Events: Last Run: 0, Total: 0
      Service Checks: Last Run: 0, Total: 0
      Average Execution Time : 1ms
      Last Execution Date : 2026-07-31 09:42:26.552 UTC (1785490946552)
      Last Successful Execution Date : 2026-07-31 09:42:26 UTC (1785490946000)
      metadata:
        config.source: /etc/datadog-agent/conf.d/cloud_hostinfo.d/conf.yaml.default[0]


    container_image
    ---------------
      Instance ID: container_image [OK]
      Long Running Check: true
      Configuration Source: file:/etc/datadog-agent/conf.d/container_image.d/conf.yaml.default[0]
      Total Metric Samples: 0
      Total Events: 0
      Total Service Checks: 0
      metadata:
        config.source: /etc/datadog-agent/conf.d/container_image.d/conf.yaml.default[0]


    container_lifecycle
    -------------------
      Instance ID: container_lifecycle [OK]
      Long Running Check: true
      Configuration Source: file:/etc/datadog-agent/conf.d/container_lifecycle.d/conf.yaml.default[0]
      Total Metric Samples: 0
      Total Events: 0
      Total Service Checks: 0
      metadata:
        config.source: /etc/datadog-agent/conf.d/container_lifecycle.d/conf.yaml.default[0]


    cpu
    ---
      Instance ID: cpu [OK]
      Configuration Source: file:/etc/datadog-agent/conf.d/cpu.d/conf.yaml.default[0]
      Total Runs: 2
      Metric Samples: Last Run: 19, Total: 31
      Events: Last Run: 0, Total: 0
      Service Checks: Last Run: 0, Total: 0
      Average Execution Time : 0s
      Last Execution Date : 2026-07-31 09:42:32.553 UTC (1785490952553)
      Last Successful Execution Date : 2026-07-31 09:42:32 UTC (1785490952000)
      metadata:
        config.source: /etc/datadog-agent/conf.d/cpu.d/conf.yaml.default[0]


    discovery
    ---------
      Instance ID: discovery [OK]
      Configuration Source: file:/etc/datadog-agent/conf.d/discovery.d/conf.yaml.default[0]
      Total Runs: 1
      Metric Samples: Last Run: 0, Total: 0
      Events: Last Run: 0, Total: 0
      Service Checks: Last Run: 0, Total: 0
      Average Execution Time : 0s
      Last Execution Date : 2026-07-31 09:42:11.556 UTC (1785490931556)
      Last Successful Execution Date : 2026-07-31 09:42:11 UTC (1785490931000)
      metadata:
        config.source: /etc/datadog-agent/conf.d/discovery.d/conf.yaml.default[0]


    disk
    ----
      Instance ID: disk:67cc0574430a16ba [OK]
      Configuration Source: file:/etc/datadog-agent/conf.d/disk.d/conf.yaml.default[0]
      Total Runs: 1
      Metric Samples: Last Run: 91, Total: 91
      Events: Last Run: 0, Total: 0
      Service Checks: Last Run: 0, Total: 0
      Average Execution Time : 14ms
      Last Execution Date : 2026-07-31 09:42:24.568 UTC (1785490944568)
      Last Successful Execution Date : 2026-07-31 09:42:24 UTC (1785490944000)
      metadata:
        config.source: /etc/datadog-agent/conf.d/disk.d/conf.yaml.default[0]


    file_handle
    -----------
      Instance ID: file_handle [OK]
      Configuration Source: file:/etc/datadog-agent/conf.d/file_handle.d/conf.yaml.default[0]
      Total Runs: 2
      Metric Samples: Last Run: 5, Total: 10
      Events: Last Run: 0, Total: 0
      Service Checks: Last Run: 0, Total: 0
      Average Execution Time : 0s
      Last Execution Date : 2026-07-31 09:42:31.552 UTC (1785490951552)
      Last Successful Execution Date : 2026-07-31 09:42:31 UTC (1785490951000)
      metadata:
        config.source: /etc/datadog-agent/conf.d/file_handle.d/conf.yaml.default[0]


    io
    --
      Instance ID: io [OK]
      Configuration Source: file:/etc/datadog-agent/conf.d/io.d/conf.yaml.default[0]
      Total Runs: 1
      Metric Samples: Last Run: 18, Total: 18
      Events: Last Run: 0, Total: 0
      Service Checks: Last Run: 0, Total: 0
      Average Execution Time : 1ms
      Last Execution Date : 2026-07-31 09:42:23.553 UTC (1785490943553)
      Last Successful Execution Date : 2026-07-31 09:42:23 UTC (1785490943000)
      metadata:
        config.source: /etc/datadog-agent/conf.d/io.d/conf.yaml.default[0]


    load
    ----
      Instance ID: load [OK]
      Configuration Source: file:/etc/datadog-agent/conf.d/load.d/conf.yaml.default[0]
      Total Runs: 2
      Metric Samples: Last Run: 6, Total: 12
      Events: Last Run: 0, Total: 0
      Service Checks: Last Run: 0, Total: 0
      Average Execution Time : 0s
      Last Execution Date : 2026-07-31 09:42:30.552 UTC (1785490950552)
      Last Successful Execution Date : 2026-07-31 09:42:30 UTC (1785490950000)
      metadata:
        config.source: /etc/datadog-agent/conf.d/load.d/conf.yaml.default[0]


    memory
    ------
      Instance ID: memory [OK]
      Configuration Source: file:/etc/datadog-agent/conf.d/memory.d/conf.yaml.default[0]
      Total Runs: 2
      Metric Samples: Last Run: 20, Total: 40
      Events: Last Run: 0, Total: 0
      Service Checks: Last Run: 0, Total: 0
      Average Execution Time : 0s
      Last Execution Date : 2026-07-31 09:42:37.553 UTC (1785490957553)
      Last Successful Execution Date : 2026-07-31 09:42:37 UTC (1785490957000)
      metadata:
        config.source: /etc/datadog-agent/conf.d/memory.d/conf.yaml.default[0]


    network
    -------
      Instance ID: network [OK]
      Configuration Source: file:/etc/datadog-agent/conf.d/network.d/conf.yaml.default[0]
      Total Runs: 2
      Metric Samples: Last Run: 83, Total: 166
      Events: Last Run: 0, Total: 0
      Service Checks: Last Run: 0, Total: 0
      Average Execution Time : 0s
      Last Execution Date : 2026-07-31 09:42:29.554 UTC (1785490949554)
      Last Successful Execution Date : 2026-07-31 09:42:29 UTC (1785490949000)
      metadata:
        config.source: /etc/datadog-agent/conf.d/network.d/conf.yaml.default[0]


    ntp
    ---
      Instance ID: ntp:3c427a42a70bbf8 [OK]
      Configuration Source: file:/etc/datadog-agent/conf.d/ntp.d/conf.yaml.default[0]
      Total Runs: 1
      Metric Samples: Last Run: 2, Total: 2
      Events: Last Run: 0, Total: 0
      Service Checks: Last Run: 1, Total: 1
      Average Execution Time : 1ms
      Last Execution Date : 2026-07-31 09:42:11.567 UTC (1785490931567)
      Last Successful Execution Date : 2026-07-31 09:42:11 UTC (1785490931000)
      metadata:
        config.source: /etc/datadog-agent/conf.d/ntp.d/conf.yaml.default[0]


    telemetry
    ---------
      Instance ID: telemetry [OK]
      Configuration Source: file:/etc/datadog-agent/conf.d/telemetry.d/conf.yaml.default[0]
      Total Runs: 1
      Metric Samples: Last Run: 4, Total: 4
      Events: Last Run: 0, Total: 0
      Service Checks: Last Run: 0, Total: 0
      Average Execution Time : 3.001s
      Last Execution Date : 2026-07-31 09:42:24.553 UTC (1785490944553)
      Last Successful Execution Date : 2026-07-31 09:42:24 UTC (1785490944000)
      metadata:
        config.source: /etc/datadog-agent/conf.d/telemetry.d/conf.yaml.default[0]


    uptime
    ------
      Instance ID: uptime [OK]
      Configuration Source: file:/etc/datadog-agent/conf.d/uptime.d/conf.yaml.default[0]
      Total Runs: 2
      Metric Samples: Last Run: 1, Total: 2
      Events: Last Run: 0, Total: 0
      Service Checks: Last Run: 0, Total: 0
      Average Execution Time : 0s
      Last Execution Date : 2026-07-31 09:42:28.553 UTC (1785490948553)
      Last Successful Execution Date : 2026-07-31 09:42:28 UTC (1785490948000)
      metadata:
        config.source: /etc/datadog-agent/conf.d/uptime.d/conf.yaml.default[0]

  Check Worker Utilization
  ========================
    Total Workers: 4
    Average Utilization: 1.2%

    Top Workers (by utilization):
      worker_2: 5.0%
      worker_1: 0.0%
      worker_3: 0.0%
      worker_4: 0.0%

==========
Aggregator
==========

  Checks Metric Sample: 432
  Dogstatsd Metric Sample: 1
  Event: 1
  Events Flushed: 1
  Number Of Flushes: 1
  Series Flushed: 108
  Service Check: 1
  Service Checks Flushed: 2

=========
APM Agent
=========


  Status: Not running or unreachable on localhost:5012.
  Error: Get "https://localhost:5012/debug/vars": dial tcp 127.0.0.1:5012: connect: connection refused

=============
Delegatedauth
=============

Delegated Authentication is not enabled

=========
DogStatsD
=========

  Event Packets: 0
  Event Parse Errors: 0
  Metric Packets: 0
  Metric Parse Errors: 0
  Service Check Packets: 0
  Service Check Parse Errors: 0
  Udp Bytes: 0
  Udp Packet Reading Errors: 0
  Udp Packets: 0
  Uds Bytes: 0
  Uds Origin Detection Errors: 0
  Uds Packet Reading Errors: 0
  Uds Packets: 1
  Unterminated Metric Errors: 0

Tip: For troubleshooting, enable 'dogstatsd_metrics_stats_enable' in the main datadog.yaml file to generate Dogstatsd logs. Once 'dogstatsd_metrics_stats_enable' is enabled, users can also use 'dogstatsd-stats' command to get visibility of the latest collected metrics.

=========
Endpoints
=========

  https://app.datadoghq.com. - API Key ending with:
      - 7115

================
Fleet Automation
================


  Fleet Management is enabled

  Remote Management Status:    Enabled
  Datadog Installer Status:    Running


=========
Forwarder
=========

  Transactions
  ============
    Cluster: 0
    ClusterRole: 0
    ClusterRoleBinding: 0
    CronJob: 0
    CustomResource: 0
    CustomResourceDefinition: 0
    DaemonSet: 0
    Deployment: 0
    Dropped: 0
    ECSTask: 0
    EndpointSlice: 0
    HighPriorityQueueFull: 0
    HorizontalPodAutoscaler: 0
    Ingress: 0
    Job: 0
    KubeletConfiguration: 0
    LimitRange: 0
    Namespace: 0
    NetworkPolicy: 0
    Node: 0
    OrchestratorManifest: 0
    PersistentVolume: 0
    PersistentVolumeClaim: 0
    Pod: 0
    PodDisruptionBudget: 0
    ReplicaSet: 0
    Requeued: 0
    Retried: 0
    RetryQueueSize: 0
    Role: 0
    RoleBinding: 0
    Service: 0
    ServiceAccount: 0
    StatefulSet: 0
    StorageClass: 0
    VerticalPodAutoscaler: 0

  Transaction Successes
  =====================
    Total number: 5
    Successes By Endpoint:
      check_run_v1: 1
      intake: 3
      series_v3: 1

  On-disk storage
  ===============
    On-disk storage is disabled. Configure `forwarder_storage_max_size_in_bytes` to enable it.

  API Keys status
  ===============
    API key ending with 7115: API Key valid

=========
JMX Fetch
=========

  Information
  ==================
  Initialized checks
  ==================
    no checks

  Failed checks
  =============
    no checks


==========
Logs Agent
==========

  Logs Agent is not running

==========
OTel Agent
==========


  Status: Not running or unreachable on https://localhost:7777.
  Error: OTel Agent is not enabled.

====
OTLP
====

  Status: Not enabled
  Collector status: Not running



=====================
Private Action Runner
=====================
Status: Disabled

=============
Process Agent
=============

  Status: Not running or unreachable

=================
Process Component
=================


  Enabled Checks: [process rtprocess]
  System Probe Process Module Status: Not running
  Process Language Detection Enabled: False

  =================
  Process Endpoints
  =================
    https://process.datadoghq.com. - API Key ending with:
        - 7115

  =========
  Collector
  =========
    Last collection time: 2026-07-31 09:42:32
    Docker socket: 
    Number of processes: 0
    Number of containers: 0
    Process Queue length: 0
    RTProcess Queue length: 0
    Connections Queue length: 0
    Event Queue length: 0
    Process Bytes enqueued: 0
    RTProcess Bytes enqueued: 0
    Connections Bytes enqueued: 0
    Event Bytes enqueued: 0
    Drop Check Payloads: []
    Number of submission errors: 0

  ==========
  Extractors
  ==========

    Workloadmeta
    ============
      Cache size: 0
      Stale diffs discarded: 0
      Diffs dropped: 0

=============
Remote Agents
=============

1 remote agent(s) registered:

  Name: Agent Data Plane
  Flavor: agent_data_plane
  Session ID: d86645c1-6fa9-4548-8b9a-bafe010d0233
  ----------------
  Last seen: 29.612020451s ago

================
Agent Data Plane
================

Failed to query for status: rpc error: code = DeadlineExceeded desc = latest balancer error: connection error: desc = "transport: Error while dialing: dial tcp 127.0.0.1:5101: connect: connection refused"

====================
Remote Configuration
====================


Organization enabled: True
API Key: Not authorized, add the Remote Configuration Read permission to enable it for this agent.
Last error: None



=======
Secrets
=======

No secret_backend_command set: secrets feature is not enabled
===
SSI
===

    SSI is not enabled.


============
System Probe
============


========================
Transport Proxy Warnings
========================

  No Transport Proxy Warnings

[ec2-user@ip-172-31-26-192 ~]$ 
