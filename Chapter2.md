# Notes
## Definitions
Closed interval - [1,4] = 1,2,3,4  
Open interval   - (1,4) = 2,3  
Half-open interval  - [1,4) = 1,2,3  
Increasing sequence - a[n] < a[n+1]  
Decreasing sequence - a[n] > a[n+1]  
Non-increasing  - a[n] >= a[n+1]  
Subsequence     - takes elements out of sequence while retaining order of terms
in original sequence  
"String over X" or "word over X"    - a finite sequence t[1...n] where each t[i]
exists in X.  
v   - logical OR  
^   - logical AND  
\-  - logical NOT (highest precedence)  
Literal - a variable (or a negation of a variable)  
Conjuctive normal form  - `c[1] ^ c[2] ^ c[3]` where each c[i] is of the form
 `p[1] v p[2] v p[3]`
->  - boolean implication
<-> - boolean eqivalence  
Loop invariant  - statement about program variables that is true just befolre a
loop begins executing, and also true after each iteration of the loop. Ideally
tells us that that the loop has produces expected results.
### Binomial Coefficients
nCk - in `n`, choose `k` - n >= k >= 0  - counts the number of k
elements subsets of an n-element set: (n!)/((n-k)!k!)

### Bounds
Upper bound - if `a` is an element in X, a set of real numbers, x is an upper
bound if all elements in X are less than or equal to `a`
Lower bound - like upper bound, but each element is more greater or equal to `a`  


#Mathematical Induction
*Examples done in exercise book*

### Loop invariant and mathematical induction  
Basis step proves that the invariant is true before the condition that controls
looping is tested for the first time. 

# Exercises
## 2.1
