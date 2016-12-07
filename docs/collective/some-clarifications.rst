Some Clarifications
======================


I need to understand several phenomena people mentioned.

1. Why crossing leads to instability?
2. What exactly is happening when we break the symmetries?


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



All Antineutrino Beams
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

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









One Antineutrino and One Neutrino Beams
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


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
