Some Clarifications
======================


I need to understand several phenomena people mentioned.

1. Why crossing leads to instability?
2. What exactly is happening when we break the symmetries?

.. _two-beams-model:

Two Beams Model
------------------------

We use a simple two-beam line model.

.. figure:: assets/some-clarifications/two-beam-line-model.png
   :align: center

   Two-beam model. Using this model we can check the effect of different symmetries.

For convinience of notations, we define a number density distribution function

.. math::
   f(\hat\nu,\omega)= \frac{n(\hat \nu,\omega)}{n_t},

where :math:`n_t` is the total number density of all neutrino emitted, :math:`n(\hat\nu,\omega)` is the number density with momentum direction :math:`\hat \nu` and energy :math:`\omega`.

We also define

.. math::
   \mu = \sqrt{2}G_F n_t.

For two dimensional systems, we can calculate the neutrinos within an angle :math:`[\theta,\theta+d\theta]`

.. math::
   n_t f(\hat\nu,\omega) d\theta.


Similarly we can define the angular distribution for antineutrinos.


All Neutrino Beams
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

If all the beams are neutrinos, but with different energies for the left and right beams. The distribution function for beams is delta function. In fact, each beam is just half of the total neutrino number density :math:`n_t`.

The Hamiltonian is a sum of vacuum terms, matter terms, and self-interaction terms,

.. math::
   H= H_v + H_m + H_{\nu\nu},

where

.. math::
   H_v =& - \eta \frac{1}{2}\omega \sigma_3 \\
   H_m =& \frac{1}{2}\lambda \sigma_3\\
   H_{\nu\nu}^L =& \frac{1}{2}\mu \rho^R (1-\cos(\theta_1-\theta_2))\\
   H_{\nu\nu}^R =& \frac{1}{2}\mu \rho^L (1-\cos(\theta_1-\theta_2)).


To linearize the equation of motion, we define the perturbed density matrix as

.. math::
   \rho = \frac{1}{2}\begin{pmatrix}
   1 & \epsilon\\
   \epsilon^* & -1
   \end{pmatrix},

where we have removed the trace part because it is alway time independent.


The linearized equation of motion becomes

.. math::
   i \partial_z \begin{pmatrix}
   \epsilon_1 \\
   \epsilon_2
   \end{pmatrix} =&  - i \begin{pmatrix}\cot\theta_1\partial_x & 0 \\
   0 & \cot\theta_2 \partial_x
   \end{pmatrix} \begin{pmatrix}
   \epsilon_1 \\
   \epsilon_2
   \end{pmatrix} \\
   &+
   \frac{1}{2}\begin{pmatrix}
   (\lambda+ \mu_2 - \eta \omega_1 - \mu_2 \cos(\theta_1-\theta_2) )/\sin \theta_1 & -\mu_2 (1-\cos(\theta_1-\theta_2)) /\sin \theta_1\\
   -\mu_1 (1- \cos(\theta_1-\theta_2))/\sin\theta_2 & (\lambda + \mu_1 - \eta \omega_2 - \mu_1 \cos(\theta_1-\theta_2) )/\sin\theta_2
   \end{pmatrix}\begin{pmatrix}
   \epsilon_1 \\
   \epsilon_2
   \end{pmatrix},
   :label: eqn-line-model-two-beams-all-neutrino-linearized-eom


where

.. math::
   \mu_1 =& \sqrt{2}G_F n_{t,1}\\
   \mu_2 =& \sqrt{2}G_F n_{t,2}.


We know that real symmetric matrix has only real eigenvalues, from which we infer that :math:`\mu_1=\mu_2` and :math:`\theta_1=\theta_2` removes the instability.

For translational symmetric models, that is :math:`\partial_x\to 0`, we have the eigenvalues

.. math::
   \Omega = \frac{1}{4}(A\pm B),

where

