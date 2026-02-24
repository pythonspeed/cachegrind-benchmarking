# Benchmarking with Cachegrind (don't use this)

> I no longer think relying on memory caches is a good idea, so I would **recommend against using this script**.
> Instead, just use Cachegrind's CPU instruction count.

[Cachegrind](https://valgrind.org/docs/manual/cg-manual.html) can be used to get [consistent performance results for your benchmarks](https://pythonspeed.com/articles/consistent-benchmarking-in-ci/), allowing you to for example run your benchmarks in noisy VMs or CI runners.

This repository includes a script to help you generate a single combined performance metric using memory cache info from Cachegrind, and get more consistency.

It is designed to run on Linux.

See the code for usage.

## Changelog

### February 2026

Deprecated the repository.

### Dec 22, 2020

* Switched to parsing the Cachegrind output file, rather than parsing the stderr output.
* Fixed a bug that inflated L3 hit counts by double-counting RAM hits as L3 hits.
* Changed cost multiplier for RAM from 30 to 35 to account for the changes from the bug fix.
