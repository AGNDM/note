![[approx_lec.pdf]]

- **Scheme** and **Algorithm**

	- $n$ is the scale of input
	
	- the cost $C$ we mentioned in the note in fact is more  similar to the meaning of **value** in **maximization problems**
	
	- So when considering maximization, we want the value $C$ to be as much as possible. In other words, we should minimize $\frac {C_{opt}} C$.
	
	- Conversely, in minimization problems, we focus on $\frac{C}{C_{opt}}$.
	
	- Furthermore, we can play around $\omega(n)$ using $\epsilon$. This becomes a **scheme** because the $\epsilon$ is an arbitrary number.
	
- **PTAS** vs **FPTAS**(poly in both n and $\frac{1}{\epsilon}$)

- Vertex Cover
	- Greedy: choose the one with the ==possible maximum== degree(good in practice bad in theory)
	
	- Random: Simply taking random edges(u, v) and pick vertices u & v
	
		- 2-approx algo:
		
			- $A$ = edges that are picked
			
			- $C$ = $2|A|$ vertices are picked (that's where '2' comes from)
			
			- No two edges in $A$ share the same point and we have to cover every edges (at least half of the vertices) in $A$ so  $C_{opt} >= |A|$ 
			
			-  So $C <= 2C_{opt}$ 
			
- Set Cover
	-  **Def** Set $X$ and subsets $S_i$ , Minimizing # of subsets while covering the set $X$ 
	- Greedy: Always select the **largest** subset
		- a $(\ln{(n)} + 1)$-approx algo (whats the bound?)
		
		- Assume $|C_{opt}| \; = \; t$  $X_k\;=\;elements \;in\; iteration\; k$ . So for any $k$ we can cover it using $t$ sets. 
		
			- One of them at least cover $\frac{|X_k|}{t}$ elements
			
			- So the one we pick should be greater than $\frac{|X_k|}{t}$
			
			- So we have $$\forall k,\quad |X_{k+1}| \le (1-\frac{1}{t})|X_k|$$
			
			- When $X_k\; = \; 0$ we're done
			
			- So inductively we have,
		    $$
        \forall k,\quad |X_k|\le(1-\frac{1}{t})^kn \le\,\ldots some\; math\ldots\le e^{-\frac{k}{n}}n 
            $$

- Partition
	-  Partition $A$ and $B$
	- Goal: maintain the balance as much as possible
	
	$$
	2L=sum\;of\;all\;the\;weights
    $$
	
	- optimal solution$\ge L$
	
	- Do a brute-force in the range of $m$ 
	
	- Do the rest in an easier way
	
	- In this case the cost $C$ should be $\omega(A)$ (or $\omega(B)$) and the $C_{opt}$ is L. Thus, the ratio $\rho(n)$ is the upper bound on $\frac{\omega(A)}{L}$.
	
 