.. _Phase_space_Lagrangian:

Phase space Lagrangian
======================================
.. _Regular_derivation:

Regular derivation
-------------------

The climax part of classical mechanics lies in **the Lagrangian and Hamiltonian form**. It starts with the extremal principle, the real motion of a mechanical system is the one makes the variation of *the action* :math:`S` vanish, i.e.,

.. math::
   \delta S=\delta \int L(q,\dot{q},t) dt=0

When the Lagrangian is not depend on time explicitly, we get

.. math::
   \delta L=\frac{\partial L}{\partial q}\delta q+\frac{\partial L}{\partial \dot{q}}\delta \dot{q}=\frac{d}{dt}\left(\frac{\partial L}{\partial \dot{q}}\delta {q}\right)+\left[\frac{\partial L}{\partial q}-\frac{d}{dt}\frac{\partial L}{\partial \dot{q}}\right]\delta q

which gives us *the Lagrangian equation*:

.. math:: \frac{d}{dt}\frac{\partial L}{\partial \dot{q}}=\frac{\partial L}{\partial q}

Define the *canonical momentum* :math:`p=\frac{\partial L}{\partial \dot{q}}`, we have

.. math:: \dot{p}=\frac{\partial L}{\partial q}

We can easily prove that energy is an *integral of motion* (which is a conserved quantity in motion) based on the homogeneity of time. When the Lagrangian does not depend on time explicitly, we found that its total derivative is

.. math:: 
   \frac{dL}{dt}=&\frac{\partial L}{\partial q}\dot{q}+\frac{\partial L}{\partial \dot{q}} \ddot{q}\\
   =&\frac{d}{dt}\left(p\dot{q}\right)

We have used Lagrangian equation in the above derivation,and we have now

.. math:: \frac{d}{dt}\left(p\dot{q}-L\right)=0

indicating that :math:`H=p\dot{q}-L` is conserved in the motion, which is called *Hamiltonian* with physical meaning of energy.

On the other hand, from:

.. math::
   dL(q,\dot{q})=&\frac{\partial L}{\partial q}dq+\frac{\partial L}{\partial \dot{q}}d\dot{q} \\
   =&\dot{p}dq+pd\dot{q}\\
   =&\dot{p}dq+d(p\dot{q})-\dot{q}dp\\
   \Rightarrow d(p\dot{q}-L)=&-\dot{p}dq+\dot{q}dp\\
     dH(q,p)=&-\dot{p}dq+\dot{q}dp

which means :math:`dH` is the total differential with respect to :math:`q` and :math:`p`. And from:

.. math:: dH=\frac{\partial H}{\partial q}dq+\frac{\partial H}{\partial p}dp

we get

.. math:: \dot{p}=-\frac{\partial H}{\partial q} \qquad \dot{q}=\frac{\partial H}{\partial p}

This is the **Hamilton canonical equations**.

The total derivative with time is:

.. math:: 
   \frac{dH}{dt}=&\frac{\partial H}{\partial t}+\frac{\partial H}{\partial q}\dot{q}+\frac{\partial H}{\partial p}\dot{p} \\
   =&\frac{\partial H}{\partial t}

where Hamilton's equations are used. It also indicates that if H is not depend on time explicitly, we have the conservation of energy.

.. note::
   From Lagragian to Hamiltonian, we did a *Legendre transformation*, makes the dependence :math:`L(q,\dot{q},t)` to :math:`H(q,p,t)`, i.e., :math:`L` is a function in *configuration space* :math:`(q,\dot{q})`, but :math:`H` is in *phase space* :math:`(q,p)`.

.. _Dynamic_system:

Dynamic system
-------------------
Mathematically, a continuous-time dynamical system is defined to be a system of first order differential equations

.. math:: \dot{\mathbf{z}} = \mathbf{f}(\mathbf{z}, t) , \quad t \in \mathbb{R}

where :math:`\mathbf{f}` is known as the vector field and :math:`\mathbb{R}` is the set of real numbers. The space in which :math:`\mathbf{z}` is defined is called phase space.

