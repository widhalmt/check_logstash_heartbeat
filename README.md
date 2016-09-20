# check_logstash_heartbeat
Monitoring Plugin to check for frequent messages in Elastic Stack

**This is just an idea. Actual code is still missing**

= Purpose =

This plugin queries Elasticsearch instances for recurring messages and accepts thresholds on how often the message has to be existent.

It can be used with the `heartbeat` plugin of Logstash or with a heartbeat your applications are sending to Elastic stack.

Main purpose is to detect whether logging functionality of your logstash instances or applications still work. If the don't send the heartbeat anymore, something seems to be wrong.

You can use Icinga 2's dependency configuration to "chain" heartbeat checks. e.g. when your central logstash instances don't send heartbeats anymore it doesn't make sense to raise an alarm about remote offices not sending heartbeats anymore because even when they do, their alarms won't reach your Elasticsearch cluster anymore.
