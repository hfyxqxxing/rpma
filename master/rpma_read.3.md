---
layout: manual
Content-Style: 'text/css'
title: LIBRPMA
collection: librpma
date: rpma API version 0.0
...

[comment]: <> (SPDX-License-Identifier: BSD-3-Clause)
[comment]: <> (Copyright 2020, Intel Corporation)

NAME
====

**rpma\_read** - initialize the read operation

SYNOPSIS
========

          #include <librpma.h>

          int rpma_read(struct rpma_conn *conn,
                  struct rpma_mr_local *dst, size_t dst_offset,
                  struct rpma_mr_remote *src,  size_t src_offset,
                  size_t len, int flags, void *op_context);

DESCRIPTION
===========

Initialize the read operation (transferring data from the remote memory
to the local memory).

ERRORS
======

**rpma\_read**() can fail with the following errors:

-   RPMA\_E\_INVAL - *conn*, *dst* or *src* is NULL

-   RPMA\_E\_INVAL - *flags* are not set

-   RPMA\_E\_PROVIDER - **ibv\_post\_send**(3) failed