Parametric Resonance Revisted
============================================

For a matter profile

.. math::
   \lambda(x) = \lambda_0 + A\sin( k x),
   :label: parametric-resonance-matter-profile-single-frequency

the parametric resonance condition is [Krastev1989]_

.. math::
   \omega_m \sim n k,

where :math:`k=1,2,3,\cdots`.


.. admonition:: A Minimal Derivation of Parametric Resonance Condition
   :class: note

   This derivation is from [Krastev1989]_.

   On one matter profile wavelength, the accumulated phase of the system should be a multiple of :math:`2\pi`,

   .. math::
      \int_0^{2\pi/k} \omega_m = 2\pi n,

   where

   .. math::
      \omega_m = \omega_v \sqrt{ (\lambda(x)/\omega_v - \cos 2\theta_v)^2 + \sin^2 2\theta_v }.

   :math:`\omega_m` doesn't change a lot during one matter profile oscillation wavelength :math:`2\pi/k`, thus we perform the integration by treating the integrand as a constant, which returns

   .. math::
      \omega_m \frac{2\pi}{k} =2\pi n,

   which can be simplified

   .. math::
      \omega_m = n k.


For matter profile :eq:`parametric-resonance-matter-profile-single-frequency`, we already know that this is the condition of resonance from Rabi oscillation.







Refs & Notes
----------------

.. [Krastev1989] Krastev, P. I., & Smirnov, A. Y. (1989). Parametric effects in neutrino oscillations. Physics Letters B, 226(3-4), 341–346. doi:10.1016/0370-2693(89)91206-9
