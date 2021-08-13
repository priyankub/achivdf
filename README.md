# Achi VDF

## Building a wheel

Compiling achivdf requires cmake, boost and GMP/MPIR.

```bash
python3 -m venv venv
source venv/bin/activate

pip install wheel setuptools_scm pybind11
pip wheel .
```

## Building Timelord and related binaries

In addition to building the required binary and source wheels for Windows,
MacOS and Linux, achivdf can be used to compile vdf_client and vdf_bench.
vdf_client is the core VDF process that completes the Proof of Time submitted
to it by the Timelord. The repo also includes a benchmarking tool to get a
sense of the iterations per second of a given CPU called vdf_bench. Try
`./vdf_bench square_asm 250000` for an ips estimate.

To build vdf_client set the environment variable BUILD_VDF_CLIENT to "Y".
`export BUILD_VDF_CLIENT=Y`.

Similarly, to build vdf_bench set the environment variable BUILD_VDF_BENCH to
"Y". `export BUILD_VDF_BENCH=Y`.

If you're running a timelord, the following tests are available, depending of which type of timelord you are running:

`./1weso_test`, in case you're running in sanitizer_mode.

`./2weso_test`, in case you're running a timelord that extends the chain and you're running the slow algorithm.

`./prover_test`, in case you're running a timelord that extends the chain and you're running the fast algorithm.

Those tests will simulate the vdf_client and verify for correctness the produced proofs.

## Background from prior VDF competitions

Copyright 2018 [Ilya Gorodetskov](http://www.sundersoft.com/)
generic@sundersoft.com

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

[http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0)

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.