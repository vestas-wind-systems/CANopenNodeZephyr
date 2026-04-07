# CANopenNode Protocol Stack for Zephyr RTOS

## Introduction

[CANopenNode](https://github.com/CANopenNode/CANopenNode) is free and open source CANopen protocol
stack. This repository provides glue code for integrating the stack with the [Zephyr
Project](https://github.com/zephyrproject-rtos/zephyr). CANopenNode itself is included as a Git
submodule.

Both CANopenNode and CANopenNodeZephyr are licensed under the Apache-2.0 license.

## CANopenNode as a Zephyr Module

To pull in CANopenNodeZephyr as a Zephyr module, either add it as a West project in the `west.yaml`
file or pull it in by adding a submanifest (e.g. `zephyr/submanifests/canopennodezephyr.yaml`) file
with the following content and run `west update`:

```yaml
manifest:
  projects:
    - name: canopennodezephyr
      url: https://github.com/vestas-wind-systems/CANopenNodeZephyr.git
      revision: main
      submodules:
        - path: CANopenNode
      path: custom/canopennodezephyr # adjust the path as needed
```
