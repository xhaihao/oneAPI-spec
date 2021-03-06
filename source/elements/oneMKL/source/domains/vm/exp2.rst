
exp2
====


.. container::


   Computes the base 2 exponential of vector elements.


   .. container:: section
      :name: SYNTAX_8AF46B7241F94765A2CAFFAEB423AF8B


      .. rubric:: Syntax
         :class: sectiontitle


      Buffer API:


      .. cpp:function::  void exp2(queue& exec_queue, int64_t n,      buffer<T,1>& a, buffer<T,1>& y, uint64_t mode = mode::not_defined,      error_handler<T> errhandler = {} )

      USM API:


      .. cpp:function::  event exp2(queue& exec_queue, int64_t n, T* a,      T* y, vector_class<event>* depends, uint64_t mode =      mode::not_defined, error_handler<T> errhandler = {} )

      ``exp2`` supports the following precisions.


      .. list-table:: 
         :header-rows: 1

         * -  T 
         * -  ``float`` 
         * -  ``double`` 




.. container:: section
   :name: GUID-27880C73-038D-4C81-8501-16F21AD14F70


   .. rubric:: Description
      :class: sectiontitle


   The exp2 function computes the base 2 exponential of vector elements.


   .. container:: tablenoborder


      .. list-table:: 
         :header-rows: 1

         * -  Data Type 
           -  Threshold Limitations on Input Parameters 
         * -  single precision 
           -  ``a``\ :sub:`i` < log\ :sub:`2`\ (FLT_MAX) 
         * -  double precision 
           -  ``a``\ :sub:`i` < log\ :sub:`2`\ (DBL_MAX) 




   .. container:: tablenoborder


      .. list-table:: 
         :header-rows: 1

         * -  Argument 
           -  Result 
           -  Error Code 
         * -  +0 
           -  +1 
           -    
         * -  -0 
           -  +1 
           -    
         * -  ``a`` > overflow 
           -  +∞ 
           -  ``status::overflow`` 
         * -  ``a`` < underflow 
           -  +0 
           -  ``status::underflow`` 
         * -  +∞ 
           -  +∞ 
           -    
         * -  -∞ 
           -  +0 
           -    
         * -  QNAN 
           -  QNAN 
           -    
         * -  SNAN 
           -  QNAN 
           -    




.. container:: section
   :name: GUID-8D31EE70-939F-4573-948A-01F1C3018531


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
      `set_mode <setmode.html>`__
      function for possible values and their description. This is an
      optional parameter. The default value is ``mode::not_defined``.


   errhandler
      Sets local error handling mode for this function call. See the
      `create_error_handler <create_error_handler.html>`__
      function for arguments and their descriptions. This is an optional
      parameter. The local error handler is disabled by default.


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
      the `set_mode <setmode.html>`__
      function for possible values and their description. This is an
      optional parameter. The default value is ``mode::not_defined``.


   errhandler
      Sets local error handling mode for this function call. See the
      `create_error_handler <create_error_handler.html>`__
      function for arguments and their descriptions. This is an optional
      parameter. The local error handler is disabled by default.


.. container:: section
   :name: GUID-08546E2A-7637-44E3-91A3-814E524F5FB7


   .. rubric:: Output Parameters
      :class: sectiontitle


   Buffer API:


   y
      The buffer ``y`` containing the output vector of size ``n``.


   USM API:


   y
      Pointer ``y`` to the output vector of size ``n``.


   return value (event)
      Function end event.


.. container:: section
   :name: GUID-C97BF68F-B566-4164-95E0-A7ADC290DDE2


   .. rubric:: Example
      :class: sectiontitle


   An example of how to use exp2can be found in the oneMKL installation
   directory, under:


   ::


      examples/sycl/vml/vexp2.cpp


.. container:: familylinks


   .. container:: parentlink


      **Parent topic:** `Exponential and Logarithmic
      Functions <exponential-and-logarithmic-functions.html>`__


