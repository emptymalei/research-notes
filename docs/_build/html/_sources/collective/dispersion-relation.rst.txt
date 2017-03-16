Dispersion Relation
================================

Reference to notes:

Izaguirre, I., Raffelt, G., & Tamborra, I. (2016). Fast Pairwise Conversion of Supernova Neutrinos: Dispersion-Relation Approach, 21101(January), 1–6. https://doi.org/10.1103/PhysRevLett.118.021101



Polarization Tensor
--------------------------

In Raffelt's paper, they defined the polarization tensor as

.. math::
   \Pi^{\mu\nu} = \eta^{\mu\nu} + \int \frac{d\Omega}{4\pi} G(\theta,\phi) \frac{v^\mu v^\nu}{k^\mu v_\mu}.

For numerical calculations, we lower the second index and multiply on both side :math:`\omega`,

.. math::
   \omega\Pi^\mu_\nu = \omega\delta^\mu_\nu + \int \frac{d\Omega}{4\pi} G(\theta,\phi) \frac{v^\mu v_\nu}{ 1- \frac{k}{\omega} \hat k\cdot \mathbf v },

where

.. math::
   v^\mu &= \begin{pmatrix} 1 & \sin\theta \cos\phi & \sin\theta \sin\phi & \cos\theta \end{pmatrix}\\
   k^\mu &= \begin{pmatrix} \omega & k \sin\theta_k \cos\phi_k & k\sin\theta_k \sin\phi_k & k\cos\theta_k \end{pmatrix}.




Parametrization of Polarization Tensor
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Raffelt et al parametrize :math:`k^\mu(n)` where :math:`n=k/\omega`. Then the polarization tensor is decomposed into two parts,

.. math::
   \eta^{\mu\nu}

and

.. math::
   \frac{1}{\omega}N^{\mu\nu},

where

.. math::
   N^{\mu\nu} = \int d\Gamma G_{\mathbf v} \frac{v^\mu v^\nu}{ 1-n \hat{\mathbf k} \cdot \mathbf v },

with :math:`k^\mu=(\omega,\mathbf k)`.

.. admonition:: Note to self
   :class: warning

   The actual wave vector that determines the instability is :math:`K^\mu` which is related to :math:`k^\mu`,

   .. math::
      k^\mu= K^\mu - (\Lambda^\mu + \Phi^\mu).

   Since :math:`\Lambda^\mu` and :math:`\Phi^\mu` are real, imaginary part of :math:`\omega` (:math:`\mathbf k`) equal imaginary part of :math:`\Omega` (:math:`\mathbf K`). Thus we only discuss the dispersion relation of :math:`k^\mu`.

   Density matrix is written as

   .. math::
      \rho = \begin{pmatrix}
      1 & \epsilon \\
      \epsilon^* & -1
      \end{pmatrix}.

   The perturbation :math:`\epsilon` is assumed to have the form

   .. math::
      \epsilon = Q(\Omega, \mathbf K) e^{ -i( \Omega t - \mathbf K \cdot \mathbf x ) }.

   This assumption indicates that even though we find instabilities, a proper initial condition/boundary condition is required to stimulate this instability.


The polarization tensor is in fact

.. math::
   \Pi^{\mu\nu} = \eta + \frac{1}{\omega}N^{\mu\nu}.

The equation of motion becomes

.. math::
   v_\mu \Pi^{\mu\nu} a_\nu =0 ,

where

.. math::
   a_\nu = - \int d\Gamma v_\nu G_{\mathbf v} Q_{\mathbf v}.

Since :math:`v_\mu` is (component) of a null dual vector, we require :math:`\Pi^{\mu\nu} a_\nu` to be (component) proportional to :math:`v^\mu`. Since we have a lot of directions, different :math:`v^\mu` are independent of each other. So we require :math:`\Pi^{\mu\nu} a_\nu=0`.

Then we need to find the solution to

.. math::
   \mathrm{Det}(\Pi^{\mu\nu})=0,

which is simplified to

.. math::
   \mathrm{Det}(\omega \eta^{\mu\nu} + N^{\mu\nu}) = 0.

We can also use the polarization tensor :math:`\Pi^\mu_\nu`

.. math::
   \mathrm{Det}(\omega \delta^\mu_\nu + N^{\mu}_\nu) =0

is the determinant of a matrix

.. math::
   \omega I + \mathbf N^\mu_\nu.