.. math::
   A=& -\eta \omega_1/\sin\theta_1 - \mu_2 /\sin\theta_1 + \eta \omega_2 /\sin\theta_2 + \mu_1 \xi /\sin\theta_2 + \lambda(1/\sin\theta_1 + 1/\sin\theta_2)  \\
   B=& \sqrt{
      -4[(\lambda-\eta\omega_1)(\lambda +\eta\omega_2) + (\lambda (\mu_1-\mu_2) -\eta (\mu_1\omega_1 + \mu_2\omega_2) )\xi ] \sin\theta_1 \sin\theta_2 + [(\lambda + \eta\omega_2 + \mu_1\xi) \sin\theta_1 + (\lambda - \eta \omega_1 - \mu_2\xi) \sin\theta_2 ]^2
   }/(\sin\theta_1\sin\theta_2)\\
   \xi=&1-\cos(\theta_1-\theta_2).



.. admonition:: All Antineutrino Beams
   :class: note


   I only need to change :math:`\mu_i\to -\bar\mu_i` and :math:`\omega_i\to -\bar\omega_i`, where :math:`\bar\mu=\sqrt{2}G_F \bar n_t`.

   .. math::
      i \partial_z \begin{pmatrix}
      \epsilon_1 \\
      \epsilon_2
      \end{pmatrix} =&  - i \begin{pmatrix}\cot\theta_1\partial_x & 0 \\
      0 & \cot\theta_2 \partial_x
      \end{pmatrix} \begin{pmatrix}
      \epsilon_1 \\
      \epsilon_2
      \end{pmatrix} \\
      &+
      \frac{1}{2}\begin{pmatrix}
      (\lambda-\bar\mu_2 + \eta \bar\omega_1 + \bar\mu_2 \cos(\theta_1-\theta_2) )/\sin \theta_1 & \bar\mu_2 (1-\cos(\theta_1-\theta_2)) /\sin \theta_1 \\
      \bar\mu_1 (1- \cos(\theta_1-\theta_2))/\sin\theta_2 & (\lambda -\bar\mu_1 + \eta \bar\omega_2 +\bar\mu_1 \cos(\theta_1-\theta_2) )/\sin\theta_2
      \end{pmatrix}\begin{pmatrix}
      \epsilon_1 \\
      \epsilon_2
      \end{pmatrix}



.. admonition:: One Antineutrino and One Neutrino Beams
   :class: note

   Assume that the left beam is neutrino beam and the right beam is antineutrno beam. The linearized equation of motion becomes

   .. math::
      i\partial_z \begin{pmatrix}
      \epsilon_1 \\
      \epsilon_2
      \end{pmatrix} = & -i\begin{pmatrix}
      \cot\theta_1 \partial_x & 0 \\
      0 & \cot\theta_2 \partial_x
      \end{pmatrix}\begin{pmatrix}
      \epsilon_1 \\
      \epsilon_2
      \end{pmatrix} \\
      &+ \frac{1}{2}\begin{pmatrix}
      (\lambda - \bar\mu - 2\eta \omega_1 + \bar\mu \cos(\theta_1-\theta_2) )/\sin\theta_1 & \bar\mu (1-\cos(\theta_1-\theta_2))/\sin\theta_1 \\
      -\mu(1-\cos(\theta_1-\theta_2))/\sin\theta_2 & (\lambda + \mu + \eta \omega_2 - \mu \cos(\theta_1-\theta_2) )/\sin\theta_2
      \end{pmatrix}\begin{pmatrix}
      \epsilon_1 \\
      \epsilon_2
      \end{pmatrix}


Simple Cases
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

We first consider a simple case, where :math:`\theta_1=\theta_2\equiv \theta`, :math:`\lambda=0`, :math:`\eta=1`, and homogeneous in x direction. For simplicity we define

.. math::
   \mu =& \sqrt{2}G_F (n_1 + n_2)\\
   \mu_i =& \mu \frac{n_i}{n_1+n_2}\equiv \mu f_i \\
   \xi = & 1-\cos(\theta_1-\theta_2)\\
   \omega'_i = & \lambda - \eta\omega_i.


The equation for perturbations becomes

