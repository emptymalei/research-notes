Matter Stimulated Oscillation
============================================

We investigate a system with matter potential

.. math::
   \lambda(x) = \lambda_0 + \delta \lambda (x),

where :math:`\lambda_0 = \sqrt{2}G_F n_{e0}` and :math:`\delta \lambda(x) = \sqrt{2}G_F \delta n_e(x)`.




The Hamiltonian is

.. math::
   H = - \frac{\omega_m}{2} \sigma_3 + \frac{\delta \lambda}{2} \cos 2\theta_m \sigma_3 - \frac{\delta \lambda}{2} \sin \theta_m \sigma_1.


.. admonition:: Derive the Hamiltonian
   :class: note

   This Hamiltonian can be derived easily using

   .. math::
      H = -\frac{\omega_m}{3}\sigma_3 + \frac{\delta \lambda}{2} U^\dagger \sigma_3 U.



A Unitary Transformation
-----------------------------



Suppose the wave function in this basis is written as

.. math::
   \begin{pmatrix} \psi_1 \\ \psi_2 \end{pmatrix}.

To remove the position dependent :math:`sigma_3` term in the Hamiltonian which prevents us from solving the equation of motion easily, we use a new basis where the wave function is related to background matter basis through

.. math::
   \begin{pmatrix} \psi_1 \\ \psi_2 \end{pmatrix} = \begin{pmatrix} e^{-i \eta (x)} & 0 \\  0 & e^{-i \eta (x)}  \end{pmatrix} \begin{pmatrix} \psi_{b1} \\ \psi_{b2} \end{pmatrix}.


.. admonition:: Transformation of Pauli Matrices
   :class: note

   This transformation, defined as :math:`\mathbf{T}`, is unitary,

   .. math::
      \mathbf{T}^\dagger \mathbf{T} = \mathbf{I}.

   It doesn't change :math:`\sigma_3`.

   .. math::
      \mathbf{T} \sigma_3 \mathbf{T}^\dagger &= \sigma_3\\
      \mathbf{T}^\dagger \sigma_3 \mathbf{T} &= \sigma_3.

   It adds a phase to the off-diagonal elements of :math:`\sigma_1`,

   .. math::
      \mathbf{T} \sigma_1 \mathbf{T}^\dagger &= \begin{pmatrix} 0 & e^{-2i\eta} \\ e^{2 i\eta } & 0 \end{pmatrix} \\
      \mathbf{T}^\dagger \sigma_1 \mathbf{T} &= \begin{pmatrix} 0 & e^{2i\eta} \\ e^{-2 i\eta } & 0 \end{pmatrix}.



   We can also look at the following very general transformation.

   .. math::
      & \begin{pmatrix} e^{i\eta_1} & 0 \\ 0 & e^{-i\eta_1}\end{pmatrix} \begin{pmatrix} a_{11} & a_{12} \\ a_{21} & a_{22}\end{pmatrix}  \begin{pmatrix} e^{i\eta_2} & 0 \\ 0 & e^{-i\eta_2}\end{pmatrix} \\
      = & \begin{pmatrix} a_{11} e^{i(\eta_1+\eta_2)} & a_{12} e^{i(\eta_1 - \eta_2)} \\ a_{21} e^{-i(\eta_1-\eta_2)} & a_{22} e^{-i(\eta_1+\eta_2)}  \end{pmatrix}


The Schrodinger equation in background matter basis is

.. math::
   i\frac{d}{dx}\begin{pmatrix} \psi_{1} \\ \psi_2 \end{pmatrix} = \left(- \frac{\omega_m}{2} \sigma_3 + \frac{\delta \lambda}{2} \cos 2\theta_m \sigma_3 - \frac{\delta \lambda}{2} \sin \theta_m \sigma_1 \right) \begin{pmatrix} \psi_{1} \\ \psi_2 \end{pmatrix}

To write down the Schodinger equation in the new basis, we need the transformation of the Hamiltonian

