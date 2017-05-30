Dispersion Relation and Gap
===============================


.. admonition:: Question about MZA solutions
   :class: warning

   I seems that we should do Taylor expansion around :math:`omega=0` for MZA solutions to see what actually is happening. We can expand the :math:`I_m`'s around small real :math:`\omega`, then perform the integral.


Discrete Beams
-------------------


I define the following beams,

.. code-block:: Mathematica

   spectDBWC1 = {{1, -0.6}, {1, 0.1}, {1, 0.6}}
   spectDBWC2 = {{0.5, -0.6}, {1, 0.1}, {1, 0.6}}
   spectDBWC3 = {{0.1, -0.6}, {1, 0.1}, {1, 0.6}}

   spectDBC1 = {{-1, -0.6}, {1, 0.1}, {1, 0.6}}
   spectDBC2 = {{-0.5, -0.6}, {1, 0.1}, {1, 0.6}}
   spectDBC3 = {{-0.1, -0.6}, {1, 0.1}, {1, 0.6}}


The first thing is to really see that the instability regions are going through the gap in discrete beams case.

.. figure:: assets/dispersion-relation-gap/lsaMAAROPltDB-WC1-to-WC3.png
   :align: center

   MAA solutions for spectra WC1, WC2, WC3. The instability regions go through the gap.


.. figure:: assets/dispersion-relation-gap/lsaMAAROPltDB-C1-to-C3.png
   :align: center

   MAA solutions for spectra C1, C2, C3. For real :math:`\omega`, no complex k is found.


The MZA+ solution can also be found.

.. figure:: assets/dispersion-relation-gap/lsaMZApROPltDB-WC1-to-WC3.png
   :align: center

   MZA+ solution for WC spectra.


.. figure:: assets/dispersion-relation-gap/lsaMZApROPltDB-C1-to-C3.png
   :align: center

   MZA+ solution for C spectra. As like before, no instability in k is found.

The MZA- solutions:

.. figure:: assets/dispersion-relation-gap/lsaMZAmROPltDB-WC1-to-WC3.png
   :align: center

   MZA- solution for WC spectra.


.. figure:: assets/dispersion-relation-gap/lsaMZAmROPltDB-C1-to-C3.png
   :align: center

   MZA- solution for C spectra.


So the C spectra have no instabilities in k. I should calculate the instabilities in :math:`\omega` for real k.


.. figure:: assets/dispersion-relation-gap/lsaMAARKPltDB-WC1-to-WC3-and-C1-to-C3.png
   :align: center

   MAA solution for real k finding complex :math:`\omega`.


.. figure:: assets/dispersion-relation-gap/lsaMZApRKPltDB-WC1-to-WC3-and-C1-to-C3.png
   :align: center

   MZA+ solution for real k finding complex :math:`\omega`.




.. figure:: assets/dispersion-relation-gap/lsaMZAmRKPltDB-WC1-to-WC3-and-C1-to-C3.png
   :align: center

   MZA- solution for real k finding complex :math:`\omega`.




Two Beams
-------------------------------------


For two beams, the equation :math:`f(\omega,k)=0` is quadratic in both :math:`\omega` and :math:`k`, thus two solutions everywhere even for complex solutions.


