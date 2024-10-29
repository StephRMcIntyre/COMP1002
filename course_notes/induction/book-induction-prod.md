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

# Product Notation
## The Basics

We can express a product of a sequence of values by product notation.
<br>This is very similar to product notation, except we are dealing with
multiplication instead of addition. <br>$$\prod_{i = a}^{b}f(i)$$<br> $a$ is an
integer representing the lower bound (first value).<br>
$b$ is an integer representing the upper bound (last value).<br>
$i$ is a variable that represents the index -- it starts with $a$ and
ends with $b$<br>
$f(i)$ is a function that takes in $i$.<br>
This means that the result of the product is<br>
$f(a) * f(a+1) * f(a+2) * ... * f(b)$.

For those that know Python, you can think of products with this loop.

``` {.python language="Python" basicstyle="\\ttfamily"}
prodValue = 1
for i in range(a,b+1):
    prodValue *= f(i)
```

## Examples

1.  Compute the value of $$\prod_{i = 1}^{5}i$$<br>
    Here $a$ is $1$, $b$ is $5$, and $f(i)$ is $i$.<br>
    $i$ starts at $1$ and ends when $i$ is $5$ (including this value!).<br>
    This means that the result of the product is
    $1 * 2 * 3 * 4 * 5=120$.

2.  Compute the value of $$\prod_{k = 3}^{6}4$$<br>
    Here $a$ is $3$, $b$ is $6$, and $f(i)$ is just $4$.<br>
    $k$, our index variable, starts at $1$ and ends when $k$ is $6$.<br>
    This means that the result of the product is $4 * 4 * 4 * 4 = 256$.

3.  Compute the value of $$\prod_{i = 2}^{4}2i^2+1$$<br>
    Here $a$ is $2$, $b$ is $4$, and $f(i)$ is $2i^2+1$.<br>
    $i$ starts at $2$ and ends when $i$ is $4$.<br>
    This means that the result of the product is
    $(2*2^2+1) * (2*3^2+1) * (2*4^2+1)$.<br>
    Which simplifies to
    $(2*4+1) * (2*9+1) * (2*16+1) = 9 * 19 * 33 = 5643$

4.  Compute the value of $$\prod_{i = 5}^{4}3i+2$$<br>
    Here $a$ is $5$, $b$ is $4$, and $f(i)$ is $3i+2$.<br>
    $i$ starts at $5$ and ends when $i$ is $4$.<br>
    $i$ starts already AFTER our last value.<br>
    This is an empty product.<br>
    The empty product is different from the empty sum. If it were 0,
    then our results would always be 0.<br>
    The empty product is 1.

5.  We can even nest the products! Compute the value of
    $$\prod_{i = 2}^{4}\sum_{j = 1}^{5}3j+2$$<br>
    Okay, so our outer product (or outer loop) goes from $2$ to $4$,
    and our inner sum (or inner loop) goes from $1$ to $5$.<br>
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
    So the final result is $55 * 55 * 55 = 166375$

6.  Compute the value of $$\prod_{i = 1}^{6}\frac{i}{i+1}$$<br>
    Okay, $i$ goes from $1$ to $6$.
    $$\prod_{i = 1}^{6}\frac{i}{i+1} = \frac{1}{1+1} * \frac{2}{2+1} * \frac{3}{3+1} * \frac{4}{4+1} + \frac{5}{5+1} * \frac{6}{6+1}$$
    On a test, you will not have access to a calculator! Need to be
    clever.<br>
    Let's simplify and see if we can notice something...<br>
    $$\prod_{i = 1}^{6}\frac{i}{i+1} = \frac{1}{2} * \frac{2}{3} * \frac{3}{4} * \frac{4}{5} + \frac{5}{6} * \frac{6}{7}$$<br>
    Maybe you noticed it...<br> we can cancel out some of the terms!<br>
    $$\prod_{i = 1}^{6}\frac{i}{i+1} = \frac{1}{\cancel{2}} * \frac{\cancel{2}}{3} * \frac{3}{4} * \frac{4}{5} + \frac{5}{6} * \frac{6}{7}$$<br>
    We can keep doing this as there are other terms we can cancel out!<br>
    $$\prod_{i = 1}^{6}\frac{i}{i+1} = \frac{1}{\cancel{2}} * \frac{\cancel{2}}{\cancel{3}} * \frac{\cancel{3}}{\cancel{4}} * \frac{\cancel{4}}{\cancel{5}} + \frac{\cancel{5}}{\cancel{6}} * \frac{\cancel{6}}{7} = \frac{1}{7}$$<br>
    These are often called telescoping sums/products. All the middle
    parts collapse down, leaving only the start and end - like a
    telescope!