Equivalently, we only need to find the eigenvalues of :math:`\mathbf N^\mu_\nu` then multiply on each of them by negative sign.



Examples of Parametrization
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Raffelt et al proposed that can now solve the dispersion relation by finding the value of :math:`k^\mu(n)` for each n. We make the plot :math:`\omega` vs :math:`\mathbf k`.

Here is an example that I calculated.

The axial symmetric system can be calculated easily using this method. The paper gave an example of two polar angle beams with axial symmetry.

.. figure:: assets/dispersion-relation/listpltOmegan1.png
   :align: center

   :math:`\omega(n)` for :math:`G=0.5 \delta(\cos\theta- 0.8) + 0.5 \delta(\cos\theta+0.2)`.


.. figure:: assets/dispersion-relation/listpltDispersionRelationDecompose1.png
   :align: center

   Dispersion relation.


We can check what happens for multibeams. I can plot the dispersion relation for similar configuration but with different number of beams.


.. figure:: assets/dispersion-relation/listanimi1.png
   :align: center

   Animition of dispersion relation.

   .. code:: text

      dataPltNBeamsPlt[Join[Table[1/beams, {n, 1, beams/2}],
      Table[-1/beams, {n, 1, beams/2}]],
      Table[Pi/3 + n Pi/2/(beams - 1), {n, 0, beams - 1}], {-10, 10}, 0.049, {{-10, 10}, {-10, 10}}]



I plot the :math:`\omega(n)` relation for different number of beams

.. image:: assets/dispersion-relation/listpltOmegan12List-2.png
   :width: 49%

.. image:: assets/dispersion-relation/listpltOmegan12List-4.png
   :width: 49%

.. image:: assets/dispersion-relation/listpltOmegan12List-8.png
   :width: 49%

.. image:: assets/dispersion-relation/listpltOmegan12List-10.png
   :width: 49%

Similar to the previous example, confining the range of :math:`n` leads to only a partial patch of the dispersion relation.

.. figure:: assets/dispersion-relation/pltDiffBeamsConfined-n-in--1-to-1-beams-10.png
   :align: center

   The code for it

   .. code:: text

      pltDiffBeamsConfined[beams_] := dataPltNBeamsPlt[
      Join[Table[1/beams, {n, 1, beams/2}],
      Table[-1/beams, {n, 1, beams/2}]],
      Table[Pi/3 + n Pi/2/(beams - 1), {n, 0, beams - 1}], {-1, 1},
      0.049, {{-10, 10}, {-10, 10}}]



.. admonition:: This should be the continuous limit?
   :class: warning

   As a comparison, we can plot the dispersion relation in a larger range of n for 10 beams.


   .. figure:: assets/dispersion-relation/listpltOmegan12List-10.png
      :align: center

      10 beams.


   On the other hand, we can calculate the continuous limit for the same angle range.

   .. figure:: assets/dispersion-relation/compare-continuous-and-10-beams-within-n-range--1-to-1.png
      :align: center

      Dispersion relation for 10 beams (:math:`n\in [-1,1]`), and continuous limit.

   MEH










Analyze the Symmetries in Polarization Tensor
------------------------------------------------------------------


.. admonition:: Vectors Using Spherical Harmonics
   :class: toggle

   Four velocity can be expressed in terms of spherical harmonics.

   .. math::
      v^\mu = \sqrt{\pi}\begin{pmatrix} 2 & \sqrt{2/3} (Y_1^{-1} - Y_1^1) & i \sqrt{2/3} (Y_1^{-1} + Y_1^1) & 2\sqrt{1/3} Y_1^0 \end{pmatrix}.


In principle, solving the dispersion relation is not easy. Neverthless, symmetries would significantly simplify the problem.

Axial symmetry indicates that the integrals of first orders of :math:`\sin\phi\cos\phi`, :math:`\sin\phi`, and :math:`\cos\phi` are 0 on the range :math:`\phi\in [0,2\Pi]`.

We denote the integral

.. math::
   \int \frac{d\Omega}{4\pi} G(\theta,\phi) \frac{v^\mu v_\nu}{\omega- k \hat{\mathbf k}\cdot \mathbf v}

as :math:`P^\mu_\nu`. The polarization tensor becomes

.. math::
   \Pi^\mu_{\phantom{\mu}\nu} = I + P^\mu_{\phantom{\mu}\nu}.

