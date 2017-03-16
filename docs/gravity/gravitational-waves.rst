Gravitational Waves
==============================

.. admonition:: Conventions
   :class: warning

   1. We use signature :math:`+2` for the metric.

Basics
----------------------------


In general, we write down the components of metric for weak gravitational field as

.. math::
   g_{\alpha\beta} = \eta_{\alpha\beta} + h_{\alpha\beta},

where :math:`h_{\alpha\beta}` is the perturbation.

In general, a weak gravitational wave has two different modes, the :math:`h_+` mode [Schutz]_,

.. math::
   h_{\alpha\beta} \to \begin{pmatrix}
   0 & 0 & 0 & 0 \\
   0 & h_+ & h_\times & 0 \\
   0 & h_\times & -h_+ & 0 \\
   0 & 0 & 0 & 0
   \end{pmatrix},

where

.. math::
   h_+ &= A_{xx} \cos(\omega(t-z))\\
   h_\times &= A_{xy} \cos(\omega(t-z)).


.. admonition:: Binary Neutron Stary System
   :class: note

   In a binary neutron star system, which we detect at a distance :math:`r`, the gravitational waves carries the metric [Hendry2007]_

   .. math::
      h_{xx} &= -h_{yy} =h\cos(4\pi f t)\\
      h_{xy}&=h_{yx} = - h\sin (4\pi f t),

   where

   .. math::
      h = \frac{ 32\pi^2 G M R^2 f^2 }{c^4 r}.




For simplicity, we ignore the cross terms and consider only the diagonal elements in perturbation, aka :math:`h_+` polarization, the metric should be

.. math::
   g_{\alpha\beta}\to \begin{pmatrix}
   -1 & 0 & 0 & 0 \\
   0 & 1 + h_+ & 0 & 0 \\
   0 & 0 & 1-h_+ & 0 \\
   0 & 0 & 0 & 1
   \end{pmatrix}.

where

.. math::
   h_+ = A_{xx} \cos(\omega(t-z)).




Some Estimations
------------------------

As an estimation, the power of gravitation waves drop as :math:`1/r^2`. Thus the strain drops as :math:`1/r`.

For compact binary coalescence, the circular polarized wave at distance r is [Riles2013]_

.. math::
   h(t) =  \frac{1}{r} \left( \frac{5 G^5 M^5}{2 c^{11}} \right)^{1/4} \frac{1}{(t_{\mathrm{coal}} -t)^{1/4}},

which shows that the frequency diverges at :math:`t_{\mathrm{coal}}`.

In the astrophysicists' form, we have [Riles2013]_

.. math::
   h(\tau) = (1.7\times 10^{-23}) \left( \frac{15\mathrm{Mpc}}{r} \right) \left( \frac{1 \text{ day} }{\tau} \right)^{1/4} \left( \frac{M}{1.4M_{\odot}}\right)^{5/4}.


As an estimation, we can show that at :math:`r=1000 km` from the source,

.. math::
   h(\tau) \sim 10^{-6}\left( \frac{1 \text{ day} }{\tau} \right)^{1/4} \left( \frac{M}{1.4M_{\odot}}\right)^{5/4}.

As an example, we plot the evolution as a function of :math:`\tau` for 1.4 solar mass binaries.

.. figure:: assets/gravitational-waves/binary-mergers-h-tau.png
   :align: center

   Binary mergers. In the beginning, gravitational waves are very strong.

.. admonition:: Strong Field
   :class: warning

   However, the problem is, for stong waves, this estimation fails. I need to find a paper that numerically calculates the strain for strong fields.

   **And I haven't found the right paper.**



The size of the disk of neutron star mergers are of the order :math:`10 km` [Foucart2012]_.






Build a Model
------------------------------


I have no idea how can we build a practical model and numerically solve it up to nonlinear regime of neutrino oscillations.

However, with the help of dispersion relation, the linear regime can be analyzed.

I have to replace the Minkowski metric with the metric of gravitational waves. Without any calculation, I expect gravitational waves breaks the symmetrics, even the degeneracy of the MAA solution for axial symmetric system.


