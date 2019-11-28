---
title: Jordan-Wigner and Bosonization
summary: Spin-1/2 XY model as a system of free fermions. Bosonization.
author: Austen Lamacraft
draft: false  # Is this a draft? true/false
toc: true  # Show table of contents? true/false
type: docs  # Do not modify.
markup: pandoc
menu:
  tqm:
    parent: Lectures
    weight: 12
---

$$
\nonumber
\newcommand{\cN}{\mathcal{N}}
\newcommand{\cC}{\mathcal{C}}
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
\newcommand{\bra}[1]{\langle{#1}\rvert}
\newcommand{\ket}[1]{\lvert{#1}\rangle}
\newcommand{\inner}[2]{\langle{#1}\rvert #2 \rangle}
\newcommand{\braket}[3]{\langle{#1}\rvert #2 \lvert #3 \rangle}
\newcommand{\sgn}{\mathrm{sgn}}
\newcommand{\brN}{\br_1, \ldots, \br_N}
\newcommand{\xN}{x_1, \ldots, x_N}
\newcommand{\zN}{z_1, \ldots, z_N}
\newcommand{\abs}[1]{\lvert{#1}\rvert}
$$

Jordan and Wigner's 1927 paper introduced the canonical anti-commutation relations for fermions. Seeking an explicit representation of the operators, they established a mapping between fermion and spin-1/2 operators. Much later, it was realized that this mapping turns certain spin chain Hamiltonians into systems of free fermions, providing a rather elementary exact solution. In this lecture, we'll explore some of things we can do with this transformation, as well as an alternative way of looking at 1D systems called  __bosonization__.

---

## From Fermions to Spins (and Back)

It's not too hard to find a matrix representation of the bosonic creation and annihilation operators satisfying

$$
\left[\aop,\adop\right]=1.
\label{car}
$$

The action of $\adop$ on the occupation number eigenstate $\ket{n}$ is of course

$$
\adop\ket{n}=\sqrt{n}\ket{n+1}
$$

In this basis the creation operator therefore has the form

$$
\mathsf{A}_\text{B}^\dagger = \begin{pmatrix}
0 & 0 & 0 & 0 & \cdots & 0 \\
1 & 0 & 0 & 0 &\cdots & 0 \\
0 & \sqrt{2} & 0 & 0 & \cdots &\cdots\\
0  &0   &\sqrt{3}  &0  &\cdots  &\cdots  \\
0 & \cdots  & \cdots  &\cdots  & \cdots & \cdots  
\end{pmatrix},
$$

with $\mathsf{A}_\text{B}$ being given by the hermitian conjugate.

> Check that $\eqref{car}$ is satisfied by this representation

If we have _two_ bosons, $\aop$, $\adop$, and $\bop$, $\bdop$, they act independently on their occupation number states, for example

$$
\adop \ket{n_a}_a\otimes\ket{n_b}_b = \left(\adop \ket{n_a}_a\right)\otimes\ket{n_b}_b = \sqrt{n_a}\ket{n_a}_a\otimes\ket{n_b}_b.
$$

Thus we represent

$$
\adop = \mathsf{A}_\text{B}^\dagger\otimes\mathbb{1},\qquad \bdop = \mathbb{1}\otimes\mathsf{A}_\text{B}^\dagger
$$

What about fermions? Here the occupancy of a state can only be zero or one, and it's not hard to show that the fundamental anticommutator

$$
\left\{\aop,\adop\right\}=1
$$

has the possible representation

$$
\begin{pmatrix}
0 & 0 \\
1 & 0
\end{pmatrix}.
$$

In fact, because of the symmetry between the empty and filled state, we could just as well take

$$
\mathsf{A}^\dagger_\text{F} = \begin{pmatrix}
0 & 1 \\
0 & 0
\end{pmatrix}.
$$

We will in fact stick with the latter choice. For two fermions, we have a problem. If we try

$$
\adop \overset{?}{=} \mathsf{A}_\text{F}^\dagger\otimes\mathbb{1},\qquad \bdop \overset{?}{=} \mathbb{1}\otimes\mathsf{A}_\text{F}^\dagger,
$$

then $\adop$ and $\bdop$ _commute_, rather than anticommute. At this point, let's switch to Pauli matrix notation: $\mathsf{A}^\dagger_\text{F}=\sigma^+$, $\mathsf{A}_\text{F}=\sigma^-$. Since different Pauli matrices anticommute, we also have

$$
\left\{\sigma^{\pm},\sigma^z\right\}=0.
$$

Thus one (somewhat asymmetrical) solution to our problem is to take

$$
\adop = \sigma^+\otimes\mathbb{1},\qquad \bdop = \sigma^z\otimes\sigma^+.
$$

It turns out that this trick generalizes. For three fermions, for example

$$
\begin{align}
\adop &= \sigma^+\otimes\mathbb{1}\otimes\mathbb{1},\\
\bdop &= \sigma^z\otimes\sigma^+\otimes\mathbb{1},\\
\cdop &= \sigma^z\otimes\sigma^z\otimes\sigma^+,\\
\end{align}
$$

and so on. For $N$ fermions we can write

$$
\adop_j = \overbrace{\sigma^z \otimes \cdots \otimes \sigma^z}^{j-1 \text{ times}}\otimes \sigma^+ \otimes \overbrace{\mathbb{1}\otimes \cdots \otimes\mathbb{1}}^{N-j \text{ times}}.
$$

Normally, we disinguish the different spin operators by an index rather than the place they occur in the tensor product, and write

$$
\adop_j = \left(\prod_{k=1}^{j-1}\sigma^z_k\right) \sigma^+_j.
$$

For applications, we are mostly interested in the _inverse_ transformation, expressing spins in terms of fermions. Notice that $\sigma^z_j$ is simply related to the number operator

$$
\sigma^z_j = 2\adop_j\aop_j-1 = 2n_j-1,
$$

Alternatively

$$
\sigma^z_j = -\exp(i\pi n_j),
$$

in which case

$$
\sigma^+_j = (-1)^{j-1}\exp\left(i\pi\sum_{k=1}^{j-1}n_k\right)\adop_j.
$$

That $(-1)^{j-1}$ at the front is a bit annoying. If we just define it away all the required algebraic relations are still preserved, leaving

$$
\sigma^+_j = \exp\left(i\pi\sum_{k=1}^{j-1}n_k\right)\adop_j.
\label{JW}
$$



### Solving the XY Model

The XY model is a particular case of the anisotropic spin chain (see [Problem Set 1]({{ site.baseurl }}/problems/Problems1/)) in which only the $x$ and $y$ components of the spins are coupled (hence the name)

$$
\begin{align}
H &= -J\sum_j\left[s^x_js^x_{j+1}+s^y_js^y_{j+1}\right]\\
&=-\frac{J}{2}\sum_j\left[\sigma^+_j\sigma^-_{j+1}+\sigma^-_j\sigma^+_{j+1}\right],
\end{align}
$$

In [Lecture 4]({{ site.baseurl }}/lectures/SpinModels/) we saw that the XY term can be interpreted as describing the hopping of magnons, or spin flips. Now, applying the mapping $\eqref{JW}$, we see that it can equally be interpreted in terms of fermion hopping

$$
\sigma_j^+\sigma_{j+1}^-=\adop_j e^{i\pi n_j}\aop_{j+1}=\adop_j\aop_{j+1}.
$$

The last equality follows from the fact that, in order to create a particle at site $j$ the site must first be empty, so that the exponential is just 1. In this way we see that the XY Hamiltonian describes free fermions

$$
H=-\frac{J}{2}\sum_j\left[\adop_j\aop_{j+1}+\adop_{j+1}\aop_{j}\right].
\label{FreeFermion}
$$

Note that it is _essential_ that we are in one dimension. The Jordan--Wigner mapping could of course be made in any dimension, but it depends on the particular choice of the labelling of the spins. In two dimensions, for example, it is not possible to choose that labelling so that all hopping terms $\sigma^+_i\sigma_j$ for nearest neighbours are expressed simply in terms of the fermions. Rather, there would be non-trivial exponential factors left over.

Diagonalizing a finite chain described by $\eqref{FreeFermion}$ is of course straightforward if we choose periodic boundary conditions for the $\adop_j$, $\aop_j$. However, if the physical degrees of freedom are the spins, we should impose periodic boundary conditions on these operators instead. How does this affect the fermion system? We have

$$
\adop_N\aop_1 = e^{i\pi\sum_{j=1}^{N-1}n_j}\sigma^+_N\sigma^-_1 = - e^{i\pi N_a}\sigma^+_N\sigma^-_1
$$

where $N_a\equiv \sum_j n_j$. The second equality follows from the observation that, after moving a particle to the site $N$, there are certainly $N_a-1$ particles on the other sites.

Thus the fermions obey (anti-)periodic boundary conditions when $N_a$ is odd (even). As usual, we can solve the Hamiltonian with the aid of the plane wave states

$$
\begin{align}
\aop_j &= \frac{1}{\sqrt{N}}\sum_{k} e^{ik j} \eta_k\\
\adop_j &= \frac{1}{\sqrt{N}}\sum_{k} e^{-i k j} \eta^\dagger_k,
\end{align}
$$

where

$$
k = \begin{cases}
\frac{2\pi}{N}\times\text{ integer} & N_a \text{ odd}\\
\frac{2\pi}{N}\times\left(\text{ integer}+\frac{1}{2}\right) & N_a \text{ even}.
\end{cases}
$$

In either case, the Hamiltonian $\eqref{FreeFermion}$ can be written

$$
H = \sum_k \epsilon(k)\eta^\dagger_k\eta_k,\qquad \epsilon(k)=-J\cos(k)
$$

Since $S^z_\text{tot}=2N_a-N$, the filling is determined by the total magnetization. In particular $S^z_\text{tot}=0$ corresponds to half filling.

We've actually met this before, albeit in a different guise. Recall that in [Lecture 1]({{ site.baseurl }}/lectures/ManyBodyWavefunctions/) we saw that the impenetrable Bose gas in one dimension can be understood in terms of noninteracting fermions. Spin-1/2 degrees of freedom are just a lattice version of hardcore fermions, and the Jordan--Wigner string serves to turn an antisymmetric fermionic wavefunction into a bosonic one. To formally recover the Bose gas without a lattice we would have to consider the limit of very low filling.

### Spin Correlations

Solving for the eigenstates of a model is one thing, but as we've seen before, it's quite another to be able to compute correlation functions. But let's start with something simple, and consider the correlation function of the $z$-components of the spins

$$
\begin{align}
\cC^{zz}(j-k)=\braket{0}{\sigma^z_j \sigma^z_k}{0}&=\braket{0}{(2n_j-1)(2n_k-1)}{0}\\
&=4\braket{0}{n_j n_k}{0}-4\braket{0}{n_j}{0}+1.
\end{align}
$$

Evidently, this is related to the density correlations in the Fermi gas. Its Fourier transform, defined by

$$
\cC^{zz}(j-k) = \frac{1}{N}\sum_q e^{iq(j-k)}\cC^{zz}_q,
$$

is

$$
\cC^{zz}_q = \frac{4}{N}\sum_k N_k(1-N_{k+q}),\quad q\neq 0
$$

where $N_k=\braket{0}{\eta^\dagger_k\eta_k}{0}$ is the occupation number of the ground state. We find

$$
\cC^{zz}_q = \begin{cases}
\frac{2\abs{q}}{\pi} & \abs{q}<2k_\text{F}\\
\frac{4N_a}{N} & \abs{q}>2k_\text{F},
\end{cases}
$$

where the Fermi momentum $k_\text{F}=\frac{\pi N_a}{N}$.

What about the _transverse_ spin correlations

$$
\cC^{+-}(j-k)=\braket{0}{\sigma^+_j\sigma^-_k}{0}?
$$

In the hardcore boson picture, the transverse correlations are just the one body density matrix, so the Fourier transform would tell us about the occupation numbers of the single particle plane wave states in the many body ground state.

Writing $\cC^{+-}(j-k)$ in terms of the fermions gives

$$
\begin{align}
\cC^{+-}(j-k)=\begin{cases}
\braket{0}{\adop_j\exp\left(i\pi \sum_{l=k}^{j-1}n_l\right)\aop_k}{0}&  j>k\\
\braket{0}{\adop_j\exp\left(i\pi \sum_{l=j}^{k-1}n_l\right)\aop_k}{0}&  j<k.
\end{cases}
\label{Transverse}
\end{align}
$$

We see that the computation of the transverse correlations in terms of fermions is fundamentally harder than the longitudinal correlations, as it the nonlocality of the Jordan--Wigner mapping comes into play.

It is possible to use Wick's theorem at this point to evaluate $\eqref{Transverse}$ in terms of the (equal time) Green's function of the fermions. However, we'll pursue a different approach, based upon yet another way of representing the degrees of freedom.

## The Quantum Ising Model and Kitaev's Chain

Another model that can be solved using the Jordan--Wigner transformation is the __quantum Ising chain__, with Hamiltonian

$$
H=\sum_j\left[g\sigma_j^z - J\sigma_{j}^x\sigma_{j+1}^x\right].
$$

The second term looks like the familiar Ising model energy, with the spin variable identified with the $x$-component of spin (for a change). Applying the Jordan—Wigner transformation we end up with the equivalent fermion Hamiltonian
$$
\begin{align}\label{eq:fermi-ising}
H &= \sum_j\left[g\left(2\adop_j\aop_j-1\right) -J\left(\adop_j-\aop_{j}\right)\left(\adop_{j+1}+\aop_{j+1}\right)\right]\\
&= \sum_j\left[-t\left(\adop_j\aop_{j+1}+\adop_{j+1}\aop_{j}\right)-\mu\left(\adop_j\aop_j-\frac{1}{2}\right)+\Delta\aop_j\aop_{j+1}+\Delta^*\adop_j\adop_{j+1}\right].
\end{align}
$$
In the second line we have written the Hamiltonian more suggestively by introducing
$$
\begin{align}\label{eq:ising-vals}
t = J\qquad \mu=-2g\qquad \Delta=-J.
\end{align}
$$
In this way the Hamiltonian resembles a BCS mean-field Hamiltonian with an unusual order parameter $\Delta$ that sits between two sites. 

With periodic boundary conditions $\aop_1=\aop_{N+1}$ the Hamiltonian $\eqref{eq:fermi-ising}$ can be solved by the Bogoliubov transformation by first introducing the mode expansion
$$
\aop_j = \frac{1}{\sqrt{N}}\sum_\eta e^{i\eta j}\aop_\eta\qquad \eta=2\pi n/N
$$
In terms of the plane wave operators, the Hamiltonian has the form

$$
H = \sum_\eta\left[-2t\cos(\eta)\adop_\eta\aop_{\eta}-\mu\left(\adop_\eta\aop_\eta-\frac{1}{2}\right)+\Delta e^{i\eta}\aop_\eta\aop_{-\eta}+\Delta^*e^{-i\eta}\adop_\eta\adop_{-\eta}\right].
$$

We can write this in matrix form, paying attention to the _anti-_commutation relations of the fermions, as
$$
\begin{equation}\label{eq:bdg}
H = \sum_\eta \begin{pmatrix}
\adop_\eta &
\aop_{-\eta}
\end{pmatrix} 
\begin{pmatrix}
-t\cos(\eta) -\mu/2 & -i\Delta\sin(\eta)\\
i\Delta^*\sin(\eta) & t\cos(\eta) +\mu/2
\end{pmatrix}
\begin{pmatrix}
\aop_\eta \\
\adop_{-\eta}
\end{pmatrix}.
\end{equation}
$$


In this format it's easy to see that a $2\times 2$ unitary transformation of the fermion operators
$$
\begin{align}
\bop_\eta &= u_\eta\aop_\eta + v_\eta \adop_{-\eta}\\
\bdop_\eta &= u_\eta^*\adop_\eta + v_\eta^* \aop_{-\eta}\nonumber\\
&|u_\eta|^2+|v_\eta|^2=1\nonumber
\end{align}
$$
Can be used to eliminate "anomalous" $\bop_\eta\bop_{-\eta}$ and $\bdop_{\eta}\bdop_{-\eta}$ terms from the Hamiltonian, diagonalizing the Hermitian matrix that appears in $\eqref{eq:bdg}$. This is the fermionic version of the Bogoliubov Hamiltonian we used for the Bose gas. Without working out the explicit form of the coefficients we can deduce the final form of the $\bdop_\eta$, $\bop_\eta$ Hamiltonian from the eigenvalues of the matrix

$$
\begin{align}
H= \sum_\eta E_\eta\left[\bdop_\eta\bop_\eta-\bop_\eta\bdop_\eta\right]\\
E_\eta =\sqrt{(t\cos(\eta)+\mu/2)^2+|\Delta|^2\sin^2(\eta)}
\end{align}
$$

With the values $\eqref{eq:ising-vals}$ for the Ising chain, the dispersion relation is
$$
E(\eta)=\pm\sqrt{J^2+g^2-2gJ\cos(\eta)}
$$
For $J\neq g$, there is a gap in the dispersion relation. For $J=g$ the gap closes. This is associated with a __quantum phase transition__ between the paramagnetic ground state at large $g$ and a ferromagnetic ground state at small $g$.