For axial symmetric emission, only terms :math:`P^0_{\phantom{0}0}, P^0_{\phantom{0}3}, P^3_{\phantom{3}0}, P^3_{\phantom{3}3}, P^1_{\phantom{1}1}, P^2_{\phantom{2}2}` are nonzero, given :math:`\mathbf k` in z direction, i.e., :math:`\phi_k=\theta_k=0`.

To simplify the calcualtion, we denote :math:`n=\frac{\lvert \mathbf k\rvert}{\omega}`. We will NOT solve :math:`\omega(n)`. Instead we write down the form of the eigenvalues of

.. math::
   N^\mu_{\phantom{\mu}\nu} = \omega P^\mu_{\phantom{\mu}\nu},

which shows is an analytical expression of :math:`\omega`. We do not solve this relation. Instead, we plugin the definition :math:`n=\frac{\lvert \mathbf  k\rvert}{\omega}` and find out the relation between :math:`\omega` and :math:`k=\lvert \mathbf k \rvert`

We define

.. math::
   I_n(\theta)=\int_{\cos\theta_2}^{\cos\theta_1} d\cos\theta G(\theta) \frac{\cos^n\theta}{1 - n \cos\theta },

where :math:`\theta_1` and :math:`\theta_2` are

Since

.. math::
   \int_0^{2\pi} d\phi&=2\pi \\
   \int_0^{2\pi} d\phi \cos^2\phi &=\int_0^{2\phi} d\phi \sin^2\phi = \pi,

the matrix :math:`N^\mu_{\phantom{\mu}\nu}` is simplified,

.. math::
   N^\mu_{\phantom{\mu}\nu} = \omega P^\mu_{\phantom{\mu}\nu}\to  \begin{pmatrix}
   \frac{1}{2}  I_0 & 0 & 0 & -\frac{1}{2}I_1\\
   0 & -\frac{1}{4}(I_0-I_2) & 0 & 0\\
   0 & 0 & -\frac{1}{4}(I_0-I_2) & 0 \\
   \frac{1}{2}I_1 & 0 & 0 & -\frac{1}{2}I_2
   \end{pmatrix}.

We express the eigen values of matrix :math:`N^\mu_{\phantom{\mu}\nu}`, which we denote as :math:`\lambda_N`,

.. math::
   \omega = -\lambda_N = \frac{1}{4}(I_0-I_2), \quad -\frac{1}{4}\left(I_0-I_2\pm \sqrt{ (I_0-2I_1+I_2)(I_0+2I_1+I_2) }\right).
   :label: eqn-omega-n-relation-axial-sym-general


We plug in the definition :math:`n=k/\omega` then solve dispersion relation from each of the solutions in Eq. :eq:`eqn-omega-n-relation-axial-sym-general`.

The questions are

1. What does each of the solutions mean?


Eigenvalues and Axial Symmetry
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


By definition, the meaning of polarization tensor, :math:`\Pi^\mu_\nu a^\nu=0` implies that :math:`a^1` and :math:`a^2` are the :math:`\phi` angle dependent components. To prove this, we rewrite :math:`Q`,

.. math::
   Q = \frac{a^\mu v_\mu}{k^\nu v_\nu},

which clearly shows that the 1, and 2 component of :math:`a^\mu` is related to the phi dependence of :math:`Q`. :math:`a^1=a^2=0` indicates that :math:`Q` has no :math:`\phi` dependence.

.. admonition:: Is this related to eigenvectors?
   :class: warning


   The eigenvalue :math:`\frac{1}{4}(I_0-I_2)` of matrix :math:`N^\mu_{\phantom{\mu}\nu}` corresponds to eigenvectors :math:`(0,0,1,0)` and :math:`(0,1,0,0)`.

   I don't think it is related to eigenvalues. However, eigenvalues set limit on the actual solution. When we write down the solution to :math:`a^\mu`, the coefficients are related to each other because we have determinant of coefficient matrix being 0. There are degeneracies.


That is to say, the part

.. math::
   \begin{pmatrix}
   -\frac{1}{4}(I_0-I_2) & 0 \\
   0 & -\frac{1}{4}(I_0-I_2)
   \end{pmatrix}

are the only elements that determines the whether we have a :math:`\phi` dependence in :math:`Q`, since this is the only part that needs to be acted on in Gaussian elimination method. It is obvious that we have

.. math::
   a^1=a^2=0.