.. admonition:: Infinities at Emission Angle
   :class: note

   It has been a very weird thing that the MZA DR lines can cross the forbidden lines defined by the emission angle. To illustrate this problem, we think of a two beams model, with spectrum :math:`\{\{g_1,u_1\},\{g_2,u_2\}\}`.

   The equation for DR has terms of the form

   .. math::
      \frac{1}{1-n u_i},

   which indicates that this can lead to infinity when :math:`n=1/u_i`, unless the numerator is 0. For MAA solution, the numerator indeed becomes 0. But for MZA solution it is not that obvious.

   However, we can prove that one of the MZA solutions is still finite as :math:`n=1/u_i`.

   The MZA solution is

   .. math::
      \omega(n) = -\frac{1}{4} \left(  I_0 - I_2 \pm \sqrt{  (I_0+I_2 - 2I_1)(I_0+I_2 + 2I_1) } \right),

   where

   .. math::
      I_m = \sum g_i \frac{ u_i^m }{1 - m u_i}.

   We are interested in wether the term

   .. math::
      I_0 - I_2 \pm \sqrt{  (I_0+I_2 - 2I_1)(I_0+I_2 + 2I_1) }

   will become finite at :math:`n=1/u_i`. We plug in the expressions for :math:`I_m`.

   .. math::
      &I_0 - I_2 \pm \sqrt{  (I_0+I_2 - 2I_1)(I_0+I_2 + 2I_1) } \\
      =&\sum_i \frac{ g_i(1-u_i^2) }{1-n u_i} \pm \sqrt{ \left( \sum_i \frac{ g_i(u_i-1)^2 }{ 1- nu_i } \right) \left( \sum_i \frac{ g_i(u_i+1)^2 }{ 1- nu_i } \right) } \\
      =& \frac{ g_1 (1-u_1^2)(1-n u_2) + g_2(1-u_2^2)(1-n u_1) }{ (1-n u_1)(1-n u_2) } \pm \sqrt{  \frac{ [ g_1 (1-u_1)^2 (1-n u_2) + g_2 (1-u_2)^2 (1-n u_1) ][ g_1 (1+u_1)^2 (1-n u_2) + g_2 (1+u_2)^2 (1-n u_1) ] }{ (1-n u_1)^2(1-n u_2)^2 } }.

   We take the limit :math:`n\to 1/u_i`.

   .. math::
      &I_0 - I_2 \pm \sqrt{  (I_0+I_2 - 2I_1)(I_0+I_2 + 2I_1) } \\
      =& \frac{ g_1(1-u_1^2) }{ 1- n u_1 } \pm  \left\lvert \frac{ g_1(1-u_1^2)  }{  1 - n u_1  } \right\rvert.

   One of the solutions, + or -, will be 0, depending on spectrum and also which side we are approaching the limit.

   Suppose we have :math:`g_1>0` and :math:`n\to 1/u_1 +` (:math:`1-n u_1<0`).

   .. math::
      \omega(n) = \frac{ g_1(1-u_1^2) }{ 1- n u_1 } \pm  \left(  - \frac{ g_1(1-u_1^2)  }{  1 - n u_1  }  \right),

   so that the MZA+ solution is 0.


Solutions
-----------------------------------

It seems that gap and instability are not really related all the time. For discrete beams, the number of solutions is the key to instabilities.

It shows that spectrum :math:`DBC1` has only MZA+ instabilities on the left side of the axis for real k. We need to prove that no solutions are found on the left side of the axis. Similarly for MZA- solutions but on different sides.


Discrete Beams
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

MAA
``````````````````````

For ``spectDBWC1`` we have the following density plots of :math:`f(\omega=0.1,k)`, :math:`f(\omega=0.5,k)`, and :math:`f(\omega=1.5,k)` respectively.

.. image:: assets/dispersion-relation-gap/f-of-omega-0.1-and-k-densityplot-log-maa-spectdbwc1.png
   :width: 32%

.. image:: assets/dispersion-relation-gap/f-of-omega-0.5-and-k-densityplot-log-maa-spectdbwc1.png
   :width: 32%

.. image:: assets/dispersion-relation-gap/f-of-omega-1.5-and-k-densityplot-log-maa-spectdbwc1.png
   :width: 32%


Similar plots are made for ``spectDBC1`` which has no MAA instabilities.


.. image:: assets/dispersion-relation-gap/f-of-omega-0.1-and-k-densityplot-log-maa-spectdbc1.png
   :width: 32%


.. image:: assets/dispersion-relation-gap/f-of-omega-0.5-and-k-densityplot-log-maa-spectdbc1.png
   :width: 32%


.. image:: assets/dispersion-relation-gap/f-of-omega-1.5-and-k-densityplot-log-maa-spectdbc1.png
   :width: 32%

MZA
``````````````````````


I can also plot out the MZA solutions.

.. figure:: assets/dispersion-relation-gap/f-of-omega-0.1-and-k-densityplot-log-mzap-mazm-spectdbwc1.png
   :align: center

   MZA solutions (MZA+ left, MZA- right) for ``spectDBWC1`` with :math:`\omega=0.1`. The MZA+ plot on the left seems to be weird. I checked the values within this region. There is a plateau here but not exactly flat. And they are not approaching 0. The other real solution in MZA- solution which is not shown is pretty far away from these two complex solutions.


