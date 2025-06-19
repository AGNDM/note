## Interactability
We define binary relation  $R \subseteq \{0,1\}^* \times \{0,1\}^*$ and two functions decide(R) and search(R).

$$
	R:x\to \omega
$$

$$
	decide(R,x):=\text{decide if }\exists\text{ witness }\omega\text{ s.t. }(x,\omega)\in R
$$

$$
	search(R,x):=\text{find a witness }\omega\text{ s.t. }(x,\omega)\in R
$$

The diffrence is that output of decide func is yes/no while output of search func is $\omega$

We are going to focus on decide func

$x$ here is an instance, a given background, i.e. the graph $(G,s,t)$ in a Max Flow problem.
$\omega$ is a witness/certificate or typically speaking, a general unknown part, i.e. the $(s,t)$ flow.
$R$ represents how we define a problem, i.e. $(x,\omega)\in R$ iff $\omega$ is a Max Flow.
Decide func can return whether there exists a Max Flow. 

Verifier $V(x,\omega)$ tells us whether $(x,\omega)\in R$
From which we can find out that decide func can be solved by simply verifying every possible $\omega$ in exponential time.

$x$ here is an instance, i.e. the graph $(G,s,t)$ in a Max Flow problem, $\omega$ is a witness/certificate, i.e. the $(s,t)$ flow. $(x,\omega)\in R$ iff $\omega$ is a Max Flow. Decide func can return whether there exists a Max Flow. 

If there is a poly-time algorithm for verifier $V$, we say it's a **NP problem**.

Furthermore, if a poly-time algorithm for decide function also exists, it's a **P problem**.

## NP-complete and NP-hard
Simply understanding, a problem $A$ is NP-hard if $A$ is not easier than any other NP problems. $A$ is NP-complete if $A$ is in NP and is NP-hard.

## Typical NP Problems
### Independent Set
### Vertex Cover
### Set Cover
$$
	S_{i}\subseteq U
$$

Is there a collection of $\leq k$ of there sets $S_i$ such that their union is $U$?

### SAT
Given a CNF formula $\Phi$, is there a satisfying assignment?

### 3SAT
Given a 3-CNF formula $\Phi$, is there a satisfying assignment?

### Hamiltonian Cycle
Does there exixst a simple cycle $C$ in an undirected graph $G=(V,E)$?

### Dierected Hamiltonian Cycle
Does there exixst a simple cycle $C$ in a directed graph $G=(V,E)$?

Use magical way to reduce it from SAT

### TSP
Travel to all vertices within distance of $d$

### 3D Matching

$$
\begin{aligned}
	T\subseteq X\times Y\times Z\\
	\exists\;elements \in X \cup Y\cup Z \text{ in T}
\end{aligned}
$$

## NP-completeness
SAT is the **source** of all NP-complete problems (maybe?).
