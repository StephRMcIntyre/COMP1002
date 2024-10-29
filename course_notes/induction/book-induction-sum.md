<script type="text/javascript"
  src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.0/MathJax.js?config=TeX-AMS_CHTML">
</script>
<script type="text/x-mathjax-config">
  MathJax.Hub.Config({
    tex2jax: {
      inlineMath: [['$','$'], ['\\(','\\)']],
      processEscapes: true},
      jax: ["input/TeX","input/MathML","input/AsciiMath","output/CommonHTML"],
      extensions: ["tex2jax.js","mml2jax.js","asciimath2jax.js","MathMenu.js","MathZoom.js","AssistiveMML.js", "[Contrib]/a11y/accessibility-menu.js"],
      TeX: {
      extensions: ["AMSmath.js","AMSsymbols.js","noErrors.js","noUndefined.js"],
      equationNumbers: {
      autoNumber: "AMS"
      }
    }
  });
</script>

# Summation Notation
## The Basics

We can express a summation of a sequence of values by summation
notation. $$\sum_{i = a}^{b}f(i)$$<br>
$a$ is an integer representing the
lower bound (first value).<br>
$b$ is an integer representing the upper bound (last value).<br>
$i$ is a variable that represents the index -- it starts with $a$ and
ends with $b$<br>
$f(i)$ is a function that takes in $i$.<br>
This means that the result of the summation is
$f(a) + f(a+1) + f(a+2) + ... + f(b)$.<br>
For those that know Python, you can think of summations with this loop.

``` {.python language="Python" basicstyle="\\ttfamily"}
sumValue = 0
for i in range(a,b+1):
    sumValue += f(i)
```

## Examples

1.  Compute the value of $$\sum_{i = 1}^{5}i$$<br>
    Here $a$ is $1$, $b$ is $5$, and $f(i)$ is $i$.<br>
    $i$ starts at $1$ and ends when $i$ is $5$ (including this value!).<br>
    This means that the result of the summation is<br>
    $1 + 2 + 3 + 4 + 5=15$.

2.  Compute the value of $$\sum_{k = 3}^{6}4$$<br>
    Here $a$ is $3$, $b$ is $6$, and $f(i)$ is just $4$.<br>
    $k$, our index variable, starts at $1$ and ends when $k$ is $6$.<br>
    This means that the result of the summation is
    $4 + 4 + 4 + 4 = 16$.<br>
    *Note: $i$ is just a variable name, it does not need to be $i$.*

3.  Compute the value of $$\sum_{i = 2}^{4}2i^2+1$$<br>
    Here $a$ is $2$, $b$ is $4$, and $f(i)$ is $2i^2+1$.<br>
    $i$ starts at $2$ and ends when $i$ is $4$.<br>
    This means that the result of the summation is
    $(2*2^2+1) + (2*3^2+1) + (2*4^2+1)$.<br>
    Which simplifies to
    $(2*4+1) + (2*9+1) + (2*16+1) = 9 + 19 + 33 = 61$<br>
    *Note: only $i$ changes!*

4.  Compute the value of $$\sum_{i = 5}^{4}3i+2$$<br>
    Here $a$ is $5$, $b$ is $4$, and $f(i)$ is $3i+2$.<br>
    $i$ starts at $5$ and ends when $i$ is $4$.<br>
    $i$ starts already AFTER our last value.<br>
    This is an empty summation. The result of this is $0$.<br>
    Think of running a bill at the store, you start at the value <br>$0,
    and we add to this total. Here we did not add any items, so the
    final result is still 0.

5.  We can even nest the sums! Compute the value of
    $$\sum_{i = 2}^{4}\sum_{j = 1}^{5}3j+2$$<br>
    Okay, so our outer summation (or outer loop) goes from $2$ to
    $4$, and our inner summation (or inner loop) goes from $1$ to
    $5$.<br>
    We start with $i=2$. Now for this value of $i$, we compute
    $\sum_{j = 1}^{5}3j+2$<br>
    $(3*1+2) + (3*2+2) + (3*3+2) + (3*4+2) + (3*5+2)$<br>
    $~=(3+2) + (6+2) + (9+2) + (12 + 2) + (15+2)$<br>
    $~=55$<br>
    Now $i=3$, and again we compute $\sum_{j = 1}^{5}3j+2$<br>
    $~$Well, we already computed this, so when $i=3$, the value is
    $55$.<br>
    Now $i=4$, and again we compute $\sum_{j = 1}^{5}3j+2$<br>
    $~$Well, we already computed this, so when $i=4$, the value is
    $55$.<br>
    So the final result is $55 + 55 + 55 = 165$

