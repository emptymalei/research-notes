Dispersion Relation and Crossing
===================================


.. admonition:: How to understand Dispersion Relation
   :class: note

   We should come back to the wave picture. DR tells us how easily a wave will disperse as it travels. The things that can be research on are the disperse itself. Stability is one important topic but it also tells us how the wave disperse.


Box Spectrum
-----------------------


.. admonition:: Numerical Issues with Box Spectrum in LSA
   :class: toggle

   Mathematica seems to fail the mission when finding the complex k's given real :math:`\omega`.

   I tested bot NIntegrate of the integrals and Integrate first. It seems that Integrate first works better and faster.

   I ploted out the MZA solutions and check if they have interceptions with the 0 plane. I found that interceptions exsits for only some values of :math:`\omega`. Examples of such plots are shown below.

   .. figure:: assets/dispersion-relation-and-crossing/mzap-solution-3d-plot-spect-wc1.png
      :align: center

      MZA solutions for spectrum id WC1. We could see the spike-like structure in the real part intercepts with 0 plane as well as imaginary part that indicates a solution.

   After some test, my thought is that the integral is nicely behaved for some range of real :math:`\omega`, which makes sense since the line of instability can not extend to arbitary large and small :math:`\omega`.

   Thus the solution to the warnings and errors in FindRoot is to plugin the suitable range of :math:`\omega`.

   Meanwhile for real :math:`k`, we have only solutions at :math:`\omega =0`.

   .. figure:: assets/dispersion-relation-and-crossing/mzap-solution-3d-plot-realk-spect-wc1.png
      :align: center

      For real k, :math:`k=0.8`.

   MAA solutions also has similar shape.

Since box spectrum is easier and faster to calculate, we'll explore the phenomena within box spectrum. For example, the spectrum notation

.. code-block:: Mathematica

   {{{-1, -0.3}, -0.2}, {{-0.3, 1}, 0.7}}

indicates tht the spectrum has a constant value -0.2 within :math:`\cos\theta \in [-1,-0.3]` and value 0.7 within :math:`\cos\theta \in [-0.3,1]`.

.. figure:: assets/dispersion-relation-and-crossing/box-spectra-without-crossing-omega-n-k-n-dr.png
   :align: center

   No crossing




.. figure:: assets/dispersion-relation-and-crossing/box-spectra-with-crossing-omega-n-k-n-dr.png
   :align: center

   With crossing


.. admonition:: Observations and Questions
   :class: warning

   1. Any 0 in spectrum make it possible go cross the singularity line.
   2. MZA disappears at some point of parameters. What are the constraints.


.. admonition:: MZA disappears
   :class: note

   The analytical expression for it to dispear shows that it involves all the elements of the spectrum. Numerically, I can show that for a specific one :math:`\{\{\{-1, -0.3\}, g_1\}, \{\{-0.3, 1\}, 1\}\}`, the region of :math:`g_1` that leads to no MZA solution for a given :math:`n` is shown in :numref:`analytical-where-mza-dispear-spectrum-c5`.

   .. _analytical-where-mza-dispear-spectrum-c5:

   .. figure:: assets/dispersion-relation-and-crossing/analytical-where-mza-dispear-spectrum-c5.png
      :align: center

      Region of :math:`g_1`.

   This figure shows that the MZA solution will come back if we choose really small :math:`g_1`. It is verified using another spectrum which is labeled as C5 spectrum.

   .. figure:: assets/dispersion-relation-and-crossing/omega-n-spectrum-c5.png
      :align: center

      For a spectrum :math:`\{\{\{-1, -0.3\}, -15\}, \{\{-0.3, 1\}, 1\}\}`.


   However examples of numerical calculations won't be enough. Alternatively, I could derive an analytical expression. MZA solution is

   .. math::
      \omega = -\frac{1}{4}\left(I_0-I_2\pm \sqrt{ (I_0-2I_1+I_2)(I_0+2I_1+I_2) }\right).

   We examine the term inside square root and set it to be negative which will show us the region where real omega disppears.


   Comment: the upper limit is not a horizontal line.

   .. figure:: assets/dispersion-relation-and-crossing/omega-n-upper-limit-spectrum-c5.png
      :align: center

      Upper limit.

   For the MZA solutions to disappear, we need to find the smallest value of the upper limit (-0.73160 in this case) and the largest value of lower limit (-7.16327 in this case).


.. admonition:: Taylor Expansion of MZA solutions
   :class: note

   What about Taylor expansion around small values of :math:`g_1`? Taylor expanding the most general abstract form doesn't give us any useful results since it is super complicated.

   .. figure:: assets/dispersion-relation-and-crossing/mza-solutions-taylor-series-coefficients-spect-c5.png
      :align: center

      Coefficients of Taylor series of MZA solutions. It's weird that the coefficients are all real.

   I am not sure how to use these results.


.. admonition:: Crossing has an effect on :math:`d\omega/dn`
   :class: note


   By observing the :math:`\omega\sim n` plot, we noticed that crossing is changes the behavior of it, especially at the point :math:`n=-1`. It seems that crossing changes whether the :math:`\omega` goes to :math:`\infty` or :math:`-\infty` at :math:`n=-1`.

   .. figure:: assets/dispersion-relation-and-crossing/box-spectra-mza-g1-n-shortrange.png
      :align: center

      :math:`d\omega/dn` for MZA solutions with spectrum :math:`spectAbs2 = \{\{\{-1, -0.3\}, g_1\}, \{\{-0.3, 1\}, 1\}\}`. In this plot, we have :math:`g_1\in [-1,1]` with a step size 0.1 while :math:`n\in [-1,1]`. We notice that the value at -1 changes as crossing happens.

   More specifically, we plot out the :math:`d\omega/dn` for three different :math:`g_1`.

   .. figure:: assets/dispersion-relation-and-crossing/box-spectra-mza-n-g1-three-values-including-crossing.png
      :align: center

      for 3 different values of :math:`g_1`. The second panel is for :math:`g_1=0`. The grid lines are actually calculated using Limit which are :math:`-0.0143723` and :math:`0.0370502`. They never become 0?


Instabilities
--------------------------

.. admonition:: Crossing seems to have little effects on instabilities
   :class: warning

   Instabilities on DR plot seems to be NOT affected by crossing. Probably because of the lines in the forbidden region (using abs for log argument in the results of integral for I's) doesn't seem to change a lot.
