---
title: Problem Set 3
summary: Fermi gas; Superconductivity; Response and Correlation; Jellium.
author: Austen Lamacraft
draft: false  # Is this a draft? true/false
toc: true  # Show table of contents? true/false
type: docs  # Do not modify.
markup: pandoc
menu:
  tqm:
    parent: Problem Sets
    weight: 3
---



$$
\nonumber
\newcommand{\cN}{\mathcal{N}}
\newcommand{\br}{\mathbf{r}}
\newcommand{\bp}{\mathbf{p}}
\newcommand{\bk}{\mathbf{k}}
\newcommand{\bq}{\mathbf{q}}
\newcommand{\bv}{\mathbf{v}}
\newcommand{\pop}{\psi^{\vphantom{\dagger}}}
\newcommand{\pdop}{\psi^\dagger}
\newcommand{\Pop}{\Psi^{\vphantom{\dagger}}}
\newcommand{\Pdop}{\Psi^\dagger}
\newcommand{\Phop}{\Phi^{\vphantom{\dagger}}}
\newcommand{\Phdop}{\Phi^\dagger}
\newcommand{\phop}{\phi^{\vphantom{\dagger}}}
\newcommand{\phdop}{\phi^\dagger}
\newcommand{\aop}{a^{\vphantom{\dagger}}}
\newcommand{\adop}{a^\dagger}
\newcommand{\bop}{b^{\vphantom{\dagger}}}
\newcommand{\bdop}{b^\dagger}
\newcommand{\cop}{c^{\vphantom{\dagger}}}
\newcommand{\cdop}{c^\dagger}
\newcommand{\Nop}{\mathsf{N}^{\vphantom{\dagger}}}
\newcommand{\bra}[1]{\langle{#1}\rvert}
\newcommand{\ket}[1]{\lvert{#1}\rangle}
\newcommand{\inner}[2]{\langle{#1}\rvert #2 \rangle}
\newcommand{\braket}[3]{\langle{#1}\rvert #2 \lvert #3 \rangle}
\DeclareMathOperator{\sgn}{sgn}
\DeclareMathOperator{\tr}{tr}
\newcommand{\abs}[1]{\lvert{#1}\rvert}
\newcommand{\brN}{\br_1, \ldots, \br_N}
\newcommand{\xN}{x_1, \ldots, x_N}
\newcommand{\zN}{z_1, \ldots, z_N}
$$

## $N(\bk)$ in the Ground State

In second order perturbation theory, find the occupation number $N(\bk)=\braket{0}{\adop_{\bk,s}\aop_{\bk,s}}{0}$ in the ground state of the interacting Fermi gas. Compare with the quantity $z_\bk$ introduced in the lecture.

## Pair Correlations in the BCS State

As well as the average occupancy of a given momentum state we can consider the correlations between
the occupancy of different $\bp$ states

$$
C_{ss'}(\bp,\bp')\equiv\langle n_{\bp,s} n_{\bp',s'}\rangle-\langle n_{\bp,s}\rangle\langle n_{\bp',s'}\rangle
$$

Show that for the BCS state

$$
\begin{align}
C_{\uparrow\downarrow}(\bp_1,\bp_2)&=\delta_{\bp_1,-\bp_2}u_{\bp_1}^2v_{\bp_1}^2=\delta_
{\bp_1,-\bp_2}\frac{|\Delta|^2}{4E_{\bp_1}^2}\nonumber\\
C_{\uparrow\uparrow}(\bp_1,\bp_2)&=\delta_{\bp_1,\bp_2}\frac{|\Delta|^2}{4E_{\bp_1}^2}
\end{align}
$$

Interpret these two expressions.

## A Very Simple Model for Phonon Mediated Attraction

An optical phonon mode gives rise to an oscillating charge that couples to the electrons at a site. We model this by the Hamiltonian

$$
H = \frac{p^2}{2m}+\frac{1}{2}m\omega^2 x^2 + \alpha x\left(N_\uparrow+N_\downarrow\right),
$$

where $N_s=0,1$ are the number of electrons of spin $s$ at the site. Since $N_s$ is conserved you can solve the model exactly.

Next, introduce an oscillator at each site of a Fermi Hubbard model

$$
H = H_\text{Hubbard} + \sum_j \left[\frac{p_j^2}{2m}+\frac{1}{2}m\omega^2 x_j^2 + \alpha x_j\left(N_{j,\uparrow}+N_{j,\downarrow}\right)\right].
$$

If the energy $\omega$ of the oscillators is larger than other scales, you can use the technique from [Lecture 7]({{< ref "lattice-models" >}}) to derive an effective Hamiltonian. What form does this take?

The physics behind this mechanism is a very simple consequence of living in an elastic medium, and is not really a quantum effect at all. The fact that two heavy spheres on a stretched horizontal rubber sheet will roll towards each other is a nearly perfect analogy for this effect (as well as a very poor one for gravitational attraction in GR!).

## An Inequality for the Static Structure factor

Use the f-sum and compressibility sum rules, together with the [Cauchy-Schwarz inequality](https://en.wikipedia.org/wiki/Cauchy–Schwarz_inequality#L2)

$$
\abs{\int f(x)g^*(x) dx}^2 \leq \int \abs{f(x)}^2 dx \int \abs{g(x)}^2 dx
$$

to obtain the __Onsager bound__ on the static structure factor

$$
	\lim_{\bq\to 0}\frac{S_\rho(\bq)}{\abs{\bq}}\leq \frac{N}{2mc}
$$

## $S_\rho(q,\omega)$ for 1D Fermi Gas

Find the dynamical structure factor for a 1D Fermi gas, and verify the Onsager bound.

## $S_\rho(q)$ for the Elastic Chain

In [Lecture 3]({{< ref "elastic-chain" >}}) we found the static structure factor of the elastic chain. Verify the Onsager bound.

## Ground State Energy of Jellium in Perturbation Theory

In [Lecture 9]({{< ref "fermi-gas" >}}) we found the corrections to the eigenenergies of a Fermi gas to second order in the interaction. Show that for Jellium the correction to the ground state energy has an infrared divergence.

## Limits of the Polarization

Check the two limits for the polarization described at the end of [Lecture 12]({{< ref "jellium" >}}).

## Explicit Evaluation of Green's Functions

Starting from the definition of the fermion Green's function, show that

$$
G_\bk(\tau) = e^{-\xi(\bk)\tau}\begin{cases}
	1-\langle N_\bk\rangle & \tau>0\\
	-\langle N_\bk \rangle & \tau<0
	\end{cases}
	\label{Gexp}
$$		

where $\langle N_\bk\rangle = n_\text{F}(\xi(\bp))$, and $n_\text{F}(\omega)=\frac{1}{e^{\beta\omega}+1}$ is the Fermi--Dirac distribution.

We also have

$$
G_\bk(\tau) = T\sum_{\epsilon_n} \frac{e^{-i\epsilon_n \tau}}{-i\epsilon_n+\xi(\bk)}.
$$

Evaluate the sum to find \eqref{Gexp}. In the lecture, we used the auxillary function $\tanh\left(\frac{\beta\epsilon}{2}\right)$ to turn the Matsubara sum into an integral. Here, to be able to deform the contour in a useful way, we must use $n_\text{F}(\omega)$ or $1-n_\text{F}(\omega)$.
