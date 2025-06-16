## How to find a DP algorithm
1. Describe $f(x)$ in words
2. Find base cases and recursions and form this,

$$
f(x) =
\begin{cases}
\text{base case}\quad x=\text{some special numbers} \\
\text{something contains $f(m)$ where }m<x
\end{cases}
$$

3. Memorization: Add a lookup table to recursive code so that future calls to $f$ with the same arguments can return immediately
So the final product is like,

$$
f(x) =
\begin{cases}
\text{base case}\quad &x=\text{some special numbers} \\
Memo[x]\text{ in the memo}\quad &\text{if it is computed before}\\
\text{something contains $f(m)$ where }m<x &\text{compute through recurtion}
\end{cases}
$$

## Shortest Path Example

We'll apply this principle to the shortest path problem

1.  $f(t)$ by word

$$
	f(t) = \text{the shortest path from s to t}
$$

2. $f(t)$ with base case and recursion

$$
f(t)=
\begin{cases}
0,\quad &if\; t=s \\
\infty,\quad&if\,indegree(t)=0 \\
\min_{e=(a,t)} 
\{weight(a,t)+f(a)\},
&otherwise
\end{cases}
$$

3. Memorization: if $f(t)$ is called, save it to $Memo[t]$

$$
f(t)=
\begin{cases}
0,\quad &if\; t=s \\
\infty,\quad&if\,indegree(t)=0 \\
Memo[t], &if\,in\,memo \\
\min_{e=(a,t)} 
\{weight(a,t)+f(a)\},
&otherwise
\end{cases}
$$

This is a Top-Bottom algorithm and  we **cannot** deal with negative edges. If we do this bottom-up we'll get Bellman-Ford algorithm which can deal with negative edges.

### How to bottom-up?
The essence of bottom-up lies in the way of memorization. In the top-down algo, we memorize in recursions. However, in bottom-up algo, we memorize first. In other words, the depth of recursion stack is at most 1.

It's simple to get a bottom-up version. To **bottom**-up, we should start from s instead of t. For every edges going out from s (or $e\in \mathbb{E}$ if there's negative edges), we apply $f(t)$ to them.

### Detect Negative Cycles
If negative cycles is reachable from $s$, we use Bellman-Ford.

If not (which means it's not a DAG), we create a virtual sink $s_v$ and $\forall v\in \mathbb{V}$, we form an edge $(s_{k},v)$ with weight of 0. We turn it into a DAG without creating new possible negative cycles.

## Weighted Interval Scheduling

![[Pasted image 20250617001849.png]]

- Job $j_{1},j_{2},\dots j_{n}$ where $finish(j_{1})\leq finishj_{2}\leq\dots\leq finish(j_{n})$

- $p(j_i)=j_{k}$ if $j_k$ 
	- is the largest index of job which is incompatible with $j_i$
	- $<j_{i}$
1. Word def

$$
\begin{align}
	f(x)=&\text{the maximum total weight of a set of mutually compatible jobs that can be selected from the first j jobs}\\
	&\text{i.e., from the subset of jobs \{1, 2, ..., j\}}
\end{align}
$$

2. Recursion def

$$
f(j)=
\begin{cases}
0,\quad &if\;j=0 \\
\max(f(j-1), f(p(j)))&otherwise
\end{cases}
$$

3. Memorization

$$
f(j)=
\begin{cases}
0,\quad &if\;j=0 \\
Memo[j]&if\;in\;memo \\
\max(f(j-1), f(p(j)))&otherwise
\end{cases}
$$

4. Bottom up: compute $Memo[1],Memo[2],\dots,Memo[n]$ one after another by transforming the formula in 3.

## Knapsack Problem

$$
OPT(i,w)=
\begin{cases}
0,\quad & i=0 \\
OPT(i-1,w) & w_{i}>w \\
\max\{OPT(i-1,w), OPT(i-1,w-w_{i})\}&otherwise
\end{cases}
$$