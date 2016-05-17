Interference
============================================


In the calculation of multi-frequency matter background,

.. math::
   \delta\lambda_N = \sum_{a=1}^N A_a \sin(k_a x + \phi_a),

we derived the equation of motion

.. math::
   i \partial_x \Psi = H \Psi,

where

.. math::
   \Psi = \begin{pmatrix}
   \psi_{b1} \\
   \psi_{b2}
   \end{pmatrix},

is the wave function in the T basis (new basis unitary transform from background matter basis using T matrix) and

.. math::
   H = \begin{pmatrix}
   0 & h_N \\
   h_N^* & 0
   \end{pmatrix},

where

.. math::
   h_N = -\frac{1}{2}\sum_{n_1=-\infty}^\infty \cdots \sum_{n_N=-\infty}^\infty B_N\Phi_N e^{i(\sum_a^{N} n_a k_a - \omega_m)x},

and

.. math::
   B_N &= (-i)^{\sum_a n_a} \left( \sum_a n_a k_a \right) \left( \prod_a J_{n_a}\left( \frac{A_a}{k_a}\cos 2\theta_m \right) \right),\\
   \Phi_N &= e^{i\left( \sum_a n_a \phi_a \right)}.


So we could identify the important combinations of n's :math:`\{n_1, \cdots, n_N \}` so that we can approximate the actual result.

The important question is combining multiple lists of n's is not intuitively easy to understand. Here we consider the effect of adding new list of n's to the system.

For simplicity a simplified system will be used,

.. math::
   i\partial_x  \begin{pmatrix}
   \psi_{b1} \\
   \psi_{b2}
   \end{pmatrix} = \begin{pmatrix}
   0 & A_1 e^{ i \phi_1 x } +A_2 e^{ i \phi_2 x } \\
   A_1^* e^{ - i \phi_1 x } + A_2^* e^{ -i \phi_2 x } & 0
   \end{pmatrix}
   \begin{pmatrix}
   \psi_{b1} \\
   \psi_{b2}
   \end{pmatrix}.

Notice that :math:`\phi_n` is always real but :math:`A_n` are either real or pure imaginary.

The matrix equation can be rewritten as systems of differential equations,

.. math::
   i \partial_x \psi_{b1} &= (A_1 e^{ i \phi_1 x } +A_2 e^{ i \phi_2 x } ) \psi_{b2}, \\
   i \partial_x \psi_{b2} & = (A_1^* e^{ - i \phi_1 x } + A_2^* e^{ -i \phi_2 x }) \psi_{b1}.

This set of equations is solved by rewrite them to a second order differential equation

.. math::
   \partial_x^2 \psi_{b2} + \frac{ A_1^* e^{ - i \phi_1 x } + A_2^* e^{ -i \phi_2 x }) }{\partial_x (A_1^* e^{ - i \phi_1 x } + A_2^* e^{ -i \phi_2 x }) } \partial_x \psi_{b2} + (A_1^* e^{ - i \phi_1 x } + A_2^* e^{ -i \phi_2 x }) (A_1 e^{ i \phi_1 x } +A_2 e^{ i \phi_2 x } ) \psi_{b2}.
   :label: two-n-list-second-order-eq-o-m

As a comparison, we also write down the equation for single n list,

.. math::
   \partial_x^2 \psi_{b2} + \left( \frac{i}{\phi_1}  \right) \partial_x \psi_{b2} + \lvert A_1 \rvert^2 \psi_{b2} = 0.


Approximations
-----------------


For single n list equation, the second term dominates if :math:`\phi_1` is much smaller than 1. In the language of physics, the second term dominates if the system is very close to resonance.

.. admonition:: :math:`\phi_n` and resonance
   :class: note

   :math:`\phi_n` is in fact the deviation from exact resonance.

   .. math::
      \phi_n = \sum_{a}^N n_a k_a - \omega_m.

In the multi-n-list case, this domination is easily destroyed. As an example, suppose we have :math:`A_1= A_2 = A` and :math:`\phi_2 = 10^{10}\phi_1`, the second term in equation :eq:`two-n-list-second-order-eq-o-m` becomes

.. math::
   \frac{ e^{ - i \phi_1 x } + e^{ -i 10^{10}\phi_1 x }) }{\partial_x (e^{ - i \phi_1 x } + e^{ -i 10^{10}\phi_1 x }) } \partial_x \psi_{b2} = \frac{ e^{ - i \phi_1 x } + e^{ -i 10^{10}\phi_1 x }) }{ (-i\phi_1 e^{ - i \phi_1 x } - i 10^{10}\phi_1 e^{ -i 10^{10}\phi_1 x }) } \partial_x \psi_{b2},

which can be dropped on as long as :math:`\phi_1` is not as small as :math:`10^{-10}`.

We exaggerated the situation.
