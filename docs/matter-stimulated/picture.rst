Physics Picture
==================


Rabi oscillations
---------------------

Hamiltonian of Rabi oscillation is

.. math::
   H = -\frac{\omega_0}{2} \begin{pmatrix} 1 & 0 \\ 0 & -1 \end{pmatrix} - A \cos(\omega t)\begin{pmatrix} 0 & 1 \\ 1 & 0  \end{pmatrix} .





Test Example
--------------------------


First we choose a system that is on resonance

.. math::
   H_1 = -\frac{\omega_m}{2} \sigma_3 + \frac{\delta \lambda_1}{2} \cos 2\theta_m \sigma_3 - \frac{\delta \lambda_1}{2} \sin 2\theta_m \sigma_1,

where :math:`\delta\lambda_1 = A_1 \sin (k_1 x)`, where :math:`k_1 = \omega_m` and :math:`A_1 = 3.5\times 10^{-5}\omega_m`. This sets the system to resonance.

.. figure:: assets/picture/resonance-freq-example-1.png
   :align: center

   Resonance


.. admonition:: Does the Diagonal Term Matter?
   :class: note

   Removing the diagonal elements of the perturbation

   .. math::
      H_1' = -\frac{\omega_m}{2} \sigma_3  - \frac{\delta \lambda_1}{2} \sin 2\theta_m \sigma_1,

   will result in :numref:`resonance-freq-example-1-compare-with-diagonal-elements-of-perturbation-removed`.

   .. _resonance-freq-example-1-compare-with-diagonal-elements-of-perturbation-removed:

   .. figure:: assets/picture/resonance-freq-example-1-compare-with-diagonal-elements-of-perturbation-removed.png
      :align: center

      Remove the diagonal elements of the preturbation



.. admonition:: Adding in Slow Rotating Field
   :class: note

   Add a new slow perturbation

   .. math::
      \delta \lambda_2 = A_2 \sin (k_2 x),

   with

   .. math::
      A_2 &= 10^{-2},\\
      k_2 &= 0.1.


   .. figure:: assets/picture/resonance-freq-example-1-added-new-slow-perturbation.png
      :align: center

      Added new slow perturbation



.. admonition:: Removing Diagonal Elements of Slow Perturbation
   :class: note

   Removing the diagonal elements of slow perturbation

   .. math::
      H_2' = -\frac{\omega_m}{2} \sigma_3 + \frac{\delta \lambda_1 }{2} \cos 2\theta_m \sigma_3 - \frac{\delta \lambda_1 + \delta \lambda_2}{2} \sin 2\theta_m \sigma_1,


   gives us the result :numref:`resonance-freq-example-1-added-new-slow-perturbation-compare-with-removing-diagonal-elements`.

   .. _resonance-freq-example-1-added-new-slow-perturbation-compare-with-removing-diagonal-elements:

   .. figure:: assets/picture/resonance-freq-example-1-added-new-slow-perturbation-compare-with-removing-diagonal-elements.png
      :align: center

      Remove diagonal elements of slow perturbation.



Explaination
~~~~~~~~~~~~~~~~~~~~~~


Slow perturbation is slow and changes the energy gap of the system. Since the energy gap :math:`\omega_m` determines the resonance point, which is

.. math::
   k_1 = \omega_m,

adding the slow perturbation could increase :math:`\omega_m`,

.. math::
   \omega_m' &= \sqrt{A_{2,\bot} ^2 + \omega_m^2} \\
   & = \omega_m \sqrt{ \left(\frac{A_{2,\bot}}{\omega_m} \right)^2 + 1 } \\
   & \approx  \omega_m + \frac{A_{2,\bot}^2}{2\omega_m},
   :label: quadratic-approximation-energy-gap-shift


where :math:`A_{2,\bot}` is component perpendicular to z axis.



.. admonition:: Only Perpendicular Component
   :class: warning

   In the calculation of the modified energy gap, we used only the perpendicular component of the new slow perturbation. This only holds for :math:`A_{2,\bot}  \ll \omega_m`.

   **PROOF**


.. admonition:: Shift The System Out of Resonance
   :class: note

   Shift the system out of resonance, it is required that

   .. math::
      \lvert \omega_m' - \omega_m \rvert \gtrsim \text{width of resonance}.

   Width of resonance is basically determined by :math:`A_{1,\bot}`. Apply equation :eq:`quadratic-approximation-energy-gap-shift`, we can solve the condition to break the resonance,

   .. math::
      A_{2,\bot} \gtrsim \sqrt{2\omega_m A_{1,\bot}}.

   In our example, the condition becomes

   .. math::
      &A_2 \sin 2\theta_m \gtrsim \sqrt{2\omega_m A_1 \sin 2\theta_m} \\
      \Rightarrow & A_2  \gtrsim \sqrt{2\omega_m A_1 \tan 2\theta_m/\cos 2\theta_m}.


   .. figure:: assets/picture/resonance-freq-example-1-added-new-slow-perturbation-destruction.png
      :align: center

      With :math:`A_2=\sqrt{2 A_1 \sin (2 \theta_m)}/ \cos ^2(2 \theta_m) =0.0190304\omega_m`



   .. figure:: assets/picture/resonance-freq-example-1-added-new-slow-perturbation-destruction-compare.png
      :align: center

      Compare to show destruction


   Using Rabi formula the amplitudes are not matching the numerical calculations, :numref:``.

   .. figure:: assets/picture/resonance-freq-example-1-added-new-slow-perturbation-destruction-compare-gridlines.png
      :align: center

      Grid lines are the amplitudes predicted by Rabi formula.

   As a reference, the Q values for each line are

   .. math::
      Q_1 & =  \frac{\lvert k_1 - \sqrt{A_2 \sin^2(2\theta_m)  + 1 }  }{A_1\sin (2\theta_m)} = 1.11689, \\
      Q_2 & = \frac{\lvert k_1 - \sqrt{A_2' \sin^2(2\theta_m)  + 1 }  }{A_1\sin (2\theta_m)} = 4.04469, \\
      Q_3 & = \frac{\lvert k_1 - \sqrt{A_2'' \sin^2(2\theta_m)  + 1 }  }{A_1\sin (2\theta_m)} = 402.277.





However, the important question is whether the modified oscillation really Rabi oscillation. The answer is NO.

.. figure:: assets/picture/really-rabi-question-mark.png
   :align: center

   Is the oscillation with slow perturbation really Rabi oscillation? Upper panel: Theoretical and numerical calculation of original system;
   Lower panel: Theoretical and numerical calculation with slow perturbation added.


We can not predict the oscillation when we add in the new perturbation using the Rabi oscillation formula.





Refs & Notes
-----------------

.. 1. Note to self: My advisor proposed and did the first calculations.