In turn, it determines the angle dependence of :math:`Q`,

.. math::
   Q =  \frac{a^0 - a^1\sin\theta\cos\phi - a^2\sin\theta\sin\phi - a^3 \cos\theta}{k^\mu v_\mu} = Q_0 + Q_3(\theta).

We have no :math:`\phi` dependence in :math:`Q` if we foce the emission to be axially symmetric.



Continuous Emission within Angle Range
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

In this case we have to calculate :math:`I_n` specifically for the angle range, then plug in the expression :math:`n=k/\omega` to find the dispersion relation.


Discrete Emission Beams
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

For discrete emission :math:`G(\theta)=\sum_i G_i \delta(\cos\theta-\cos\theta_i)`, we can define new quantities

.. math::
   \tilde I_n(\theta)= \sum_i G_i \frac{\cos^n\theta_i}{1 - n \cos\theta_i }.


Thus

.. math::
   &\omega = \frac{1}{4}(I_0-I_2) \\
   \Rightarrow &\omega = \frac{1}{4} \sum_i G_i \frac{1-\cos^2\theta_i}{1 - n \cos\theta_i }.


For two sets of beams, we have

.. math::
   4 =  G_1 \frac{1-\cos^2\theta_1}{\omega - k\cos\theta_1 } + G_2 \frac{1-\cos^2\theta_2}{\omega - k \cos\theta_2 },

which is a conic section. We have already used :math:`n=k/\omega`.

.. admonition:: Hyperbola
   :class: note

   For an quadratic equation [HyperbolaWikipedia]_

   .. math::
      A_{xx} x^2 + 2 A_{xy} xy + A_{yy} y^2 + 2 B_x x + 2 B_y y + C = 0,

   it is hyperbola if

   .. math::
      D := \begin{vmatrix} A_{xx} & A_{xy}\\A_{xy} & A_{yy} \end{vmatrix} < 0.

   Center of the hyperbola :math:`(x_c,y_c)` is

   .. math::
      x_c &= -\frac{1}{D} \begin{vmatrix} B_x & A_{xy} \\ B_y & A_{yy} \end{vmatrix}\\
      y_c &= -\frac 1 D \begin{vmatrix} A_{xx} & B_x \\A_{xy} & B_y \end{vmatrix}.

   Principal axis is tilted away from x axis by angle :math:`\beta`

   .. math::
      \tan 2\beta = \frac{2A_{xy}}{A_{xx}-A_{yy}}.

   .. [HyperbolaWikipedia] `Hyperbola @ Wikipedia <https://en.wikipedia.org/wiki/Hyperbola#Quadratic_equation>`_


We can prove that this is a hyperbola. Simplify the equation to standard form of conic sections

.. math::
   4\cos\theta_1\cos\theta_2 k^2 - 2 \times 2(\cos \theta_1+\cos\theta_2) \omega k +4\omega^2  + 2 \times \frac{ G_1(1-\cos^2\theta_1)\cos\theta_2 + G_2(1-\cos^2\theta_2)\cos\theta_1 }{2} k - 2 \times\frac{ G_1(1-\cos^2\theta_1) + G_2(1-\cos^2\theta_2) }{2}  \omega = 0.


.. admonition:: The :math:`\omega~k` plane
   :class: toggle

   We use :math:`\omega~k` plane, so that we map :math:`k` to :math:`x` and :math:`\omega` to :math:`y`.

   So the coefficients are defined as

   .. math::
      A_{kk} &= 4\cos\theta_1\cos\theta_2\\
      A_{k\omega} &= -2(\cos\theta_1+\cos\theta_2)\\
      A_{\omega\omega} & = 4 \\
      B_k & =  \frac{ G_1(1-\cos^2\theta_1)\cos\theta_2 + G_2(1-\cos^2\theta_2)\cos\theta_1 }{2} = \frac{\tilde G_1 \cos\theta_2 + \tilde G_2 \cos\theta_1}{2}\\
      B_\omega & =  - \frac{ G_1(1-\cos^2\theta_1) + G_2(1-\cos^2\theta_2) }{2} = -\frac{\tilde G_1 + \tilde G_2}{2}.



The condition for it to be hyperbola is :math:`D<0`, where

.. math::
   D = \begin{vmatrix}
   4\cos\theta_1\cos\theta_2 & -2(\cos\theta_1+\cos\theta_2) \\
   -2(\cos\theta_1+\cos\theta_2)  & 4
   \end{vmatrix} = - 4 (\cos\theta_1-\cos\theta_2)^2.

