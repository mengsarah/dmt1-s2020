---
title: English to Quantifiers
...

----------  -----------------------
   domain:  people
   $H(x)$:  $x$ is happy
   $C(x)$:  $x$ is in this class
 $A(x,y)$:  $x$ appreciates $y$
      $t$:  Luther Tychonievich
----------  -----------------------

Everyone is happy
:   $\forall x \;.\; H(x)$

Everyone in this class is happy
:   $\forall x \;.\; C(x) \rightarrow H(x)$

    Note that $\forall x \;.\; C(x) \land H(x)$ is wrong: it is only satisfied if every person is in the class and every person is happy.

Someone is happy
:   $\exists x \;.\; H(x)$

Someone in this class is happy
:   $\exists x \;.\; C(x) \land H(x)$

    Note that $\exists x \;.\; C(x) \rightarrow H(x)$ is wrong: it is satisfied if anyone is not in the class (happy or not), or anyone is happy (in the class or not).

Not everyone is happy
:   $\lnot \forall x \;.\; H(x)$
    
    See also the next sentence, which is equivalent to this.
    If done properly, any equivalent sentence in English translates into a logically equivalent predicate logic formula.

Someone is unhappy
:   $\exists x \;.\; \lnot H(x)$
    
    See also the previous sentence, which is equivalent to this.
    
    Sometimes it is important to distinguish between "unhappy" and "not happy", which can be different if there is a neither-happy-nor-unhappy state. We'll generally not deal with that nuance in this class.

Only one person is happy
:   This can be handled several ways:
    
    Someone is happy, and everyone other than them is unhappy
    :   $$\exists x \;.\; H(x) \land \forall y\;.\; \big((x \neq y) \rightarrow \lnot H(y)\big)$$
        
        We can commute quantifiers over expressions that do not involve their variable:
        
        $$\exists x \;.\; \forall y\;.\;  H(x) \land \big((x \neq y) \rightarrow \lnot H(y)\big)$$
        
        We cannot commute quantifiers over other quantifiers; for example $\forall y\;.\; \exists x \;.\; H(x) \land \big((x \neq y) \rightarrow \lnot H(y)\big)$ means "Pick anyone you want and I can find someone who is happy such that either my person is your person or your person is unhappy"; this is trivially true because I can always pick the same person you picked.
    
    If two people are both happy, they are the same person
    :   $\forall x, y \;.\; \big(H(x) \land H(y)\big) \rightarrow (x = y)$
        
        Note that we commonly combine quantifiers of the same kind, and can commute them; the above is equivalent to both of the following:
        
        $$\forall x \;.\; \forall y \;.\; \big(H(x) \land H(y)\big) \rightarrow (x = y)$$

        $$\forall y \;.\; \forall x \;.\; \big(H(x) \land H(y)\big) \rightarrow (x = y)$$
        
        Note this does not include the claim "at least one person is happy"; we could add that with
        
        $\Big(\exists z \;.\; H(z)\Big) \land \Big(\forall x, y \;.\; \big(H(x) \land H(y)\big) \rightarrow (x = y)\Big)$

    If two people are distinct, at least one is unhappy
    :   $\forall x, y \;.\; (x \neq y) \rightarrow \big(\lnot H(x) \lor \lnot H(y)\big)$
        
        Like the previous, this does not include "at lease one person is happy" but that can be added

Only one person in this class is happy
:   Also has several forms
    
    Someone in the class is happy, and everyone in the class other than them is unhappy
    :   $$\exists x \;.\; \big(C(x) \land H(x)\big) \land \Big(\forall y \;.\; \big(C(y) \land (x \neq y)\big) \rightarrow \lnot H(y)\Big)$$
        
        Again, we can commute the $\forall x$: $$\exists x \;.\; \forall y \;.\; \big(C(x) \land H(x)\big) \land \Big(\big(C(y) \land (x \neq y)\big) \rightarrow \lnot H(y)\Big)$$
    
    If two people are both in the class and both happy, they are the same person
    :   $$\forall x, y \;.\; \big(C(x) \land C(y) ^ H(x) \land H(y)\big) \rightarrow (x = y)$$
        
Everyone appreciates someone
:   For everyone, there is someone they appreciate
    
    $$\forall x \;.\; \exists y \;.\; A(x,y)$$
    
    Note again we cannot commute the different quantifiers across each other. $\exists y \;.\; \forall x \;.\; A(x,y)$ means "there is someone that everyone appreciates".