.. math::
   i\partial_z\begin{pmatrix}
   \epsilon_1 \\
   \epsilon_2
   \end{pmatrix} = \frac{1}{2\sin\theta} \begin{pmatrix}
   \omega'_i + \mu f_2\xi & -\mu f_2 \xi \\
   -\mu f_1 \xi & \omega'_2 + \mu f_1 \xi
   \end{pmatrix}\begin{pmatrix}
   \epsilon_1 \\
   \epsilon_2
   \end{pmatrix}.

Since :math:`\mu` is the most important energy scale in this problem, we scale all energies with it.

.. math::
   i\partial_{\hat z}\begin{pmatrix}
   \epsilon_1 \\
   \epsilon_2
   \end{pmatrix} = \frac{1}{2\sin\theta} \begin{pmatrix}
   \hat\omega'_1 +  f_2\xi & - f_2 \xi \\
   - f_1 \xi & \hat\omega'_2 +  f_1 \xi
   \end{pmatrix}\begin{pmatrix}
   \epsilon_1 \\
   \epsilon_2
   \end{pmatrix},

where

.. math::
   \partial_{\hat z} =& \frac{d}{\mu dz} \\
   \hat \omega'_i =& \frac{\omega'_i}{\mu}.



The characteristic equation for this equation is

.. math::
   \left( ( \Omega - \hat\omega'_1 - f_2\xi )(\Omega - \hat\omega'_2-f_1\xi) - f_1 f_2 \xi^2 \right) =0,
   :label: eqn-two-beam-line-characteristic-eqn-simple

which is simplified to

.. math::
   (\Omega-\Omega_1)(\Omega-\Omega_2) -f_1f_2\xi^2 = 0,

where

.. math::
   \Omega_1 = & \hat\omega'_1 + f_2 \xi\\
   \Omega_2 = & \hat\omega'_2 + f_1 \xi.


Complete the square

.. math::
   (\Omega - (\Omega_1 + \Omega_2)/2)^2 = \frac{1}{4}(\Omega_1-\Omega_2) + f_1f_2\xi^2.


The solution becomes

.. math::
   \Omega = \frac{1}{2}(\Omega_1+\Omega_2)\pm\sqrt{ (\Omega_1-\Omega_2)^2/4 + f_1f_2\xi^2 }.

The condition to have positive imaginary part is

.. math::
   (\Omega_1-\Omega_2)^2 + 4f_1f_2\xi^2 < 0,

or

.. math::
   -2\sqrt{-f_1f_2\xi^2}<\Omega_1-\Omega_2<2\sqrt{-f_1f_2\xi^2}.

Plug in the definitions of :math:`\Omega_i`,

.. math::
   -2\sqrt{-f_1f_2\xi^2}< \eta(- \omega_1 + \omega_2)/\mu + (f_2 - f_1)\xi < 2\sqrt{-f_1f_2\xi^2}.

From this we can infer

1. :math:`f_1f_2` has to be negative, which means we can NOT have instabilities with only neutrinos or antineutrinos with all the symmetries we assumed. This is :highlight-text:`crossing`.
2. :math:`-\omega_1+\omega_2=0` will remove the instability. So we have to have both neutrinos and antineutrinos.
3. :math:`f_2-f_1`, :math:`\eta(\omega_2-\omega_1)`, and :math:`\mu` set limit on each other.


.. admonition:: But why?
   :class: warning

   We have these conclusions. But why?

   What are the roles of

   1. :math:`f_i`,
   2. neutrino beam and antineutrino beam,
   3. hierarchy,
   4. neutrino number density variations.

.. admonition:: Real Symmetric and Skew Symmetric
	:class: toggle

	Another way of understanding this equation is to think of it as the growth of the length of the vector :math:`\vec v = (\epsilon_1,\epsilon_2)^T`. For an arbitrary matrix differential equation of the form

	.. math::
		\partial_z \mathbf v = \mathbf A \mathbf v,

	we can always decompose the matrix :math:`\mathbf A` into symmetric part and skew-symmetric part

	.. math::
		\mathbf A = \frac{1}{2}(\mathbf A + \mathbf A^T) + \frac{1}{2}(\mathbf A - \mathbf A^T) \equiv \mathbf A^+ + \mathbf A^-.

   We can indentify the effect of :math:`f_1-f_2` but this is not particularly useful since we can not say anything about the eigenvalues of matrix :math:`\mathbf A` from the eigenvalues of matrix :math:`\mathbf A^+` and :math:`\mathbf A^-`.