A closer look at the MZA- solutions are showed below.

.. figure:: assets/dispersion-relation-gap/f-of-omega-0.1-and-k-densityplot-log-mazm-spectdbwc1-2.png
   :align: center

   MZA- solutions for ``spectDBWC1`` at a closer look at the 0 points. The white bands are regions slightly larger than 0. ``Log@Abs@DBAxialSymOmegaNMZApEqnLHSComplex[0.1, -0.1826 - 0*I, spectDBWC1]`` returns ``0.475377``.

.. admonition:: Check Values at Plateau
   :class: toggle

   .. code-block:: Mathematica

      In[162]:= Log@Abs@DBAxialSymOmegaNMZApEqnLHSComplex[0.1, 1.6 - 1*I, spectDBWC1]
      Log@Abs@DBAxialSymOmegaNMZApEqnLHSComplex[0.1, 1.2 - 1*I, spectDBWC1]

      Out[162]= -2.46077
      Out[163]= -2.49663

   A sharp transition occurs at the white boundry. The values near the boundary change abruptly. According to the values :math:`f(\omega=0.1,k)`, imaginary part of it appears and becomes large as we move from left to right around the boundary.

   .. figure:: assets/dispersion-relation-gap/f-of-omega-0.1-and-k-densityplot-log-mzap-spectwc1-at-step-structure.png
      :align: center

      LogPlot of :math:`|f(\omega=0.1,k=kreal-0.8386*I)|` for :math:`kreal\in [1.052, 1.0535]`. This region of plot goes across the step structure.

   .. code-block:: Mathematica


      LogPlot[Abs@DBAxialSymOmegaNMZApEqnLHSComplex[0.1, kreal - 0.8386*I,  spectDBWC1], {kreal, 1.052, 1.0535}, Frame -> True, PlotLabel -> "|f(\[Omega]=0.1,k=kreal-0.8386*I)| for spectDBWC1"]


For :math:`\omega=-0.5`.




.. figure:: assets/dispersion-relation-gap/f-of-omega-m0.5-and-k-densityplot-log-mzap-mazm-spectdbwc1.png
   :align: center

   MZA solutions (MZA+ left, MZA- right) for ``spectDBWC1`` with :math:`\omega=-0.5`.

.. figure:: assets/dispersion-relation-gap/f-of-omega-m0.5-and-k-densityplot-log-mazm-spectdbwc1-2.png
   :align: center

   MZA- solution around the real solution. ``Log@Abs@DBAxialSymOmegaNMZApEqnLHSComplex[-0.5, -1.99 - 0*I, spectDBWC1]`` returns ``-5.18447`` which indicates a 0 point.





Box Spectra
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

.. figure:: assets/dispersion-relation-gap/f-of-omega-0.1-and-k-densityplot-log-maa-spectwc3.png
   :align: center

   MAA ``spectWC3`` for :math:`\omega=0.1`. We have points or regions approaching :math:`f(\omega=0.1,k)\to 0`.




f-of-omega-m0.1-and-k-densityplot-log-maa-spectwc3.png



.. figure:: assets/dispersion-relation-gap/f-of-omega-m0.1-and-k-densityplot-log-maa-spectwc3.png
   :align: center

   MAA ``spectWC3`` for :math:`\omega=-0.1`. How do I determine whether it is approaching 0? I change the plot range and checked. :math:`e^{-2.3}` seems to be the smallest value.





.. figure:: assets/dispersion-relation-gap/f-of-omega-1-and-k-densityplot-log-maa-spectwc3.png
   :align: center

   MAA ``spectWC3`` for :math:`\omega=1`. It seems that the solutions to k are real.



Similar plots are made for ``spectWC4``.

.. figure:: assets/dispersion-relation-gap/f-of-omega-0.1-and-k-densityplot-log-maa-spectwc4.png
   :align: center

   MAA ``spectWC4`` for :math:`\omega=0.1`.



