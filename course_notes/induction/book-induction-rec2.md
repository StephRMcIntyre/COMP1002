##Simple Prop Wffs##

A recursive definition gives a set of objects which share that type.

Let the set of simple propositional wffs be recursively defined as follows:
<br> $~~~~$ 1) P, where P is __any__ proposition symbol, is a simple propositional wff.
<br> $~~~~$ 2) If α is a simple propositional wff, then so is (¬α).
<br> $~~~~$ 3) If α and β are both simple propositional wffs, then so is (α ∧ β).
<br> $~~~~$ 4) If α and β are both simple propositional wffs, then so is (α ∨ β).


```{.QualitativeProblem .MultipleSelection options="check" submission="none" content-format="html"}
SimplePropWffs1. Select all of the elements in the basis for simple propositional wffs.
| *R
| (P ∧ Q) ∨ S
| ((P ∧ Q) ∨ (¬S))
| (P)
| (¬(P ∧ Q))
| *P
```

```{.QualitativeProblem .MultipleSelection options="check" submission="none" content-format="html"}
SimplePropWffs2. Select all of the clauses which are part of the recursion step for simple propositional wffs.
| P, where P is __any__ proposition symbol, is a simple propositional wff.
| *If α is a simple propositional wff, then so is (¬α).
| *If α and β are both simple propositional wffs, then so is (α ∧ β).
| *If α and β are both simple propositional wffs, then so is (α ∨ β).
```

For example, (¬P) would be a simple propositional wff, but ¬P would not as it is missing the parentheses.

Derive ((P ∧ Q) ∨ (¬S)).
<br> $~~~~$ By the basis, P, Q and S are all simple propositional wffs.
<br> $~~~~$ Since P and Q are simple propositional wffs, then by 3) (P ∧ Q) is a simple propositional wff.
<br> $~~~~$ As S is a simple propositional wff, then by 2) so is (¬S).
<br> $~~~~$ Lastly, as both (P ∧ Q) and (¬S) are simple propositional wffs, then by 4) so is ((P ∧ Q) ∨ (¬S)).

```{.QualitativeProblem .MultipleSelection options="check" submission="none" content-format="html"}
SimplePropWffs3. Select all of the elements in the set of simple propositional wffs.
| *R
| (P ∧ Q) ∨ S
| *((P ∧ Q) ∨ (¬S))
| (P)
| *(¬(P ∧ Q))
| (P → P)
```
_Hint: It must be constructed exactly as given in the definition. Construct them on paper following the rules._


####Exercises

For each of the following, determine whether or not it is derivable given the simple popositional wff definition.
<br>If it is derivable, then give the derivation.
<br>Else, explain why it is not.

1. (¬((¬Q) ∨ (¬(¬S))))
2. (¬(¬P)
3. (¬P ∨ P)
4. (P ∧∨ Q)
5. ¬


<p>[Previous: Product Notation](https://carnap.io/shared/srenee651@gmail.com/book-induction-prod.pandoc) &emsp; &emsp; &emsp; &emsp; [-Main Page-](https://carnap.io/assignments/COMP%201002%20-%20Spring%202022/Workbook.pandoc#part-iii-induction)   &emsp; &emsp; &emsp; &emsp;  [Next: Recurrence Relations](https://carnap.io/shared/srenee651@gmail.com/book-induction-recrel.pandoc) </p>