Lagrange’s equations do not form a dynamical system, because they implicitly contain second-order derivatives, :math:`\ddot{q}`. However, there is a standard way to obtain a system of first-order equations from a second-order system, which is to double the size of the space of time-dependent variables by treating the generalized velocities :math:`u` as independent of the generalized coordinates, so that the dynamical system is :math:`\dot{q} = u, \dot{u} = \ddot{q}(q,u,t)`. Then the phase space is of dimension :math:`2n`. This trick is used very frequently in numerical problems, because the standard numerical integrators require the problem to be posed in terms of systems of first-order differential equations.

In the particular case of Lagrangian mechanics, expanding out :math:`\frac{d}{dt}\frac{\partial L}{\partial \dot{q}}` using the chain rule and moving all but the highest-order time derivatives to the right-hand side,

.. math:: \sum\limits_{j=1}^{n}\frac{\partial^2 L}{\partial \dot{q}_i \partial \dot{q}_j}\ddot{q}_j=\frac{\partial L}{\partial q_i}-\frac{\partial^2 L}{\partial \dot{q}_i \partial t}-\sum\limits_{j=1}^{n}\frac{\partial^2 L}{\partial \dot{q}_i \partial {q}_j}\dot{q}_j
The matrix :math:`H` acting on :math:`\ddot{q}`, whose elements are given by :math:`H_{i,j}\equiv\frac{\partial^2 L}{\partial \dot{q}_i \partial \dot{q}_j}`, is called the *Hessian matrix* . It is a kind of generalized mass tensor, and for our method to work we require it to be *nonsingular*, so that its inverse, :math:`H^{-1}`, exists and we can find :math:`\ddot{q}`. Then our dynamical system becomes:

.. math::
   \dot{q}=&u, \\
   \dot{u}=&H^{-1}\cdot\left[\frac{\partial L}{\partial q}-\frac{\partial L}{\partial \dot{q}\partial t}-\frac{\partial^2 L}{\partial \dot{q}\partial q}\cdot \dot{q}\right]

**Momentum instead of velocity**

We can achieve our aim of finding 2n first-order differential equations by using many choices of auxiliary variables other than :math:`u`. These will be more complicated functions of the generalized velocities, but the extra freedom of choice may also bring advantages.

In particular, Hamilton realized that it is very natural to use as the
new auxiliary variables the set :math:`p=\left\{p_i|i=1,\cdots,n\right\}` defined by

.. math:: p_i\equiv\frac{\partial}{\partial \dot{q}_i}L(q,\dot{q},t)

where :math:`p_i` is called the **canonical momentum** conjugate
to :math:`q_i`.

At this moment, we shall assume that the above equation can be solved to give :math:`\dot{q}` as a function of :math:`q` and :math:`p`

.. math:: \dot{q}=u(q,p,t).

The Lagrange's equations immediately give us

.. math:: \dot{p}=\frac{\partial L(q,\dot{q},t)}{\partial q}\left.\right|_{\dot{q}=u(q,p,t)}

The above two equations do indeed form a dynamical system, but so far it looks rather unsatisfactory: now :math:`u` is defined only implicitly as a
function of the phase-space variables :math:`q` and :math:`p`, yet the right-hand side of above equation involves a partial derivative in which the :math:`q`-dependence of
:math:`u` is ignored!

We can fix the latter problem by holding :math:`p` fixed in partial derivatives
with respect to :math:`q` (because it is an independent phase-space variable) but then subtracting a correction term to cancel the contribution coming from the :math:`q`-dependence of :math:`u`. Applying the chain rule, we get

.. math::
   \dot{p}=&\frac{\partial L(q,u,t)}{\partial q}-\frac{\partial L}{\partial u}\frac{\partial u}{\partial q} \\
   =&\frac{\partial L(q,u,t)}{\partial q}-p\frac{\partial u}{\partial q} \\
   =&\frac{\partial}{\partial q}\left[L(q,u,t)-p\cdot u\right] \\
   =&-\frac{\partial H}{\partial q}
where we have already defined the Hamiltonian :math:`H(q, p, t)= p\cdot u − L(q,u, t)` is a function of :math:`(q, p)`.