### Practice Problems


1.	Compute the value of $\prod_{i = 1}^{5}2$

	~~~{.QualitativeProblem .Numerical submission="none" options="check"}
	1 128: Enter only the integer value.
	~~~

2.	Compute the value of $\prod_{i = 0}^{3}2i$

	~~~{.QualitativeProblem .Numerical submission="none" options="check"}
	2 0: Enter only the integer value.
	~~~

3.	Compute the value of $\prod_{i = 1}^{2}\sum_{j = i}^{3}j$

	~~~{.QualitativeProblem .Numerical submission="none" options="check"}
	3 30: Enter only the integer value.
	~~~

4.	Compute the value of $\prod_{i = 4}^{4}i$

	~~~{.QualitativeProblem .Numerical submission="none" options="check"}
	4 4: Enter only the integer value.
	~~~

5.	Compute the value of $\prod_{i = 3}^{2}\prod_{j = i}^{4}i*j$

	~~~{.QualitativeProblem .Numerical submission="none" options="check"}
	5 1: Enter only the integer value.
	~~~

6.	Compute the value of $\prod_{i = 3}^{7}\frac{i+2}{i}$

	~~~{.QualitativeProblem .Numerical submission="none" options="check"}
	6 6: Enter only the integer value.
	~~~


## Recursive Definitions and Properties


Recursive definition of summation is,<br>
<br>$\prod_{i=a}^{b} f(i) = 0$, when $a > b$<br><br>
$\prod_{i=a}^{b} f(i) = f(i)$, when  $a = b$<br><br>
$\prod_{i=a}^{b} f(i) = (\prod_{i=a}^{b-1} f(i)) * (\prod_{i=b}^{b} f(i))$



```{.QualitativeProblem .MultipleSelection options="check" submission="none" content-format="html"}
RecSum. Select the base case(s) for recursive definition above.
| *First part.
| *Second part.
| Third part.
```


Useful properties:

1) $\prod_{i=a}^{b}f(i) * \prod_{i=a}^{b}g(i)  = \prod_{i=a}^{b}f(i)*g(i)$<br>
    Note that the lower and upper bounds must be the same.

2) $\prod_{i=a}^{b}f(i) * \prod_{j=c}^{d}g(j) = \prod_{i=a}^{b}\prod_{j=c}^{d}f(i)*g(j)$


## Induction with Products

1.  Prove: $\prod_{i=2}^{n} \frac{i+1}{i-1}=\frac{n(n+1)}{2}$ for all
    integers $n\geq 2$.
    
    Proof: By induction on $n$.
    
    Base case: $n=2$:<br>
    $LHS=\prod_{i=2}^{2}$<br>
    $=\frac{2+1}{2-1}$ by base case for recursive definition of product<br>
    $=\frac{3}{1}=3$,<br>
    $RHS=\frac{2(2+1)}{2}=3$.<br>
    $LHS=RHS$ as desired.<br>
    
    Inductive Hypothesis: <br>Suppose
    $\prod_{i=2}^{k} \frac{i+1}{i-1}=\frac{k(k+1)}{2}$ some arbitrary
    but particular integer $k\geq 2$.<br>
    WTS: $\prod_{i=2}^{k+1} \frac{i+1}{i-1}=\frac{(k+1)(k+1+1)}{2}$

    Inductive Argument: Starting with the LHS of the WTS<br>
    $LHS = \prod_{i=2}^{k+1} \frac{i+1}{i-1}$<br>
    $=(\prod_{i=2}^{k} \frac{i+1}{i-1})*(\prod_{i=k+1}^{k+1} \frac{i+1}{i-1})$
    , &nbsp;&nbsp;by product recursive definition<br>
    $=(\prod_{i=2}^{k}\frac{i+1}{i-1})*\frac{k+1+1}{k+1-1})$, &nbsp;&nbsp;by base
    case in product recursive definition<br>
    $=(\prod_{i=2}^{k}\frac{i+1}{i-1})*\frac{k+1+1}{k}$, &nbsp;&nbsp;by algebra<br>
    $=\frac{k(k+1)}{2}*\frac{k+1+1}{k}$, &nbsp;&nbsp;by inductive hypothesis<br>
    $=\frac{k(k+1)(k+1+1)}{2k}$, &nbsp;&nbsp;by algebra<br>
    $=\frac{(k+1)(k+1+1)}{2}$, &nbsp;&nbsp;by algebra<br>
    
    Conclusion: By the principle of mathematical induction,<br>
    $\prod_{i=2}^{n} \frac{i+1}{i-1}=\frac{n(n+1)}{2}$ for all integers
    $n\geq 2$.