6.  Compute the value of $$\sum_{i = 1}^{3}\sum_{j = i}^{4}j$$<br>
    Okay, so our outer summation (or outer loop) goes from $1$ to
    $3$, and our inner summation (or inner loop) goes from $i$ to
    $4$.<br>
    Notice how $j$'s value relies on $i$.<br>
    We start with $i=1$. Compute $\sum_{j = i}^{4}j$, and $j$ starts at
    $i$, which is $1$.<br>
    $~~1 + 2 + 3 + 4 = 10$<br>
    Now $i=2$. Compute $\sum_{j = i}^{4}j$, and $j$ starts at $i$, which
    is $2$.<br>
    $~~2 + 3 + 4 = 9$<br>
    Now $i=3$. Compute $\sum_{j = i}^{4}j$, and $j$ starts at $i$, which
    is $3$.<br>
    $~~3 + 4 = 7$<br>
    So the final result is $10 + 9 + 7 = 26$

### Practice Problems


1.	Compute the value of $\sum_{i = 1}^{5}100$

	~~~{.QualitativeProblem .Numerical submission="none" options="check"}
	1 500: Enter only the integer value.
	~~~

2.	Compute the value of $\sum_{i = 0}^{3}2i$

	~~~{.QualitativeProblem .Numerical submission="none" options="check"}
	2 12: Enter only the integer value.
	~~~

3.	Compute the value of $\sum_{i = 1}^{2}\sum_{j = i}^{4}i*j$

	~~~{.QualitativeProblem .Numerical submission="none" options="check"}
	3 84: Enter only the integer value.
	~~~

4.	Compute the value of $\sum_{i = 4}^{4}i$

	~~~{.QualitativeProblem .Numerical submission="none" options="check"}
	4 4: Enter only the integer value.
	~~~

5.	Compute the value of $\sum_{i = 3}^{2}\sum_{j = i}^{4}i*j$

	~~~{.QualitativeProblem .Numerical submission="none" options="check"}
	5 0: Enter only the integer value.
	~~~

6.	Compute the value of $\sum_{i = 1}^{2}\sum_{j = i}^{4}i*j$

	~~~{.QualitativeProblem .Numerical submission="none" options="check"}
	6 84: Enter only the integer value.
	~~~


## Recursive Definitions and Properties


Recursive definition of summation is,<br>
<br>
$\sum_{i=a}^{b} f(i) = 0$, when $a > b$
<br><br>
$\sum_{i=a}^{b} f(i) = f(i)$, when $a = b$
<br><br>
$\sum_{i=a}^{b} f(i) = (\sum_{i=a}^{b-1} f(i)) + (\sum_{i=b}^{b} f(i))$
<br><br>

```{.QualitativeProblem .MultipleSelection options="check" submission="none" content-format="html"}
RecSum. Select the base case(s) for recursive definition above.
| *First part.
| *Second part.
| Third part.
```


Useful property:

$\sum_{i=a}^{b}f(i) + \sum_{i=a}^{b}g(i) = \sum_{i=a}^{b}f(i)+g(i)$<br>
    Note that the lower and upper bounds must be the same.


## Induction with Summations

1.  Prove $\sum_{i=1}^{n} i = \frac{n(n+1)}{2}$ for all integers $n>0$.
    
    Proof: By induction on $n$.
    
    Base case: $n=1$.<br>
    Then $LHS = \sum_{i=1}^{1} i = i$ by base case of the recursive<br>
    definition of summations as the lower and upper bounds are equal.<br>
    And $RHS = \frac{1(1+1)}{2} = \frac{2}{2} = 1$.<br>
    Since $LHS = RHS$, as desired, the base case has been proved.
    
    Inductive Hypothesis: Suppose $\sum_{i=1}^{k} i = \frac{k(k+1)}{2}$
    for some integer $k>0$.
    WTS: $\sum_{i=1}^{k+1} i = \frac{(k+1)(k+1+1)}{2}$
    
    Inductive Argument: Starting with the LHS of WTS

    $\sum_{i=1}^{k+1} i$<br>
    $= (\sum_{i=1}^{k}i) + (\sum_{i=k+1}^{k+1} i)$ &nbsp;&nbsp;by recursive
    definition of sum<br>
    $= (\sum_{i=1}^{k}i) + (k+1)$ &nbsp;&nbsp;by base case in recursive
    definition of sum<br>
    $= \frac{k(k+1)}{2}+(k+1)$ &nbsp;&nbsp;by inductive hypothesis<br>
    $= (k+1)(\frac{k}{2} + 1)$ &nbsp;&nbsp;factoring $k+1$ from both
    parts<br>
    $= (k+1)(\frac{k+2}{2})$&nbsp;&nbsp; by turning $1$ into
    $\frac{2}{2}$<br>
    $= \frac{(k+1)(k+2)}{2}$ &nbsp;&nbsp;by associativity of
    multiplication<br>
    $= \frac{(k+1)(k+1+1)}{2}$ &nbsp;&nbsp;as $2 = 1 + 1$

    Which is the RHS. So LHS = RHS for the WTS, as desired.
    Thus the property holds for k+1, completing the argument.
    
    Conclusion: By the principle of mathematical induction,
    $\sum_{i=1}^{n} i = \frac{n(n+1)}{2}$ for all integers $n>0$.

