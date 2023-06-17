# Infra Patches

Sometimes there is something running on the infra, that needs patching.
This repository contains those patches.

Why another repo?
As it is mostly binaries, and mostly temporary till upstream fixes the issue.
And otherwise it ends up in the history of the infra repository, making it slow for-ever.

## Patches

Use these patches at your own risk.
They are not meant for public usage; purely meant for OpenTTD's infrastructure.
#You have no guarantees what these binaries actually do

- Nomad has the following patches applied on v1.5.6:
  - an issue with cgroup v2 causes `exec` jobs to lose access to `/dev`.
    https://github.com/hashicorp/nomad/pull/17535 addresses the issue.
  - no CPU counters were available, making it easy to miss actual CPU
    usage on the cluster.
    https://github.com/hashicorp/nomad/pull/17579 addresses the issue.
  - `cpu_total_compute` is not used to calculate CPU usage (only
    scheduling).
    https://github.com/hashicorp/nomad/issues/17577 reports this issue,
    and a dirty workaround is applied to Nomad.
