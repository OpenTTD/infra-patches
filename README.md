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

- Nomad: an issue with cgroup v2 causes `exec` jobs to lose access to `/dev`.
  https://github.com/hashicorp/nomad/pull/17535 addresses the issue.
  The binary here is a v1.5.6 recompiled with that patch applied.

