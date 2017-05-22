Dispersion Relation and Gap
===============================


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
