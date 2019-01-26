.. meta::
   :description: Compile Axe Core for Linux, macOS, Windows and Gitian deterministic builds
   :keywords: axe, build, compile, linux, Jenkins, macOS, windows, binary, Gitian, developers

.. _compiling-axe:

===================
Compiling Axe Core 
===================

While Axe offers stable binary builds on the `website
<https://www.axerunners.com/wallets>`_ and on `GitHub
<https://github.com/axerunners/axe/releases>`_, and development builds
using `Jenkins <https://jenkins.docs.axerunners.com/blue/organizations/jenkins/axerunners-axe-gitian-nightly/activity/>`_, 
many users will also be interested in building Axe binaries for
themselves. This process has been greatly simplified with the release of
Axe Core 0.13.0, and users who do not required deterministic builds can
typically follow the `generic build notes <https://github.com/axerunners/axe/blob/develop/doc/build-generic.md>`__
available on GitHub to compile or cross-compile Axe for any platform.

The instructions to build Axe Core 0.12.3 or older are available `here
<https://docs.axerunners.com/en/0.12.3/developers/compiling.html>`__ on a
previous version of this page.

.. _gitian-build:

Gitian
======

Gitian is the deterministic build process that is used to build the Axe
Core executables. It provides a way to be reasonably sure that the
executables are really built from the source on GitHub. It also makes
sure that the same, tested dependencies are used and statically built
into the executable. Multiple developers build the source code by
following a specific descriptor ("recipe"), cryptographically sign the
result, and upload the resulting signature. These results are compared
and only if they match, the build is accepted and uploaded to docs.axerunners.com.

Instructions on how to build Axe Core 0.13.0 will appear here once the
Docker build system for Gitian is available. Instructions to create
deterministic builds of Axe Core 0.12.3 or older are available `here
<https://docs.axerunners.com/en/0.12.3/developers/compiling.html#gitian-build>`__ 
on a previous version of this page.