2. Prove $\sum_{i=1}^{n}f(i) + \sum_{i=1}^{n}g(i) = \sum_{i=1}^{n}f(i)+g(i)$ for all positive integers $n$.
    
    Proof: By induction on $n$.
    
    Base case: $n=?$<br>

	~~~{.QualitativeProblem .Numerical submission="none" options="check"}
	2.a 1: Enter the value of n for the base case.
	~~~

    Now, complete the proof for the base case. <br>
    Show that $\sum_{i=1}^{n}f(i) + \sum_{i=1}^{n}g(i) = \sum_{i=1}^{n}f(i)+g(i)$ when $n$ is the value of the base case.<br>
    $LHS = $<br>
    $RHS = $
    
    Inductive Hypothesis: Suppose $\sum_{i=1}^{k}f(i) + \sum_{i=1}^{k}g(i) = \sum_{i=1}^{k}f(i)+g(i)$ for ....

	```{.QualitativeProblem .MultipleChoice options="check" submission="none" content-format="html"}
	2.b what do we need to suppose about k for this predicate?
	| an arbitrary integer k.
	| *an arbitrary positive integer k.
	| all integers k.
	| all positive integers k.
	```
    WTS: $\sum_{i=1}^{k+1}f(i) + \sum_{i=1}^{k+1}g(i) = \sum_{i=1}^{k+1}f(i)+g(i)$    

    Inductive Argument: <br>
    Start with either the LHS or RHS of the WTS. <br>
    Now, refer back to the recursive definition of summation!  

    <details>
    <summary>Inductive Argument Solution</summary>

    $LHS = \sum_{i=1}^{k+1}f(i) + \sum_{i=1}^{k+1}g(i)$<br>
    $= (\sum_{i=1}^{k}f(i)) + (\sum_{i=k+1}^{k+1}f(i)) + (\sum_{i=1}^{k}g(i)) + (\sum_{i=k+1}^{k+1}g(i))$ &nbsp;&nbsp;by recursive definition of summation<br>
    $= (\sum_{i=1}^{k}f(i)) + (\sum_{i=1}^{k}g(i)) + (\sum_{i=k+1}^{k+1}f(i)) +  (\sum_{i=k+1}^{k+1}g(i))$ &nbsp;&nbsp;by associativity of addition<br>
    $= (\sum_{i=1}^{k}f(i) + g(i)) + (\sum_{i=k+1}^{k+1}f(i)) +  (\sum_{i=k+1}^{k+1}g(i))$ &nbsp;&nbsp;by inductive hypothesis<br>
    $= (\sum_{i=1}^{k}f(i) + g(i)) + f(i) +  g(i)$ &nbsp;&nbsp;by base case of summation<br>
    $= (\sum_{i=1}^{k}f(i) + g(i)) + (\sum_{i=k+1}^{k+1}f(i) +  g(i))$ &nbsp;&nbsp;by base case of summation (but other direction of = )<br>
    $= (\sum_{i=1}^{k+1}f(i) + g(i)) $ &nbsp;&nbsp;by recursive definition of summation<br>
    </details>

    Conclusion: left for the reader.
  


## Exercises

1.  Consider the expression: $$\sum_{k=1}^{n+1}2^{k-1}$$

    a.  Let n = 4. Evaluate the expression without using a calculator.

    b.  Consider a change of variable k to j, where j = k -- 1.<br>
        Calculate the lower and upper limits of the new summation.<br>
        Transform the summation by making the specified change of
        variable.<br>
        *Hint: use high school algebra and think what $2^{k-1}$ should
        be if we used j instead of k.*

    c.  Let n = 4. Evaluate the new expression from part b.<br>
        Is the result the same as the result from part a?<br>
        *Hint: It should be the same. Use this to check your work.*

2.  Prove by induction that $2*\sum_{k=1}^{n} k = n(n+1)$ for all integers $n>0$. 

3.  Prove by induction that $\sum_{i=0}{n} 4 = 4n$ for all non-negative integers.

4. Prove by induction that $\sum_{i=1}{n} n = n^2$ for all integers $n>0$. 