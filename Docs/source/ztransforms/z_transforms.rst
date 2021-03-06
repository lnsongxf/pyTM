****************************
Introduction to Z-Transforms
****************************

.. contents::
    :depth: 3

.. toctree::
    :hidden:

    definition
    transform_table
    inverse_trans
    properties
    difference_eq
    pv

This lecture describes the z-transform.  

A useful set of tricks for simplifying problems involving *sequences*

Applications include

* Easily computing a *convolution* of two sequences

   * A nonnegative sequence :math:`p = \{p_n\}_{n=0}^\infty` with :math:`\sum_{n=0}^\infty p_n =1` is a discrete probability density
   
   * If discrete random variable :math:`x` has probability density :math:`p` and discrete random variable :math:`y` has probability density :math:`g`, 
     then the sum :math:`x+y` has probability density :math:`p*g` where :math:`*` denotes *convolution*
   
* Solving *linear difference equations*

    * These express restrictions on elements of a sequence at two or more different dates
    
    * Solving means finding a sequence that satisfies the restrictions

* Computing *present values* of sequences

* Providing the mathematical foundations of *lag operators*


.. include:: definition.rst

.. include:: transform_table.rst

.. include:: inverse_trans.rst

.. include:: properties.rst

.. include:: difference_eq.rst

.. include:: pv.rst
