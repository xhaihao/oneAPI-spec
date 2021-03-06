..
  Copyright 2019-2020 Intel Corporation

.. default-domain:: cpp

.. namespace:: 0

######
Memory
######

There are two levels of abstraction for memory in oneDNN.

1. *Memory descriptor* -- engine-agnostic logical description of data (number
   of dimensions, dimension sizes, :ref:`data type <data_types-label>`, and
   :ref:`format <memory_formats-label>`.

2. *Memory object* -- an engine-specific object combines memory descriptor
   with storage.

oneDNN defines the following convenience aliases to denote tensor dimensions

.. doxygentypedef:: dnnl::memory::dim
   :project: oneDNN

.. doxygentypedef:: dnnl::memory::dims
   :project: oneDNN

.. toctree::

   formats.rst
   objects.rst

.. vim: ts=3 sw=3 et spell spelllang=en

