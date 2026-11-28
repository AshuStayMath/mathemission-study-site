---
type: "weekly-note"
series: "Note of the Week"
week: 4
published: 2026-11-30
from: "The Mathematical Lab · Part 6 · Differential Calculus"
chapter:
  - "[[1112A-Limits]]"
tags:
  - "ch/limits"
  - "jee/advanced"
  - "idea/approximation"
---

# Limits by Polynomial Approximation

**The lemma.** If near $x = 0$ a function looks like $f(x) = x + a x^3 + O(x^5)$, then applying it $n$ times gives

$$f_n(x) = \underbrace{f(f(\cdots f}_{n}(x)\cdots)) = x + n\,a\,x^3 + O(x^5)$$

Each layer simply adds one more $a x^3$.

**Key idea:** in a limit where the $x$ terms cancel, only the coefficient of $x^3$ matters. Read it off the [[Maclaurin Series]] of the base function and multiply by the number of layers in the [[Composition of Functions]].

## The archetype in three steps
Find $\displaystyle\lim_{x \to 0} \frac{\tan(\tan(\tan x)) - \sin(\sin(\sin x))}{\tan x - \sin x}$.

**1. Prove the lemma.** Put $f(x) = x + a x^3$ into itself:
$$f(f(x)) = (x + a x^3) + a(x + a x^3)^3 = x + 2a x^3 + O(x^5).$$
The cube of $x + ax^3$ only adds $x^3$ once more; everything else is $x^5$ or higher. Repeat, and each layer adds another $a x^3$.

**2. Read off the coefficients.** $\tan x = x + \frac13 x^3 + \dots$ and $\sin x = x - \frac16 x^3 + \dots$ With 3 layers:
$$\tan(\tan(\tan x)) = x + x^3 + \dots, \qquad \sin(\sin(\sin x)) = x - \tfrac12 x^3 + \dots$$

**3. Divide the $x^3$ terms.** Numerator: $x^3 + \frac12 x^3 = \frac32 x^3$. Denominator: $\frac13 x^3 + \frac16 x^3 = \frac12 x^3$. So the limit is $\dfrac{3/2}{1/2} = 3$. $\blacksquare$

## Check it with numbers
- At $x = 0.1$ the fraction is about $3.015$; at $x = 0.01$ it is about $3.00015$. It is closing in on $3$.
- $\sin(\sin x) = x - \frac13 x^3 + \dots$, exactly $2 \times \left(-\frac16\right)$ as the lemma says.
- With 10 layers of $\tan$ and 10 of $\sin$, the limit is $\dfrac{10\left(\frac13 + \frac16\right)}{\frac13 + \frac16} = 10$. In general, $n$ layers give $n$.

<!-- teach -->
## In class
- **Where it appears:** limits of nested $\sin$, $\tan$, $\sin^{-1}$, $\tan^{-1}$, where L'Hôpital's rule would need three or more rounds of messy derivatives.
- **The trap:** the lemma needs the series to start with exactly $x$ and to have **no $x^2$ term**. For $f(x) = e^x - 1 = x + \frac12 x^2 + \frac16 x^3 + \dots$ the lemma would predict $\frac13 x^3$ for $f(f(x))$, but the true coefficient is $\frac56$, because the $x^2$ term feeds into $x^3$. Odd functions like $\sin$ and $\tan$ are always safe.
- **Try:** $\displaystyle\lim_{x \to 0} \frac{\tan(\tan x) - \sin(\sin x)}{x^3}$. *(Answer: $2 \cdot \frac13 - 2 \cdot \left(-\frac16\right) = \frac23 + \frac13 = 1$.)*

---

## Your turn: link it into your brain
This note is **your copy**. Change anything. The original stays in AK's Lab.
1. **Read** it once with a pen in hand.
2. **Link:** tap [[Maclaurin Series]] and [[Composition of Functions]]. If that note is not in your notebook yet, the tap opens a new blank note with that title. In each, write 3 lines in your own words: what the idea says and where you would use it.
3. **Connect:** add one link to a note of yours where a limit needed a series expansion (a question, a lecture, a trick).
4. **Modify:** add your own example or classroom story below.
<!-- /teach -->
<!-- study -->
## In the exam
- **Where it appears in JEE:** limits at $0$ of nested $\sin$, $\tan$, $\sin^{-1}$, $\tan^{-1}$, usually divided by $x^3$ or by a simpler difference such as $\tan x - \sin x$. Three rounds of L'Hôpital's rule would take minutes; the lemma takes one line.
- **The usual slip:** using the lemma on a function whose series has an $x^2$ term, such as $e^x - 1$ or $\ln(1+x)$. There the $x^2$ term feeds into $x^3$ and the shortcut gives a wrong answer. Odd functions ($\sin$, $\tan$, $\sin^{-1}$, $\tan^{-1}$) are always safe.
- **Try:** $\displaystyle\lim_{x \to 0} \frac{\sin(\sin x) - \tan^{-1}(\tan^{-1} x)}{x^3}$. *(Answer: $\tan^{-1} x = x - \frac13 x^3 + \dots$, so two layers give $x - \frac23 x^3$, while $\sin(\sin x) = x - \frac13 x^3$. The limit is $-\frac13 + \frac23 = \frac13$.)*

---

## Your turn: link it into your notes
This note is **your copy** in My Notes. Change anything. The original stays with AK.
1. **Read** it once with a pen in hand.
2. **Link:** tap [[Maclaurin Series]] and [[Composition of Functions]]. If that note is not in your notebook yet, the tap opens a new blank note with that title. In each, write 3 lines in your own words: what the idea says and where you would use it.
3. **Connect:** add one link to a note of yours where a limit needed a series expansion (a PYQ you solved, a chapter note, a question from your Mistake Book).
4. **Try it:** solve the Try question above before you read its answer, and write your working below.
<!-- /study -->

### My notes
-

---
*Note of the Week · from The Mathematical Lab · AK · Stay Mathactive · mathemission.in*
