Solving a Linear Difference Equation
====================================

As an example of a difference equation, we study a backward rectangle approximation of an integral.  Let :math:`x(k)` be the value of the integral at point :math:`k` and similarly :math:`x(k-1)` is the value at point :math:`k-1`, and so on.  Let the value of the function at point :math:`k` be given as :math:`y(k)`.  Then the value of the backward rectangle approximation at point :math:`k` can be expressed as:

.. TODO: define T here

.. math::

    x(k) = x(k-1) + T y(k-1)

.. image:: ../images/backwardrect.png
    :scale: 15%

Although this problem could be solved via backward substitution and basic algebra [#fdiff1]_, this approach will not solve all linear difference equations.  Instead, we will examine how to use z-transforms to solve linear difference equations.  This method makes extensive use of the time-shift properties described above.

The first step to solving a simple linear difference equation, :math:`x(k) = f\bigl(x(k-1), x(k-2), \dots, u(k), u(k-1), \dots \bigr)`, with z-transforms is to take the z-transform.  Then you should combine elements (time-shift properties allow everything to be expressed only in terms of :math:`X(z)`) and leave the equation in the form :math:`X(z)=f(z)` where :math:`f(z)` is some function.  We can then take the inverse z-transform of :math:`X(z) = f(z)` to get a functional form of :math:`x(k)` in terms of only :math:`k`.

Let's now return to solving the example backward rectangle approximation from before.  Let the equation we are taking the integral of be :math:`y(k) = k^2 + 1` from 0 to 2 in 1 unit steps. Thus :math:`T=1`.

.. math::

    x(k) &= x(k-1) + y(k-1) \\
    x(k) - x(k-1) &= y(k-1) \\
    X(z) - z^{-1} X(z) &= z^{-1} Y(k)\\
    X(z) &= \frac{z^{-1}}{1 - z^{-1}} Y(z) \\
    x(k) &= u[n] y(k)

Now, since we already know what :math:`n` and :math:`y(k)` are [#fdiff2]_, we can simply plug in the values we need.

.. math::

    x(k) = u[0] (k^2 + 1)

This is the solution to the linear difference equation.

.. TODO: maybe give an example where T \ne 1? Just suggesting it because to understand the equation I had to do that myself.

.. [#fdiff1] Doing this yields  :math:`x(k) = x(0) + T \sum_{j=0}^{k-1} y(j)`.
.. [#fdiff2] Since we are integrating from 0 to 2,   :math:`n=0` and we are given a function :math:`y(k) = k^2 + 1`
