.. SPDX-FileCopyrightText: 2019-2020 Intel Corporation
..
.. SPDX-License-Identifier: CC-BY-4.0

.. _onemath_lapack_orgqr_scratchpad_size:

orgqr_scratchpad_size
=====================

Computes size of scratchpad memory required for :ref:`onemath_lapack_orgqr` function.

.. container:: section

  .. rubric:: Description

``orgqr_scratchpad_size`` supports the following precisions.

    .. list-table:: 
       :header-rows: 1

       * -  T 
       * -  ``float`` 
       * -  ``double`` 

Computes the number of elements of type ``T`` the scratchpad memory to be passed to :ref:`onemath_lapack_orgqr` function should be able to hold.
Calls to this routine must specify the template parameter explicitly.

orgqr_scratchpad_size
---------------------

.. container:: section

  .. rubric:: Syntax
         
.. code-block:: cpp

    namespace oneapi::math::lapack {
      template <typename T>
      std::int64_t orgqr_scratchpad_size(cl::sycl::queue &queue, std::int64_t m, std::int64_t n, std::int64_t k, std::int64_t lda) 
    }

.. container:: section

  .. rubric:: Input Parameters

queue
   Device queue where calculations by :ref:`onemath_lapack_orgqr` function will be performed.

m
   The number of rows in the matrix :math:`A` (:math:`0 \le m`).

n
   The number of columns in the matrix :math:`A` (:math:`0 \le n \le m`).

k
   The number of elementary reflectors whose product defines the
   matrix :math:`Q` (:math:`0 \le k \le n`).

lda
   The leading dimension of ``a``.

.. container:: section

  .. rubric:: Throws
         
This routine shall throw the following exceptions if the associated condition is detected. An implementation may throw additional implementation-specific exception(s) in case of error conditions not covered here.

:ref:`oneapi::math::unimplemented<onemath_exception_unimplemented>`

:ref:`oneapi::math::unsupported_device<onemath_exception_unsupported_device>`

:ref:`oneapi::math::lapack::invalid_argument<onemath_lapack_exception_invalid_argument>`

   Exception is thrown in case of incorrect supplied argument value.
   Position of wrong argument can be determined by `info()` method of exception object.

.. container:: section

  .. rubric:: Return Value
         
The number of elements of type ``T`` the scratchpad memory to be passed to :ref:`onemath_lapack_orgqr` function should be able to hold.

**Parent topic:** :ref:`onemath_lapack-linear-equation-routines`


