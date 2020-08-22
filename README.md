# ceph-experiments
ceph-experiments
Please see http://ceph.com/ for current info.


# Ceph - a scalable distributed storage system


Most of Ceph is dual licensed under the LGPL version 2.1 or 3.0. Some miscellaneous code is under BSD-style license or is public domain. The documentation is licensed under Creative Commons Attribution Share Alike 3.0 (CC-BY-SA-3.0). There are a handful of headers included here that are licensed under the GPL. Please see the file COPYING for a full inventory of licenses by file.

Code contributions must include a valid "Signed-off-by" acknowledging the license for the modified or contributed file. Please see the file SubmittingPatches.rst for details on what that means and on how to generate and submit patches.

We do not require assignment of copyright to contribute code; code is contributed under the terms of the applicable license.

# Checking out the source

You can clone from github with

`git clone git@github.com:ceph/ceph`


or, if you are not a github user,
`git clone git://github.com/ceph/ceph`

# Build Prerequisites

The list of Debian or RPM packages dependencies can be installed with:

Note that these instructions are meant for developers who are compiling the code for development and testing. To build binaries suitable for installation we recommend you build deb or rpm packages, or refer to the `ceph.spec.in` or `debian/rules` to see which configuration options are specified for production builds.

Build instructions:

`./do_cmake.sh
cd build
make`


(Note: `do_cmake.sh` now defaults to creating a debug build of ceph that can be up to 5x slower with some workloads. Please pass "-DCMAKE_BUILD_TYPE=RelWithDebInfo" to do_cmake.sh to create a non-debug release.)


(Note: `make` alone will use only one CPU thread, this could take a while. use the `-j` option to use more threads. Something like make `-j$(nproc)`  would be a good start.