Given the importance of :math:`\partial H/ \partial q` it is natural to investigate whether :math:`\partial H/\partial p` plays a significant role as well. Differentiating :math:`H(q, p, t)= p\cdot u − L(q,u, t)` we get

.. math:: \frac{\partial H}{\partial p}=&u(q,p,t)-\left[p-\frac{\partial}{\partial u}L(q,u,t)\right]\frac{\partial u}{\partial p} \\
   =&\dot{q}

the above two equations are just the **Hamilton's equations** we derived before.

.. _Phase_space_Lagrangian
Phase space Lagrangian
------------------------------
The equation :math:`H(q,p,t)\equiv p\cdot\dot{q}-L(q,\dot{q},t)` suggest we define :math:`L_{ph}(q,\dot{q},p,t)\equiv p\cdot\dot{q}-H(q,p,t)`. If :math:`\dot{q}=u(q,p,t)` were identically satisfied, even on arbitrarily varied phase-space paths, then :math:`L_{ph}` would simply be :math:`L` expressed in phase-space coordinates.

However, one can easily construct a counter example to show that this is not the case: consider a variation of the path in which we can vary the direction of its tangent vector, at some point :math:`z\equiv (q, p)`, while keeping this
point fixed. Then :math:`\dot{q}` changes, but :math:`u` remains the same. Thus :math:`L_{ph}` and :math:`L` are the same value only on the subset of paths (which includes the physical paths) for which :math:`p\cdot\dot{q} = p\cdot u(q, p, t)` .

.. figure:: /CM/images/1.jpg
   :width: 50%
   :align: center

   **Fig. 1** Phase-space variations of different paths.

Replacing :math:`L` by :math:`L_{ph}` in :math:`S =
\int L dt` we define the phase-space action integral

.. math:: S_{ph}\left[q, p\right] = \int_{t_1}^{t_2}dt L_{ph}(q,p,\dot{q},t)=\int_{t_1}^{t_2}dt \left(p\cdot\dot{q}-H(q,p,t)\right)

We know from variational calculus that :math:`S_{ph}` is stationary under arbitrary
variations of the phase-space path (with endpoints fixed), explicitly, we get:

.. math:: 
   \delta S_{ph} =&\delta\int_{t_1}^{t_2}dt \left(p\cdot\dot{q}-H(q,p,t)\right) \\
   =&\int_{t_1}^{t_2}dt \left(\delta p\cdot\dot{q}+p\cdot\delta\dot{q}-\delta p \frac{\partial H(q,p,t)}{\partial p}-\delta q \frac{\partial H(q,p,t)}{\partial q}\right) \\
   =&p\delta q\left. \right |_{t_1}^{t_2}+\int_{t_1}^{t_2}dt \left\{\delta p\cdot\left[\dot{q}-\frac{\partial H(q,p,t)}{\partial p}\right]-\delta q\cdot\left[\dot{p}+ \frac{\partial H(q,p,t)}{\partial q}\right]\right\}

which gives us the **Hamilton's equations**:

.. math:: \dot{p}=-\frac{\partial H}{\partial q} \qquad \dot{q}=\frac{\partial H}{\partial p}

.. note::
   More generally, the phase-space Lagrangian can depend on :math:`\dot{p}` as well, and makes the Lagrange's equations become:

   .. math::
      \frac{\delta L_{ph}(q,\dot{q},p,\dot{p})}{\delta q}=&\frac{\partial L_{ph}}{\partial q}-\frac{d}{dt}\frac{\partial L_{ph}}{\partial \dot{q}}=0 \\
      \frac{\delta L_{ph}(q,\dot{q},p,\dot{p})}{\delta p}=&\frac{\partial L_{ph}}{\partial p}-\frac{d}{dt}\frac{\partial L_{ph}}{\partial \dot{p}}=0 


**References**

#. L.D. Landau & E.M. Lifshitz, *Mechanics*.
#. Lecture notes by **Bob Dewar** on website `Classical Mechanics <http://people.physics.anu.edu.au/~rld105/C01_ClassMech/>`_.