As long as we have different angles, :math:`D` is always less than 0. We always have a hyperbola. The center of the hyperbola is

.. math::
   k_c &= -\frac{1}{D} \begin{vmatrix}
   B_k & A_{k\omega} \\
   B_\omega & A_{\omega\omega}
   \end{vmatrix} = \frac{1}{4 (\cos\theta_1-\cos\theta_2)^2} \begin{vmatrix}
   \frac{ \tilde G_1\cos\theta_2 + \tilde G_2\cos\theta_1 }{2} & -2(\cos\theta_1+\cos\theta_2)\\
   - \frac{ \tilde G_1 + \tilde G_2 }{2} & 4
   \end{vmatrix}   \\
   \omega_c &= -\frac{1}{D} \begin{vmatrix}
   A_{kk} & B_k \\
   A_{k\omega} & B_\omega
   \end{vmatrix} = \frac{1}{4 (\cos\theta_1-\cos\theta_2)^2} \begin{vmatrix}
   4\cos\theta_1\cos\theta_2 & \frac{ \tilde G_1\cos\theta_2 + \tilde G_2\cos\theta_1 }{2}\\
   -2(\cos\theta_1+\cos\theta_2) & - \frac{ \tilde G_1 + \tilde G_2 }{2}
   \end{vmatrix}  .


A special case for it is :math:`G_1=\pm G_2`, however, the expression for the center doesn't really simplify that much.


We are interested in gaps, so the asymptotic lines are the lines that we are interested in.

First of all, we need to find out the principal axis. The angle between the principal axis and x axis is defined to be :math:`\beta`,

.. math::
   \tan2 \beta = \frac{2A_{k\omega}}{A_{kk}-A_{\omega\omega}} = \frac{\cos\theta_1+\cos\theta_2}{1-\cos\theta_1\cos\theta_2}.

Suppose we have angles :math:`\theta'_i=\arctan ( \cos\theta_i )`,

.. math::
   \beta = \frac{\theta'_1+\theta'_2}{2}.

This indicates that the angle :math:`\beta` is always within range :math:`\beta \in [\pi/4,\pi/4]`.



.. admonition:: The other solutions
   :class: note

   For the solutions

   .. math::
      \omega = -\frac{1}{4}\left(I_0-I_2\pm \sqrt{ (I_0-2I_1+I_2)(I_0+2I_1+I_2) }\right),

   it becomes much more complicated.




Why is it called Polarization Tensor
-------------------------------------------


Why is :math:`a^\mu` called polarization vector?

We kind of see why :math:`a^\mu` is some kind of polarization given the definition

.. math::
   a^\mu = -\int d\Gamma v^\mu G(\theta,\phi) Q(\theta,\phi).

In some sense it is a weighted average of :math:`Q`. And :math:`S = Q e^{-i k^\mu x_\mu}` is the "field" we are insterested in.

Comparing to electrodynamics, where we have the field :math:`A^\mu` which tells us about the polarization,


.. admonition:: Polarization in Electrodynamics
   :class: toggle

   We can assume that the four vector field is

   .. math::
      A^\mu = \epsilon^\mu a e^{-ikx} + {\epsilon^\mu}^*  a^* e^{ikx} \qquad \text{with}\quad k_\mu k^\mu =0.

   We make sense of it by interpretating :math:`\epsilon^\mu` as the polarization vector and :math:`a` as the amplitude of the field strength. This solution is only for one particular case. We use it as an example because it is simple.

   To calculate the electric field, :math:`E^i` where :math:`i=1,2,3`, we apply the definition of it

   .. math::
      E^i = - F^{0i}.

   By working it out, we find :math:`\epsilon^i`, which is the spatial part of :math:`\epsilon^\mu`, indeed plays a role in the direction of field.



Solving Continuous Emission
-----------------------------------------

Suppose neutrinos are emitted within a angle range :math:`[\theta_1,\theta_2]`. Using Mathematica, we find the three important integrals

