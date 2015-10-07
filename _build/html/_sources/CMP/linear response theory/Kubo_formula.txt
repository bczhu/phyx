.. _Kubo_formula:

***************
Kubo formula
***************

Many times, the world shows us as a **black box**, we can only get limited knowledge about it and the rest are filled with our *theories*, in this way, theories can always changing and are never completed. we always use a probe to probe a system and check its response to this probe, and naturally, we expect when the perturbation of the probe is ignorable to the system, the response should be linear to the probe, which is called **linear response theory**. The most important result of linear response theory is consummated by *Kubo formula*, we are now going to derive it. 

.. _Zero_temperature:

Zero temperature
=============================

Let :math:`\hat{H}_0` be the full many-body Hamiltonian for some isolated system that we are interested in, and assume the existence of a set of eigenkets :math:`\{|n\rangle\}` that diagonalize :math:`\hat{H}_0` with associated 
eigenvalues (energies) :math:`\varepsilon_n`. 

In addition to :math:`\hat{H}_0`, we now turn on an external probe potential :math:`\hat{V}(t)`, such that the total Hamiltonian :math:`\hat{H}(t)` satisfies:

.. math::

  \hat{H}(t)=\hat{H}_0+e^{\eta t}\hat{V}(t)

.. note::
  The additional factor :math:`e^{\eta t}` means we switch on the external potential adiabatically from :math:`t\to -\infty`, we'll see later that it is this factor gives us the way to detour the *singular points*, it is an *analytical continuation* which is a reflection of *causality*.

The Schrödinger equation of the system now reads:

.. math::
  
  i\hbar\frac{\partial}{\partial t}|\psi(t)\rangle=(\hat{H}_0+e^{\eta t}\hat{V}(t))|\psi(t)\rangle


.. warning::
   us the way to detour the singular points, it is an analytical continuation which is a reflection of causality.

.. important::
   us the way to detour the singular points, it is an analytical continuation which is a reflection of causality.

.. hint::
   us the way to detour the singular points, it is an analytical continuation which is a reflection of causality.

