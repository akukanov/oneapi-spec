.. SPDX-FileCopyrightText: 2019-2020 Intel Corporation
..
.. SPDX-License-Identifier: CC-BY-4.0

.. _onemath_vm_modf:

modf
====


.. container::


   Computes a truncated integer value and the remaining fraction part
   for each vector element.


   .. container:: section


      .. rubric:: Syntax
         :class: sectiontitle


      Buffer API:


      .. code-block:: cpp


            namespace oneapi::math::vm {

            sycl::event modf(
                    sycl::queue& exec_queue,
                    std::int64_t n,
                    sycl::buffer<T,1>& a,
                    sycl::buffer<T,1>& y,
                    sycl::buffer<T,1>& z,
                    oneapi::math::vm::mode mode = oneapi::math::vm::mode::not_defined);

            } // namespace oneapi::math::vm



      USM API:


      .. code-block:: cpp


            namespace oneapi::math::vm {

            sycl::event modf(
                    sycl::queue& exec_queue,
                    std::int64_t n,
                    const T *a,
                    T* y,
                    T* z,
                    std::vector<sycl::event> const & depends = {},
                    oneapi::math::vm::mode mode = oneapi::math::vm::mode::not_defined);

            } // namespace oneapi::math::vm



      ``modf`` supports the following precisions.


      .. list-table::
         :header-rows: 1

         * - T
         * - ``float``
         * - ``double``




.. container:: section


   .. rubric:: Description
      :class: sectiontitle


   The modf(a) function computes a truncated integer value and the
   remaining fraction part for each vector element.


   .. math::
      a_i \geq 0,
      \begin{cases}
         y_i = \lfloor a_i \rfloor \\
         z_i = a_i - \lfloor a_i \rfloor
      \end{cases}

      a_i < 0,
      \begin{cases}
         y_i = \lceil a_i \rceil \\
         z_i = a_i - \lceil  a_i \rceil
      \end{cases}


   .. container:: tablenoborder


      .. list-table::
         :header-rows: 1

         * - Argument
           - Result 1
           - Result 2
           - Status code
         * - +0
           - +0
           - +0
           -  
         * - -0
           - -0
           - -0
           -  
         * - +∞
           - +∞
           - +0
           -  
         * - -∞
           - -∞
           - -0
           -  
         * - SNAN
           - QNAN
           - QNAN
           -  
         * - QNAN
           - QNAN
           - QNAN
           -  




   The modf function does not generate any errors.


.. container:: section


   .. rubric:: Input Parameters
      :class: sectiontitle


   Buffer API:


   exec_queue
      The queue where the routine should be executed.


   n
      Specifies the number of elements to be calculated.


   a
      The buffer ``a`` containing input vector of size ``n``.


   mode
      Overrides the global VM mode setting for this function call. See
      :ref:`onemath_vm_setmode`
      function for possible values and their description. This is an
      optional parameter. The default value is ``oneapi::math::vm::mode::not_defined``.


   USM API:


   exec_queue
      The queue where the routine should be executed.


   n
      Specifies the number of elements to be calculated.


   a
      Pointer ``a`` to the input vector of size ``n``.


   depends
      Vector of dependent events (to wait for input data to be ready).


   mode
      Overrides the global VM mode setting for this function call. See
      the :ref:`onemath_vm_setmode`
      function for possible values and their description. This is an
      optional parameter. The default value is ``oneapi::math::vm::mode::not_defined``.


.. container:: section


   .. rubric:: Output Parameters
      :class: sectiontitle


   Buffer API:


   y
      The buffer ``y`` containing the output vector of size ``n`` for
      truncated integer values.


   z
      The buffer ``z`` containing the output vector of size ``n`` for
      remaining fraction parts.


   USM API:


   y
      Pointer ``y`` to the output vector of size ``n`` for truncated
      integer values.


   z
      Pointer ``z`` to the output vector of size ``n`` for remaining
      fraction parts.


   return value (event)
      Event, signifying availability of computed output and status code(s).

.. container:: section


    .. rubric:: Exceptions
        :class: sectiontitle

    For list of generated exceptions please refer to  :ref:`onemath_vm_exceptions`


.. container:: familylinks


   .. container:: parentlink

      **Parent topic:** :ref:`onemath_vm_mathematical_functions`