.. math::
   I_0 &= \int_{c_2 }^{c_1 } d x \frac{1}{1-k\cos\theta/\omega} \\
      &= \frac{\omega}{k} \ln \left( \frac{\omega-c_2 k}{\omega-c_1 k} \right) \\
   I_1 &= \int_{c_2 }^{c_1 } d x \frac{x}{1-k\cos\theta/\omega} \\
   & =  \frac{\omega}{\omega} \left( c_2 -c_1  +  \frac{ \omega }{k} \ln \left( \frac{\omega-c_2 k}{\omega-c_1 k} \right) \right) \\
   I_2 &= \int_{c_2 }^{c_1 } d x \frac{x^2}{1-k\cos\theta/\omega} \\
   &= \frac{\omega}{k} \left(  (c_2 -c_1 )\left(\frac{\omega}{k} + c_1 +c_2  \right) + \left(\frac{\omega}{k}\right)^2 \ln \left( \frac{\omega-c_2 k}{\omega-c_1 k} \right) \right).


where :math:`c_1=\cos\theta_1` and :math:`c_2=\cos\theta_2`.


Homogeneous Emission
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Assuming :math:`G=1`, the MAA solution is

.. math::
   -4 = I_0 - I_2,

which becomes

.. math::
   \ln \left( \frac{1-c_2 n }{1-c_1 n} \right) = \frac{ -4 n^3 + (c_2-c_1)(1+(c_1+c_2)n/2 ) }{ n^2-1 }.
   :label: eqn-dr-continuous-angle-range

.. figure:: assets/dispersion-relation/DR-omega-k-direct-continuous-two-graphic-solution.png
   :align: center

   LHS and RHS of Eq. :eq:`eqn-dr-continuous-angle-range`. The :math:`n` values where the LHS = RHS are :math:`n\sim -1, -0.35, 0.9, 1`. The value -0.35 can be found usng FindRoot, but all other values are approximated guesses.


.. admonition:: -0.35?
   :class: warning

   I was wondering whether this -0.35 is of any importance. So I ploted the line :math:`\pm 0.35 k` on top of the :math:`\omega\sim k` plot. Didn't find any match to the discrete solutions.

   .. figure:: assets/dispersion-relation/DR-omega-k-direct-4-beams.png
      :align: center

      4 Beams



Emission with Crossing
~~~~~~~~~~~~~~~~~~~~~~~~

I have to break each of the integral into two parts. I calculate :math:`I_0-I_2` for the first region then add to it the second region. Within a region :math:`[\theta_1,\theta_2]` and :math:`G=g`,

.. math::
   RHS(c_1,c_2)=I_0-I_2 = g \left[ \left( \frac{1}{n} - \frac{1}{n^3} \right)\ln\left( \frac{1-n c_2}{1-n c_1} \right) - \frac{c_2-c_1}{n} \left( \frac{c_1+c_2}{2} + \frac{1}{n} \right) \right].


The dispersion relation is given by

.. math::
   -4 = RHS(c_1,c_0) + RHS(c_0,c_2).

I can plot the RHS.

.. figure:: assets/dispersion-relation/DR-omega-k-direct-continuous-two-regions.png
   :align: center

   Function value for :math:`RHS(c_1,c_0) + RHS(c_0,c_2)`. The vertical grid lines are :math:`n=1/c_1, 1/c_2`.

The reason we have no real values between :math:`1/0.9` and :math:`1/0.3` is because the argument of the ln function is negative within this regime.

.. figure:: assets/dispersion-relation/DR-omega-k-direct-continuous-two-regions-arg-ln.png
   :align: center

   The argument of the ln function for RHS.


Discrete Case and Continuous Case
--------------------------------------


Will we have a continuous case if the number of beams is infinite.

For discrete case

.. math::
   I_0 - I_2 = \sum_{i=1}^N G_i \frac{ 1-\cos^2\theta_i }{\omega - k \cos \theta_i} = \sum_i G_i \frac{1-u_i^2}{\omega-k u_i}.
   :label: eqn-discrete-beams-i0-i2

The continuous case is

.. math::
   I_0 - I_2 = \int d\cos\theta  G(\cos\theta) \frac{1 - \cos^2\theta}{\omega- k \cos\theta} = \int du G(u) \frac{1-u^2}{\omega-k u} .
   :label: eqn-conti-beams-i0-i2


We notice that Eq. :eq:`eqn-discrete-beams-i0-i2` and Eq. :eq:`eqn-conti-beams-i0-i2` are the same when number of beams becomes large.

:math:`G_i` is in fact :math:`G_i = g_i \Delta u_i`, where :math:`\Delta u_i` is the range of :math:`\cos \theta_i` around :math:`\theta_i`.
