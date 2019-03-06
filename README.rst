========================
Team and repository tags
========================

.. image:: https://governance.openstack.org/tc/badges/osprofiler.svg
    :target: https://governance.openstack.org/tc/reference/tags/index.html

.. Change things from this point on

===========================================================
 OSProfiler -- Library for cross-project profiling library
===========================================================

.. image:: https://img.shields.io/pypi/v/osprofiler.svg
    :target: https://pypi.org/project/osprofiler/
    :alt: Latest Version

.. image:: https://img.shields.io/pypi/dm/osprofiler.svg
    :target: https://pypi.org/project/osprofiler/
    :alt: Downloads

OSProfiler provides a tiny but powerful library that is used by
most (soon to be all) OpenStack projects and their python clients. It
provides functionality to be able to generate 1 trace per request, that goes
through all involved services. This trace can then be extracted and used
to build a tree of calls which can be quite handy for a variety of
reasons (for example in isolating cross-project performance issues).

* Free software: Apache license
* Documentation: https://docs.openstack.org/osprofiler/latest/
* Source: https://git.openstack.org/cgit/openstack/osprofiler
* Bugs: https://bugs.launchpad.net/osprofiler
* Release notes: https://docs.openstack.org/releasenotes/osprofiler

================
Docc-lab Changes
================

* Disable sqlalchemy tracing
* Added `--since` to `osprofiler list`
* Added `tracepoint_id` to spans. Only works fully for redis backend.
    * For normal traces, location of function and full function name with class etc.
    * For web calls, path that is called and request type
* Disabled `loginsight` backend
* Added sampling rate
* Global variables at `osprofiler/profiler.py`:
    * `CREATE_MANIFEST`: create a file for each tracepoint encountered
    * `TRACE_NEWTHREAD`: trace thread creation events
    * `SKELETON_ONLY`: only collect thread creation events
* Added `profiler.annotate` to add annotations to traces
* Added ability to enable/disable tracepoints. Works by reading manifest files at each tracepoint
* Fixed metaclass/builtin method tracing. These traces work correctly now. Can turn into a pull request to upstream.