Breaking Symmetries
~~~~~~~~~~~~~~~~~~~~~~


For a line model, the symmetries we have are

1. Time translation symmetry;
2. Translational symmetry along the line;
3. Energy spectrum of the beams; **One of particular interest is to have different neutrino spheres for different energies which can be investigated using two beam model.**
4. Number density of left and right beams;
5. Angle of left and right beams;
6. With and without matter.


In this subsection we provide simple pictures of some the symmetries mentioned above.

Translational symmetry is explained by introducing Fourier transform in x direction. For each mode, a term that is proportional to Fourier mode index m. It only appears in diagonal elements, thus is effectively a shift of vacuum frequencies, thus energies of neutrinos.

Number density of each beam is described by the distribution :math:`f_i`'s effectively.

To see the importance of angles, we can redefine some quantities

.. math::
   \omega''_i=& \frac{\omega/_i}{\sin\theta_i}\\
   f''_1=&\frac{f_1}{\sin\theta_2} \\
   f''_2=&\frac{f_2}{\sin\theta_1}.

The we will reach the same characteristic equation as Eq. :eq:`eqn-two-beam-line-characteristic-eqn-simple`. So the angles serves as shift of energy gap and angular distribution.


Including matter will define vacuum frequencies, :math:`\omega'_i`, which is effectively just a shift of vacuum frequencies.



.. admonition:: Time Translational Symmetry
   :class: warning

   How about time translational symmetry? I need to write down the equation of motion that is related to time.

   Two limits are of particular interest.

   1. Adiabatic limit,
   2. Superfast time variants.



Numerical Calculations
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


We assume the two beams have different energy, as indicated by :math:`\omega_1` and :math:`\omega_2` in Eq. :eq:`eqn-line-model-two-beams-all-neutrino-linearized-eom`.


For numerical calcualtions, we scale quantities using :math:`\mu`.

With symmetric angles for the two beams, I didn't find instabilities. However, :math:`\theta_1\neq \theta_2` leads to instabilities in IH, which is consistant with our expections.



For NH:


.. image:: assets/some-clarifications/allneutrinos/line-two-beam-eta-1-lambda-0-mu-10-alpha-0.5-theta1-pi-div-3-theta2-pi-div-6.png
   :width: 31%
.. image:: assets/some-clarifications/allneutrinos/line-two-beam-eta-1-lambda-0-mu-10-alpha-1.-theta1-pi-div-3-theta2-pi-div-6.png
   :width: 31%
.. image:: assets/some-clarifications/allneutrinos/line-two-beam-eta-1-lambda-0-mu-10-alpha-1.5-theta1-pi-div-3-theta2-pi-div-6.png
   :width: 31%

.. image:: assets/some-clarifications/allneutrinos/line-two-beam-eta-1-lambda-0-mu-10-alpha-0.5-theta1-pi-div-6-theta2-pi-div-3.png
   :width: 31%
.. image:: assets/some-clarifications/allneutrinos/line-two-beam-eta-1-lambda-0-mu-10-alpha-1.-theta1-pi-div-6-theta2-pi-div-3.png
   :width: 31%
.. image:: assets/some-clarifications/allneutrinos/line-two-beam-eta-1-lambda-0-mu-10-alpha-1.5-theta1-pi-div-6-theta2-pi-div-3.png
   :width: 31%

.. image:: assets/some-clarifications/allneutrinos/line-two-beam-eta-1-lambda-0-mu-10-alpha-0.5-theta1-pi-div-3-theta2-pi-div-3.png
   :width: 31%
.. image:: assets/some-clarifications/allneutrinos/line-two-beam-eta-1-lambda-0-mu-10-alpha-1.-theta1-pi-div-3-theta2-pi-div-3.png
   :width: 31%
.. image:: assets/some-clarifications/allneutrinos/line-two-beam-eta-1-lambda-0-mu-10-alpha-1.5-theta1-pi-div-3-theta2-pi-div-3.png
   :width: 31%