2. Prove $\prod_{i=a}^{b}f(i) * \prod_{i=a}^{b}g(i)  = \prod_{i=a}^{b}f(i)*g(i)$ for all positive integers $n$.
    
    Proof: By induction on $n$.
    
    Base case: $n=?$<br>

	~~~{.QualitativeProblem .Numerical submission="none" options="check"}
	2.a 1: Enter the value of n for the base case.
	~~~

    Now, complete the proof for the base case. <br>
    Show that $\prod_{i=a}^{b}f(i) * \prod_{i=a}^{b}g(i)  = \prod_{i=a}^{b}f(i)*g(i)$ when $n$ is the value of the base case.<br>
    $LHS = $<br>
    $RHS = $
    
    Inductive Hypothesis: Suppose $\prod_{i=1}^{k}f(i) * \prod_{i=1}^{k}g(i) = \prod_{i=1}^{k}f(i)*g(i)$ for ....

	```{.QualitativeProblem .MultipleChoice options="check" submission="none" content-format="html"}
	2.b what do we need to suppose about k for this predicate?
	| an arbitrary integer k.
	| *an arbitrary positive integer k.
	| all integers k.
	| all positive integers k.
	```
    WTS: $\prod_{i=1}^{k+1}f(i) * \prod_{i=1}^{k+1}g(i) = \prod_{i=1}^{k+1}f(i)*g(i)$    

    Inductive Argument: <br>
    Start with either the LHS or RHS of the WTS. <br>
    Now, refer back to the recursive definition of summation!  

    <details>
    <summary>Inductive Argument Solution</summary>

    $LHS = \prod_{i=1}^{k+1}f(i) * \prod_{i=1}^{k+1}g(i)$<br>
    $= (\prod_{i=1}^{k}f(i)) * (\prod_{i=k+1}^{k+1}f(i)) * (\prod_{i=1}^{k}g(i)) * (\prod_{i=k+1}^{k+1}g(i))$ &nbsp;&nbsp;by recursive definition of product<br>
    $= (\prod_{i=1}^{k}f(i)) * (\prod_{i=1}^{k}g(i)) * (\prod_{i=k+1}^{k+1}f(i)) *  (\prod_{i=k+1}^{k+1}g(i))$ &nbsp;&nbsp;by associativity of addition<br>
    $= (\prod_{i=1}^{k}f(i) * g(i)) * (\prod_{i=k+1}^{k+1}f(i)) *  (\prod_{i=k+1}^{k+1}g(i))$ &nbsp;&nbsp;by inductive hypothesis<br>
    $= (\prod_{i=1}^{k}f(i) * g(i)) * f(i) *  g(i)$ &nbsp;&nbsp;by base case of product<br>
    $= (\prod_{i=1}^{k}f(i) * g(i)) * (\prod_{i=k+1}^{k+1}f(i) *  g(i))$ &nbsp;&nbsp;by base case of product (but other direction of = )<br>
    $= (\prod_{i=1}^{k+1}f(i) * g(i)) $ &nbsp;&nbsp;by recursive definition of product<br>
    </details>

    Conclusion: left for the reader.
  


## Exercises

1.  Consider the expression:
    $$\prod_{k=1}{n}\frac{k+1}{k} \prod_{k=1}{n}\frac{k+2}{k+1}$$

    a.  Write the expression as a single product.<br>
        You may simplify, but do not assign n a specific value.<br>
        *Hint: use the properties.*

    b.  Compute the expression where n = 5 without using a calculator.

    c.  Compute the expression where n = 7 without using a calculator.

    d.  Find the Closed Form of the Product of the expression given.<br>
        This means find an expression without summations, products, or
        recursion that is equal to the product given.<br>
        *Hint: The work you did from parts a and b should help with
        this.*

    e.  Prove by Induction that your answer for part d is equal to the
        given expression.

2.  Prove by induction that $2*\sum_{k=1}^{n} k = n!$ for all integers $n>0$. 

3.  Prove by induction that $\sum_{i=1}{n} 4 = 4^n$ for all non-negative integers.

4. Prove by induction that $\sum_{i=1}{n} n = n^n$ for all integers $n>0$. 