.. math::
   \mathbf{T}^\dagger \cdot \mathrm{LHS} &= \mathbf{T}^\dagger\left[ i \begin{pmatrix} - i \frac{d\eta}{dx} e^{-i\eta} & 0 \\ 0 & i \frac{d\eta}{dx} e^{i\eta} \end{pmatrix} \begin{pmatrix} \psi_{b1} \\ \psi_{b2} \end{pmatrix} + i \begin{pmatrix}  e^{-i\eta} & 0 \\ 0  e^{i\eta} \end{pmatrix} \frac{d}{dx} \begin{pmatrix} \psi_1 \\ \psi_2 \end{pmatrix} \right] \\
   & =   i \begin{pmatrix} - i \frac{d\eta}{dx}  & 0 \\ 0 & i \frac{d\eta}{dx}  \end{pmatrix} \begin{pmatrix} \psi_{b1} \\ \psi_{b2} \end{pmatrix} + i \frac{d}{dx} \begin{pmatrix} \psi_1 \\ \psi_2 \end{pmatrix}  .


.. math::
   \mathbf{T}^\dagger \cdot \mathrm{RHS} &= \left[ -\frac{\omega_m}{2} \mathbf{T} ^\dagger \sigma_3 \mathbf{T} + \frac{\delta \lambda}{2} \cos 2\theta_m \mathbf{T}^\dagger \sigma_3 \mathbf{T} - \frac{\delta \lambda}{2} \sin 2\theta_m \mathbf{T}^\dagger \sigma_1 \mathbf{T}   \right] \begin{pmatrix} \psi_{b1} \\ \psi_{b2} \end{pmatrix} \\
   & =  \left[ -\frac{\omega_m}{2} \sigma_3  + \frac{\delta \lambda}{2} \cos 2\theta_m  \sigma_3  - \frac{\delta \lambda}{2} \sin 2\theta_m \begin{pmatrix} 0 & e^{2i\eta} \\ e^{-2 i\eta } & 0 \end{pmatrix}   \right] \begin{pmatrix} \psi_{b1} \\ \psi_{b2} \end{pmatrix} .


The equation of motion in this new basis becomes

.. math::
   \begin{pmatrix}  \frac{d\eta}{dx}  & 0 \\ 0 & - \frac{d\eta}{dx}  \end{pmatrix} \begin{pmatrix} \psi_{b1} \\ \psi_{b2} \end{pmatrix} + i \frac{d}{dx} \begin{pmatrix} \psi_1 \\ \psi_2 \end{pmatrix} =
   \left[ -\frac{\omega_m}{2} \sigma_3  + \frac{\delta \lambda}{2} \cos 2\theta_m  \sigma_3  - \frac{\delta \lambda}{2} \sin 2\theta_m \begin{pmatrix} 0 & e^{2i\eta} \\ e^{-2 i\eta } & 0 \end{pmatrix}   \right] \begin{pmatrix} \psi_{b1} \\ \psi_{b2} \end{pmatrix}

The key is to remove the :math:`\sigma_3` terms using this transformation, which requires

.. math::
   \begin{pmatrix}  \frac{d\eta}{dx}  & 0 \\ 0 & - \frac{d\eta}{dx}  \end{pmatrix} \begin{pmatrix} \psi_{b1} \\ \psi_{b2} \end{pmatrix} = \left[ -\frac{\omega_m}{2} \sigma_3  + \frac{\delta \lambda}{2} \cos 2\theta_m  \sigma_3 \right] \begin{pmatrix} \psi_{b1} \\ \psi_{b2} \end{pmatrix}.

It reduces to

.. math::
   \frac{d\eta(x)}{dx} = - \frac{\omega_m}{2} + \frac{\delta \lambda(x)}{2} \cos 2\theta_m ,

which has a general solution of the form

.. math::
   \eta(x) - \eta(0) = - \frac{\omega_m}{2} x + \frac{\cos 2\theta_m}{2} \int_0^x \delta\lambda (\tau) d\tau.

We might choose :math:`\eta(0)=0`, which simplifies the relation

.. math::
   \eta(x)= - \frac{\omega_m}{2} x + \frac{\cos 2\theta_m}{2} \int_0^x \delta\lambda (\tau) d\tau.


.. admonition:: Other Initial Conditions
   :class: note

   The initial condition can be other convinient ones. For example we can remove the integration constant of the last term in the relation.

At any position/time, the wave function in background matter basis is

.. math::
   \begin{pmatrix} \psi_1 (x) \\ \psi_2(x)  \end{pmatrix} = \begin{pmatrix} e^{- i \eta} \psi_{b1} (x) \\ e^{i\eta} \psi_{b2} (x)  \end{pmatrix}.
   :label: wavefunction-diff-basis