.. figure:: assets/dispersion-relation-gap/f-of-omega-m0.1-and-k-densityplot-log-maa-spectwc4.png
   :align: center

   MAA ``spectWC4`` for :math:`\omega=-0.1`.





.. figure:: assets/dispersion-relation-gap/f-of-omega-1-and-k-densityplot-log-maa-spectwc4.png
   :align: center

   MAA ``spectWC4`` for :math:`\omega=-0.1`.






.. figure:: assets/dispersion-relation-gap/f-of-omega-0.1-and-k-densityplot-log-maa-spectc1.png
   :align: center

   MAA ``spectC1`` for :math:`\omega=0.1`.




.. figure:: assets/dispersion-relation-gap/f-of-omega-m0.1-and-k-densityplot-log-maa-spectc1.png
   :align: center

   MAA ``spectC1`` for :math:`\omega=-0.1`.






.. figure:: assets/dispersion-relation-gap/f-of-omega-1-and-k-densityplot-log-maa-spectc1.png
   :align: center

   MAA ``spectC1`` for :math:`\omega=1`.





.. figure:: assets/dispersion-relation-gap/f-of-omega-0.1-and-k-densityplot-log-mzap-mzam-boxspectrum-spectwc3.png
   :align: center

   MZA ``spectWC3`` for :math:`\omega=0.1`.


.. figure:: assets/dispersion-relation-gap/f-of-omega-m0.1-and-k-densityplot-log-mzap-mzam-spectwc3.png
   :align: center

   MZA solution ``spectWC3`` for :math:`\omega=-0.1`.



.. figure:: assets/dispersion-relation-gap/f-of-omega-0.05-and-k-densityplot-log-mzap-mzam-spectwc3.png
   :align: center

   MZA solutions ``spectWC3`` for :math:`\omega=0.05`.




.. figure:: assets/dispersion-relation-gap/f-of-omega-0.05-and-k-densityplot-log-mzap-mzam-spectwc3-check-point.png
   :align: center

   MZA+ solution ``spectWC3`` for :math:`\omega=0.05` for a small range of :math:`k`. I chose only real :math:`k`.





.. figure:: assets/dispersion-relation-gap/f-of-omega-0.1-and-k-densityplot-log-mzap-mzam-spectwc4.png
   :align: center

   MZA solution ``spectWC4`` for :math:`\omega=0.1`.



.. figure:: assets/dispersion-relation-gap/f-of-omega-m0.1-and-k-densityplot-log-mzap-mzam-spectwc4.png
   :align: center

   MZA solution ``spectWC4`` for :math:`\omega=-0.1`.




.. figure:: assets/dispersion-relation-gap/f-of-omega-0.05-and-k-densityplot-log-mzap-mzam-spectwc4.png
   :align: center

   MZA solution ``spectWC4`` for :math:`\omega=0.05`.


.. admonition:: Questions about MZA Solutions
   :class: warning

   The results are weird. For ``spectWC3`` and ``spectWC4``, no real solutions are found in DR for :math:`\omega=0.05`. However, here we found one real solution for :math:`k`, which is not 0.


MZA solutions for spectra with crossing are shown below.

.. figure:: assets/dispersion-relation-gap/f-of-omega-0.1-and-k-densityplot-log-mzap-mzam-spectc1.png
   :align: center

   MZA solutions for ``spectC1`` with :math:`\omega=0.1`



.. figure:: assets/dispersion-relation-gap/f-of-omega-m0.1-and-k-densityplot-log-mzap-mzam-spectc1.png
   :align: center

   MZA solutions for ``spectC1`` with :math:`\omega=-0.1`




.. figure:: assets/dispersion-relation-gap/f-of-omega-1-and-k-densityplot-log-mzap-mzam-spectc1.png
   :align: center

   MZA solutions for ``spectC1`` with :math:`\omega=1`. We found one real solutioin for MZA- solution.



.. figure:: assets/dispersion-relation-gap/f-of-omega-m1-and-k-densityplot-log-mzap-mzam-spectc1.png
   :align: center

   MZA solutions for ``spectC1`` with :math:`\omega=-1`. We found one real solutioin for MZA+ solution.



References and Notes
-----------------------------
