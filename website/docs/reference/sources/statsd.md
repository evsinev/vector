---
delivery_guarantee: "best_effort"
description: "The Vector `statsd` source ingests data through the StatsD UDP protocol and outputs `metric` events."
event_types: ["metric"]
issues_url: https://github.com/timberio/vector/issues?q=is%3Aopen+is%3Aissue+label%3A%22source%3A+statsd%22
operating_systems: ["linux","macos","windows"]
sidebar_label: "statsd|[\"metric\"]"
source_url: https://github.com/timberio/vector/tree/master/src/sources/statsd/mod.rs
status: "beta"
title: "Statsd Source"
unsupported_operating_systems: []
---

The Vector `statsd` source ingests data through the StatsD UDP protocol and outputs [`metric`][docs.data-model.metric] events.

<!--
     THIS FILE IS AUTOGENERATED!

     To make changes please edit the template located at:

     website/docs/reference/sources/statsd.md.erb
-->

## Configuration

import CodeHeader from '@site/src/components/CodeHeader';

<CodeHeader fileName="vector.toml" learnMoreUrl="/docs/setup/configuration/"/ >

```toml
[sources.my_source_id]
  type = "statsd" # example, must be: "statsd"
  address = "127.0.0.1:8126" # example
```

## Options

import Fields from '@site/src/components/Fields';

import Field from '@site/src/components/Field';

<Fields filters={true}>


<Field
  common={true}
  defaultValue={null}
  enumValues={null}
  examples={["127.0.0.1:8126"]}
  name={"address"}
  nullable={false}
  path={null}
  relevantWhen={null}
  required={true}
  templateable={false}
  type={"string"}
  unit={null}
  >

### address

UDP socket address to bind to.


</Field>


</Fields>

## Output

The `statsd` source ingests data through the StatsD UDP protocol and outputs [`metric`][docs.data-model.metric] events.
For example:


import Tabs from '@theme/Tabs';

<Tabs
  block={true}
  defaultValue="counter"
  values={[{"label":"Counter","value":"counter"},{"label":"Gauge","value":"gauge"},{"label":"Set","value":"set"},{"label":"Timer/Histogram","value":"timerhistogram"}]}>

import TabItem from '@theme/TabItem';

<TabItem value="counter">



</TabItem>

<TabItem value="gauge">



</TabItem>

<TabItem value="set">



</TabItem>

<TabItem value="timerhistogram">



</TabItem>
</Tabs>

## How It Works

### Environment Variables

Environment variables are supported through all of Vector's configuration.
Simply add `${MY_ENV_VAR}` in your Vector configuration file and the variable
will be replaced before being evaluated.

You can learn more in the [Environment Variables][docs.configuration#environment-variables]
section.

### Timestamp

StatsD protocol does not provide support for sending metric timestamps. You'll
notice that each parsed metric is assigned a `null` timestamp, which is a
special value which means "a real time metric" (not historical one). Normally such
`null` timestamps will be substituted by current time by downstream sinks or
3rd party services during sending/ingestion. See the [metric][docs.data-model.metric]
data model page for more info.


[docs.configuration#environment-variables]: /docs/setup/configuration/#environment-variables
[docs.data-model.metric]: /docs/about/data-model/metric/