To calculated the transition from low energy state to high energy state in background matter basis, with initial condition

.. math::
   \begin{pmatrix} \psi_1 (0) \\ \psi_2(0)  \end{pmatrix} = \begin{pmatrix} 1 \\ 0  \end{pmatrix},

we simply calculate

.. math::
   P_{1 \to 2} (x) = \lvert e^{i\eta} \psi_{b2} (x)  \rvert^2 = \lvert \psi_{b2} (x)  \rvert^2 .




Single Frequency Matter Perturbation
------------------------------------------------------------------


As a first step, we solve single frequency matter perturbation

.. math::
   \delta \lambda(x)  = A \sin (k x + \phi).


Using the relation between :math:`\eta` and :math:`\delta\lambda`, we solve out :math:`\eta`.

.. math::
   \eta(x) = - \frac{\omega_m}{2}x + \frac{\cos 2\theta_m}{2} \frac{A}{k} \cos (k x + \phi),

where we have chosen :math:`\eta(0)=\frac{\cos 2\theta_m}{2}\frac{A}{k}\cos\phi`.

The problem is to solve the equation of motion

.. math::
   i \frac{d}{dx} \begin{pmatrix} \psi_{b1} \\ \psi_{b2} \end{pmatrix} = \frac{\sin 2\theta_m}{2}\delta\lambda(x) \begin{pmatrix} 0 &  e^{2i\eta(x)} \\   e^{-2i\eta(x)} &  0 \end{pmatrix}  \begin{pmatrix} \psi_{b1} \\ \psi_{b2} \end{pmatrix} .

We also define

.. math::
   h &= \frac{\sin 2\theta_m}{2}\delta\lambda(x)  e^{2i\eta(x)} \\
   & = \frac{\sin 2\theta_m}{2} A \sin (kx+\phi) e^{2i\left( -\frac{\omega_m}{2} x + \frac{A \cos 2\theta_m}{2k} \cos (kx+\phi) \right)}.
   :label: single-frequency-hamiltonian-element

Obviously, the exponential terms is too complicate. On the other hand, this equation of motion reminds us of the Rabi oscillation. So we decide to rewrite the exponential into some plane wave terms using Jacobi-Anger expansion. (Refs & Notes: Patton et al)

.. admonition:: Jacobi-Anger Expansion
   :class: note

   One of the forms of Jacobi-Anger expansion is

   .. math::
      e^{i z \cos (\Phi)} = \sum_{n=-\infty}^\infty i^n J_n(z) e^{i n\Phi}.
      :label: jacobi-anger-expansion


We define :math:`z_k = \frac{A}{k} \cos 2\theta_m`, with which we expand the term

.. math::
   e^{i\frac{\cos 2\theta_m A}{k} \cos (kx +\phi)} = \sum_{n=-\infty}^\infty i^n J_n (z_k) e^{in (kx +\phi)}.

The expansion is plugged into the Hamiltonian elements,

