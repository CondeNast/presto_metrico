Presto Metrico
===============
**NOTE:** I have made several customizations to this tool to make it work in my own Presto environment. These customizations will not work for all users. Please feel free to reach out with any questions or issues.

A small daemon process which runs and collects JMX metrics from a Presto Coordinator and submits to a statsd server  (DataDog). Stats are submitted every 15s by default. Not all JMX attributes are captured since they don't directly translate into a metric. For example, Presto, Java environment settings, and flags which cannot be converted to a datadog metric. The list of metrics being captured, is for the moment, hard coded in `metrics.go`.

```
Presto Metrico  - Collect and send Presto Metrics to datadog

OPTIONS:
-c
The coordinator node we are going to pull metrics from (be sure to precede with http:// or https://, even for localhost)
-d
The uri for the statsd client. Defaults to 127.0.0.1:8125
-t
The time in secs between sending metrics
```