Gravitational Waves + Mode
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


.. admonition:: Assumptions
   :class: warning

   Assume the EoM derived by Raffelt is valid for weak gravitational field.

   In principle, if we do not consider other effects on Schrodinger equation but only the change in distances.


The polarization tensor

.. math::
   \Pi^\mu_\nu = g^\mu_\nu + \int \frac{d\Gamma}{4\pi} \frac{v^\mu v_\nu}{g_{\mu\nu}k^\mu v^\nu}.

Since we choose to calculate the dispersion relation in :math:`k_z` direction, :math:`g_{\mu\nu}k^\mu v^\nu=\omega - g_{33} k^z v^z`.

The first situation we demonstrate is for gravitational waves propagating in :math:`z` direction. At a certain time and z, we can write down the dispersion relation,

.. math::
   I + \begin{pmatrix}
   \frac{1}{2} I_0 & 0 & 0 & -\frac{1}{2}I_1\\
   0 & -\frac{1}{4}(1+h_+) (I_0-I_2) & 0  & 0 \\
   0 & 0 & -\frac{1}{4}(1+h_+) (I_0-I_2) & 0  \\
   \frac{1}{2}I_1 & 0 & 0 & -\frac{1}{2}I_2
   \end{pmatrix}.


:math:`h_+` is small, so we expect small effect from + mode. At least we do not expect something completely different.



Gravitational Waves x Mode
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The x mode will bring in cross terms. The polarization tensor becomes

.. math::
   I + \begin{pmatrix}
   \frac{1}{2} I_0 & 0 & 0 & -\frac{1}{2}I_1\\
   0 & -\frac{1}{4}(1+h_+) (I_0-I_2) & \frac{1}{4} h_\times (I_0-I_2)  & 0 \\
   0 & \frac{1}{4}h_\times (I_0 - I_2) & -\frac{1}{4}(1+h_+) (I_0-I_2) & 0  \\
   \frac{1}{2}I_1 & 0 & 0 & -\frac{1}{2}I_2
   \end{pmatrix}.

To look at the MAA solution, we need to write down the eigenvalues for the 2 by 2 matrix in the center. We fine the relation between :math:`\omega` and :math:`k` is

.. math::
   -4 &= -(1-h_+ - h_\times) (I_0-I_2)\\
   -4 &= -(1-h_+ + h_\times) (I_0-I_2).


For neutron star mergers, :math:`h_\times=-h_+`. The first solution is reduced to the flat space time solution.



.. admonition:: A Lot More to Think abut
   :class: warning

   How can I make sure I am can use this method?

   Even the previous calculations are valid, gravitational waves seems to break the symmetries in the emission surface. The question to ask is **the effect of breaking emission surface symmetry anyway**.


References and Notes
-----------------------


.. [Schutz] A First Course in General Relativity, Bernard Schutz.
.. [Hendry2007] `An Introduction to General Relativity, Gravitational Waves and Detection Principles <http://star-www.st-and.ac.uk/~hz4/gr/hendry_GRwaves.pdf>`_, Dr Martin Hendry. This discussion about the gravitational waves in a binary neutron star system is for slow motion approximation.
.. [Riles2013] K. Riles, `Gravitational waves: Sources, detectors and searches <http://dx.doi.org/10.1016/j.ppnp.2012.08.001>`_, Progress in Particle and Nuclear Physics, Volume 68, January 2013, Pages 1-54, ISSN 0146-6410.
.. [Foucart2012] Francois Foucart, `Black-hole–neutron-star mergers: Disk mass predictions <http://journals.aps.org/prd/abstract/10.1103/PhysRevD.86.124007>`_, Phys. Rev. D 86, December 2012.


Kip Thorne wrote a review paper about gravitational waves: `The Generation of Gravitational Waves: A Review of Computational Tecniques <https://www.its.caltech.edu/~kip/scripts/PubScans/II-68.pdf>`_.

A paper about modern techniques: `Extracting Physics from Gravitational Waves <http://www.nikhef.nl/pub/services/biblio/theses_pdf/thesis_T_G_F_Li.pdf>`_.