.. math::
   h &= \frac{A \sin 2\theta_m \sin (kx + \phi)}{2} e^{-i\omega_m x } \sum_{n = - \infty}^\infty i^n J_n(z_k) e^{i n ( kx + \phi)} \\
   & = \frac{A\sin 2\theta_m}{4i} \left( e^{i(kx + \phi)} - e^{-i(kx+\phi)} \right) e^{-i\omega_m x } \sum_{n = - \infty}^\infty i^n J_n(z_k) e^{i n ( kx + \phi)} \\
   & = \frac{A\sin 2\theta_m}{4i} \left( \sum_{n=-\infty}^\infty e^{i(n+1)} i^n J_n (z_k) e^{i((n+1) k - \omega_m)x}  - \sum_{n'=-\infty}^\infty e^{i(n'-1)} i^{n'}J_{n'}(z_k) e^{i( (n'-1)k - \omega_m)x}  \right).


Here comes the approximation. The most important oscillation we need is the one with largest period, which indicates the phase to be almost zero,

.. math::
   (n+1) k -\omega_m &\sim 0 \\
   (n'-1) k -\omega_m &\sim 0.
   :label: single-frequency-rwa-requirement


The two such conditions for the two summations are

.. math::
   n \equiv n_- &= \mathrm{Int}\left( \frac{\omega_m}{k} \right) - 1 \\
   n' \equiv n_+ &= \mathrm{Int}\left( \frac{\omega_m}{k} \right) + 1 .

We define :math:`\mathrm{Int}\left( \frac{\omega_m}{k} \right) = n_0`,

.. math::
   n_- &= n_0 - 1 \\
   n_+ &= n_0 + 1 .


The element of Hamiltonian is written as

.. math::
   h &= \frac{A\sin 2\theta_m}{4i} e^{in_0\phi}\left( i^{n_0-1} J_{n_0-1}(z_k) - i^{n_0+1} J_{n_0 +1}(z_k) \right) e^{i(n_0 k -\omega_m)x} \\
   & = \frac{A\sin 2\theta_m}{4i} e^{in_0\phi} i^{n_0-1}\left( J_{n_0-1}(z_k) + J_{n_0 +1}(z_k) \right) e^{i(n_0 k -\omega_m)x}.

Recall that for Bessel functions,

.. math::
   J_{n_0-1}(z_k) + J_{n_0+1}(z_k)  = \frac{2n_0+1}{z_k}J_{n_0}(z_k).

Then we have

.. math::
   h = \frac{A\sin 2\theta_m}{4} e^{in_0\phi} i^{n_0} \frac{2n_0+1}{z_k} J_{n_0 }(z_k) e^{i(n_0 k -\omega_m)x}.


To save keystrokes, we define

.. math::
   F = \frac{1}{4} A\sin 2\theta_m e^{i n_0 \phi} (- i^{n_0}) \frac{2n_0+1}{z_k} J_{n_0} (z_k) ,
   :label: definition-F

which depends on :math:`n_0` and :math:`z_k`.


.. admonition:: Solving Using Mathematica
   :class: hint

   The Mathematica code::

      In[1]:= sys = I D[{phi1[x], phi2[x]}, x] == {{0, (g0R + I g0I) Exp[ I (-omegam + n0 k) x]}, {(g0R - I g0I) Exp[-I (-omegam + n0 k) x], 0}}.{phi1[x], phi2[x]}
      In[2]:= DSolve[sys, {phi1, phi2}, x]// FullSimplify
      Out[3]:= {{phi1 -> Function[{x},
      E^(1/2 I (k n0 + I Sqrt[-4 (g0I^2 + g0R^2) - (k n0 - omegam)^2] - omegam) x) C[1]
      + E^(1/2 (Sqrt[-4 (g0I^2 + g0R^2) - (k n0 - omegam)^2] + I (k n0 - omegam)) x) C[2]],
      phi2 -> Function[{x}, (1/(2 (g0I - I g0R)))
      I E^(-I (k n0 - omegam) x +
       1/2 I (k n0 + I Sqrt[-4 (g0I^2 + g0R^2) - (k n0 - omegam)^2] - omegam) x)
       (k n0 + I Sqrt[-4 (g0I^2 + g0R^2) - (k n0 - omegam)^2] - omegam) C[1]
       + (1/(2 (g0I - I g0R))) E^(1/2 (Sqrt[-4 (g0I^2 + g0R^2) - (k n0 - omegam)^2]
       + I (k n0 - omegam)) x - I (k n0 - omegam) x) (Sqrt[-4 (g0I^2 + g0R^2) - (k n0 - omegam)^2]
       + I (k n0 - omegam)) C[2]]}}



The general solution to the equation of motion is

.. math::
   \psi_{b1} = & C_1 e^{\frac{1}{2} i \left( n_0 k -\omega_m - \sqrt{  4\lvert F \rvert^2 +  (n_0 k -\omega_m)^2 } \right)x} + C_2 e^{\frac{1}{2} i \left( n_0 k -\omega_m + \sqrt{  4\lvert F \rvert^2 +  (n_0 k -\omega_m)^2 } \right)x} \\
   \psi_{b2} = & \frac{C_1}{2F^*} i \left( n_0 k - \omega_m - \sqrt{ 4\lvert F\rvert^2 + ( n_0 k - \omega_m )^2 } \right) e^{ -\frac{1}{2}i (n_0 k - \omega_m ) x - \frac{1}{2} i \sqrt{ 4\lvert F \rvert^2 + (n_0 k - \omega_m )^2 }  } \\
   & + \frac{C_2}{2 F^*} i \left( n_0 k - \omega_m + \sqrt{ 4\lvert F\rvert^2 + ( n_0 k - \omega_m )^2 }  \right)   e^{ -\frac{1}{2}i (n_0 k - \omega_m ) x + \frac{1}{2} i \sqrt{ 4\lvert F \rvert^2 + (n_0 k - \omega_m )^2 }  } .

For simplicity, we define

.. math::
   g &= n_0 k  - \omega_m, \\
   l &= 4 \lvert F \rvert^2 + g^2.
   :label: definition-g-l


To determine the constants, we need intial condition,

.. math::
   \begin{pmatrix} \psi_1 (0) \\ \psi_2(0)  \end{pmatrix} = \begin{pmatrix} 1 \\ 0  \end{pmatrix} ,

which leads to

.. math::
   \begin{pmatrix} \psi_{b1} (0) \\ \psi_{b2}(0)  \end{pmatrix} = \begin{pmatrix} e^{i\eta(0)} \\ 0  \end{pmatrix},

using equation :eq:`wavefunction-diff-basis`.

Plug in the initial condition for the wave function,

.. math::
   C_1 + C_2 &= e^{i \frac{z_k}{2}\cos \phi} \\
   \frac{C_1}{2F^ * } i \left( g - \sqrt{l} \right) + \frac{C _ 2}{2 F ^ *} i \left( \sqrt{l} + g  \right) & = 0.


The constants are solved out

.. math::
   C_1 &= e^{i \frac{z_k}{2}\cos \phi} \frac{\sqrt{l} + g }{2\sqrt{l}} , \\
   C_2 &= e^{i \frac{z_k}{2}\cos \phi} \frac{ \sqrt{l} - g }{2\sqrt{l}}.


where :math:`F` is defined in :eq:`definition-F` and :math:`l` and :math:`g` are defined in :eq:`definition-g-l`.


The second element of wave function becomes

.. math::
   \psi_{b2}(x) = \frac{- 2 F}{\sqrt{l}} e^{i\frac{z_k}{2} \cos\phi} e^{- \frac{i}{2}gx} \sin \left( \frac{1}{2}\sqrt{l} x \right).


The transition probability becomes

.. math::
   P_{1\to 2} = \lvert \psi_{b2} \rvert^2 = \frac{4 \lvert F \rvert^2}{l} \sin^2\left( \frac{\sqrt{l} }{2} x \right).



.. admonition:: Compare The Result with Kneller et al
   :class: note

   Kneller et al have a transition probability

   .. math::
      \color{red}P_{12} = \frac{\kappa_n^2}{q_n^2} \sin^2 (q_n x),

   where :math:`\color{red}q_n^2 = k_n^2 + \kappa_n^2` and :math:`\color{red}2k_n = \tilde{\delta k}_{12} + n k_\star`.

   In my notation, :math:`k` is the same as their :math:`\color{red}k_\star`. After the first step of translation, we have :math:`g = \color{red} 2 k_n`.

   The definition of :math:`\color{red}\kappa_n` is given by

   .. math
      \color{red}\kappa_{ij,n} = (-i)^{n-1} \frac{n C_\star V_\star}{z_{ij}} J_n(z_{ij}) \tilde U_{ei}^* \tilde U_{ej} e^{i ( n \eta + z_{ij} \cos \eta)},

   in Kneller's notation and

   .. math::
      \delta V_{ee}(x) = C_\star V_\star \sin (k_\star x + \eta).

   So we conclude that my :math:`\lvert F \rvert ^2` is related to Kneller's :math:`\lvert \kappa_n \rvert^2` through

   .. math::
      \lvert F \rvert^2 = \color{red} \lvert \kappa_n \rvert^2.

   We also have

   .. math::
      l = 4 \lvert F \rvert ^2 + g  = 4 \color{red} q_n^2,

   i.e., :math:`{\color{red}q_n} = \frac{\sqrt{l} }{2}`.

   Now we see the method we have used gives exactly the same transition probability as Kneller's.



Physics Behind The Math
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~


There are several question to answer before we can understand the picture of the math.

1. What does each term mean in the Hamiltonian?
2. What exactly is the unitary transformation we used to rotate the wave function?
3. What is the physical meaning of Jacobi-Anger expansion in our calculation?


To answer the first question, we need to write down the solution to Schrodinger equation assuming the Hamiltonian has only one term. The results are listed below.

============================================================ =================================================================================================================================
Hamiltonian                                                       Solution to The First Element of Wave Function
============================================================ =================================================================================================================================
.. math:: -\frac{\omega_m}{2}\sigma_3                           .. math:: \psi_1 \sim e^{i\omega_m x/2}
.. math:: \frac{\delta\lambda}{2}\cos 2\theta_m \sigma_3        .. math:: \psi_1 \sim e^{i\frac{A\cos 2\theta_m}{2k}\cos(kx+\phi)}
.. math:: \frac{\delta\lambda}{2}\cos 2\theta_m \sigma_3        .. math:: \psi_1 = C_1 e^{i\frac{A\sin 2\theta_m}{2k}\cos(kx+\phi)} + C_2 e^{-i\frac{A\sin 2\theta_m}{2k}\cos(kx+\phi)}
============================================================ =================================================================================================================================


The unitary transformation used is to move our reference frame to a co-rotating one. :math:`-\frac{\omega_m}{2}\sigma_3` is indeed causing the wave function to rotate and removing this term using a transformation means we are co-rotating with it. :math:`\frac{\delta\lambda}{2}\cos 2\theta_m \sigma_3` causes a more complicated rotation however it is still a rotation.



As for Jacobi-Anger expansion, it expands an oscillating matter profile to infinite constant matter potentials. To see it more clearly, we assume that :math:`\delta\lambda= \lambda_c` is constant. After the unitary transformation, the effective Hamiltonian is

.. math::
   H' = \frac{\sin 2\theta_m}{2} \lambda_c \begin{pmatrix} 0 & e^{2i\eta(x)} \\ e^{-2i\eta(x)} & 0 \end{pmatrix},

where :math:`\eta(x) = -\frac{\omega_m}{2}x + \frac{\cos 2\theta_m}{2}\lambda_c x` and we have chosen :math:`\eta(0)=0`.

The 12 element of the Hamiltonian becomes

.. math::
   \frac{\sin 2\theta_m}{2} \lambda_c e^{2i\eta(x)} = \frac{\sin 2\theta_m}{2} \lambda_c e^{2i\left( \frac{\omega_m}{2} + \frac{\cos 2\theta_m}{2} \lambda_c \right)x} .

The significance of it is to show that a constant matter profile will result in a simple exponential term. However, as we move on to periodic matter profile, we have a Hamiltonian element of the form

.. math::
   h = \frac{\sin 2\theta_m}{2} A \sin (kx+\phi) e^{2i\left( -\frac{\omega_m}{2} x + \frac{A \cos 2\theta_m}{2k} \cos (kx+\phi) \right)},

as derived in equation :eq:`single-frequency-hamiltonian-element`. To compare with the constant matter case, we make a table of relevant terms in Hamiltonian.

================================================================================   ========================================================================
Constant Matter Profile :math:`\delta\lambda = \lambda_c`                           Period Matter Profile :math:`\delta\lambda=A\sin (kx+\phi)`
================================================================================   ========================================================================
.. math:: \frac{\sin 2\theta_m}{2}\lambda_c e^{i \cos 2\theta_m \lambda_c x}         .. math:: \frac{\sin 2\theta_m}{2} A \sin (kx+\phi) e^{i\frac{A\cos 2\theta_m}{k} \cos (kx+\phi) }
================================================================================   ========================================================================

The periodic profile comes into the exponential. Jacobi-Anger expansion (equation :eq:`jacobi-anger-expansion`) expands the periodic matter profile into infinite constant matter profiles.

The RWA approximation we used to drop fast oscillatory terms in the summation is to find the most relevant constant matter profile per se.

The big question is which constant matter profiles are the most important ones? Mathematically, we require the phase to be almost zero, i.e. equation :eq:`single-frequency-rwa-requirement` or

.. math::
   n_0 k - \omega_m \sim 0 ,

where :math:`n_0=\mathrm{Int}\left( \frac{\omega_m}{k} \right)`.


**What is the meaning of this condition in this new basis?**









Refs & Notes
------------------------

1. Patton, K. M., Kneller, J. P., & McLaughlin, G. C. (2014). Stimulated neutrino transformation through turbulence. Physical Review D, 89(7), 073022. doi:10.1103/PhysRevD.89.073022
2. Kneller, J. P., McLaughlin, G. C., & Patton, K. M. (2013). Stimulated neutrino transformation in supernovae. AIP Conference Proceedings, 1560, 176–178. doi:10.1063/1.4826746
