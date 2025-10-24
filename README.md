# P4TV

This repository contains the implementation of our approach described in the paper *"On Temporal Verification of Stateful P4 Programs," NSDI '25*.

## Building

We have tested P4TV on the Ubuntu 20.04 platform. While other platforms are untested, you are welcome to try them, but YMMV.

Before running P4TV, two components must be built:

1. [P4LTL-Translator](https://github.com/NVThufv/P4LTL-Translator)
2. [P4LTL-Validator](https://github.com/NVThufv/P4LTL-Validator)

## Verifying P4LTL

Before verification, please **make sure that both `P4LTL-Translator` and `P4LTL-Validator` have been successfully built**.

The `Check.sh` script used for verification is located in the **P4LTL-Validator** repository under:

```
trunk/examples/P4LTL/Check.sh
```

Ensure that this script is included in your `PATH` environment variable before running.

To verify a property, execute:

```bash
$ Check.sh example.p4 example.p4ltl
```

This checks whether the P4 program (`example.p4`) satisfies the P4LTL property (`example.p4ltl`).

For detailed setup and usage instructions, **please refer to the README files** of both
 👉 [P4LTL-Translator](https://github.com/NVThufv/P4LTL-Translator) and
 👉 [P4LTL-Validator](https://github.com/NVThufv/P4LTL-Validator).

If successful, the validator should report a counterexample violating a simple property like:
 *"The packet will eventually be dropped,"* showing a trace where packets are continually forwarded.
