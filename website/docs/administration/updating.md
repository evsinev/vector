---
title: Updating
description: Updating Vector to a later version
---

Updating Vector depends largely on your [installation][docs.installation] 
method. Each installation guide provides it's own "Updating" section:

---

**Containers**

import Jump from '@site/src/components/Jump';

<Jump to="/docs/setup/installation/containers/docker#updating">Docker</Jump>

**Package managers**

<Jump to="/docs/setup/installation/package-managers/dpkg#updating">DPKG</Jump>
<Jump to="/docs/setup/installation/package-managers/homebrew#updating">Homebrew</Jump>
<Jump to="/docs/setup/installation/package-managers/rpm#updating">RPM</Jump>

**Manual**

<Jump to="/docs/setup/installation/manual/from-archives#updating">Updating from archives</Jump>
<Jump to="/docs/setup/installation/manual/from-source#updating">Updating from source</Jump>

## Working Upstream

Depending on your [topology][docs.topologies], you'll want update your Vector
instances in a specific order. You should _always_ start downstream and work
your way upstream. This allows for incremental updating across your topology,
ensuring downstream Vector instances do not receive data in formats that are
unrecognized. Vector always makes a best effort to successfully process data,
but there is no guarantee of this if a Vector instance is handling a data
format defined by a future unknown Vector version.

## Capacity Planning

Because you'll be taking Vector instances offline for a short period of time,
upstream data will accumulate and buffer. To avoid overloading your instances,
you'll want to make sure you have enough capacity to handle the surplus of
data. We recommend provisioning at least 20% of head room, on all resources,
to account for spikes and updating.


[docs.installation]: /docs/setup/installation
[docs.topologies]: /docs/setup/deployment/topologies