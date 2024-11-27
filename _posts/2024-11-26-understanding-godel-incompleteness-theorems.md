---
title: Understanding Gödel incompleteness theorems
description: Why mathematics are not broken.
date: 2024-10-07 09:00:00 +0200
categories: [Logic]
tags: [Gödel incompleteness, boolean logic, mathematical reasoning]
math: true
mermaid: true
---
## What are Mathematics?

The question might sound a bit *silly*, of course we all know what mathematics are! Everyone has gone through math classes at some point in their lives, or have done arithmetic for grocery shopping. It is apparently a fundamental concept we all think we know but the actual specific meaning isn't that obvious. It reminds me of the famous quote from *Saint Augustine* regarding the concept of time:

> "What, then, is time? If no one asks me, I know what it is. If I wish to explain it to him who asks, I do not know."
> 
> *Confessions* (Book XI, Chapter 14)
{: .prompt-info }

I'd say we are here in a similar situation, but for math, I have a much more satisfactory answer than for time. So <u>what do mathematicians do then?</u> Play a very **peculiar game**. 

### The game

Every game has its own rules and an objective, a wining condition, and Maths are not an exception. We want to <u><strong>prove statements</strong> (winning condition) using the <strong>rules of logic</strong> to derive them from a <strong>set of axioms</strong></u>. You might call it the reasoning game (sounds pretty enjoyable for a weekend plan, I know). And the best of it is that those rules and axioms are arbitrary, so you can change them and do **new math** with that.

> I did have a Calculus professor who shouted *"Gané!"* (I won) at the end of every proof. Much better than *qed* (*quod erat demonstrandum*), you have to give him that.
{: .prompt-info }

> A statement is a proposition, a claim, a fact... That has the property of truth. In most Mathematics, it can only be true or false. But there exists graded logics where you might have different possible values of truth. For example in Fuzzy logic we work with a continuum of possible truth values in the interval $[0,1]$
{: .prompt-tip }

When I say arbitrary, I do NOT mean *random*. Those axioms and rules are at least <u>arguably reasonable</u> and the statements studied by mathematicians almost always have some motivation from real world problems: differential calculus was born for understanding the movement of planets, geometry for working with shapes and sizes, etc. There are even "recreational mathematics" that seemed to be useless when they were being developed and ended up being practical, like number theory which is the basis of cryptography.

So we have mentioned 3 key elements for the game of Mathematics: 
  - **Statements**: they are <u>what we want to either prove or disprove</u>. As we have mentioned, often motivated by some real problem.
  - **Axioms**: can be thought of as a <u>set of statements that you assume to be true without a proof</u>. It is the starting point of the game. 
    - The most common axiomatic system used in mathematics are the Zermelo-Fraenkel axioms upon which you can build set theory and from there, 99% of maths are derived.
    - I said 99% on purpose, because you could take different axioms. But then, you would be playing a different math game. Statements that are true in one game, might be false in another. For example: whether you accept or reject the axiom of choice; or euclidean geometry (2 parallel lines never intersect) vs non-euclidean geometry (2 parallel lines can intersect, like in a spherical surface).
    - In practice, mathematicians don't return to the axioms every time they want to prove a statement. Instead, they typically begin with other statements that have been derived from previous ones, continuing this chain until they eventually reach the axioms, which themselves are not derived.
  - **Rules of logic**: these are chosen in order to satisfy certain desirable properties like consistency (we do not want any contradictions). In the next section we are going to explain them more in detail.


## The rules of logic

Let's have a look at how we actually play the game. We use a formal language, which consists of a set of symbols that carry specific meanings, enabling us to articulate any logical relationships between the statements we wish to explore. The key components of this language include:
  - Quantifiers: symbols used to express the quantity of objects in a statement: $\forall$ (for all), $\exists$ (exists).
  - Logical connectives: symbols that connect statements and define their logical relationships: $\land$ (and), $\lor$ (or), $\neg$ (not), $\implies$ (implies), and $\iff$ (if and only if).
  - Domain: the set of objects we are discussing or the universe of discourse (this could be anything, from natural numbers, to functions, to whatever we want to define).

> We could have used just plain text in English but then proofs would be MUCH longer and it would actually make it harder to read. For example, consider the definition of a continuous function: 
>  
> **With logical symbols**: 
> $\forall \epsilon > 0, \exists \delta > 0, (|x - a| < \delta \implies |f(x) - f(a)| < \epsilon)$ for a function $f$ at a point $a$.
> 
> **In plain English**: 
> For any small positive number (epsilon), there is another small positive number (delta) such that if the distance (measured as the absolute value of the difference between point x and point a) is less than delta, then the distance (measured like before) between point f(x) and point f(a) is less than epsilon.
{: .prompt-tip }

And about the actual rules, you can have a look at the truth table below to have some idea of what they look like in the Boolean Logic case. There are many techniques mathematicians use: proof by reduction to absurd, by counterreciprocal, by induction, by contradiction, and by construction...
In the end it depends on each case and it is almost an art which technique to choose and how to use it in each scenario.

Counterreciprocal for example is based on the *modus tollens*, which is "a form of logical argument where one infers the negation of a premise from the negation of the conclusion". In simpler words, proving $P \implies Q$ is equivalent to proving $\neg Q \implies \neg P$. For example, if we say "If it rains ($P$), then the ground will be wet ($Q$)," proving this is equivalent to proving "If the ground is not wet ($\neg Q$), then it did not rain ($\neg P$)."

### Syntax and semantics
Explain that statements, rules of logic and axioms live in the syntax.
syntax = proof
truth = semantics = models (boolean, fuzzy)
Semantics determine the truth values, makes it concrete. They determine the truth tables. From the abstract to the 
concrete, gives meaning to the objects. Whether P is true or not. Whether the axioms are satisfied or not. And 
this is done through the models. Models can be compatible or not. Can be consistent or not.

In mathematics, when we talk about statements, rules of logic, and axioms, we are referring to elements that exist within the realm of **syntax**. Syntax is essentially the structure or the form of our mathematical language. It is about how we write and manipulate symbols to form proofs. Think of syntax as the grammar and rules of a language that allow us to construct meaningful sentences, or in this case, proofs. The syntax allow as to say $P \implies Q$ without saying what $P$ or $Q$ are and without stating if they are true or not, nor what that "implies" actually mean.

On the other hand, **semantics** is about meaning and truth. It is concerned with what these syntactical structures actually represent in the real world or in any abstract model we choose. Semantics gives life to the syntax by assigning truth values to statements, determining whether they are true or false and what they actually represent. It is to concretize the abstraction of syntax. This is where models come into play.

A model in semantics is a specific interpretation of the symbols and statements in our language. It provides a concrete context in which we can evaluate the truth of statements. For example, in Boolean logic (the most common logic in mathematics), a model might assign the truth value 'true' or 'false' to each statement and also might say that the domain is the natural numbers (the objects we are reasoning about).

> Syntax = proof = symbols = abstract
> 
> Semantics = models = truth value assignation = concrete
{: .prompt-tip }

To make this clearer, let's look at the truth tables for the logical connectives in boolean logic:

| P | Q | P $\land$ Q | P $\lor$ Q | $\neg$P | P $\implies$ Q | Q $\implies$ P | P $\iff$ Q | $\neg$Q | $\neg$Q $\implies$ $\neg$P |
|---|---|-------------|------------|---------|----------------|----------------|------------|--------|--------------------------|
| T | T | T           | T          | F       | T              | T              | T          | F      | T                        |
| T | F | F           | T          | F       | F              | T              | F          | T      | F                        |
| F | T | F           | T          | T       | T              | F              | F          | F      | T                        |
| F | F | F           | F          | T       | T              | T              | T          | T      | T                        |

This is a **truth table**: each line represents a possible case of values for all the statements in the header. It defines the syntactic rules of Boolean logic: it shows how the truth values of statements like $P \implies Q$ depend purely on the truth values of $P$ and $Q$. **These rules are always syntactically true** within Boolean logic.

However, semantic truth depends on how $P$ and $Q$ are interpreted in a specific model. For example, consider these two models:

1. Model 1: $P$ means "It is raining," and $Q$ means "The ground is wet."
Here, if $P$ is true (it is raining), then $Q$ is also true (the ground is wet), making $P \implies Q$ **semantically true**.

1. Model 2: $P$ means "It is raining," and $Q$ means "The ground is dry."
In this case, if $P$ is true (it is raining), then $Q$ must be false (the ground is dry), making $P \implies Q$ **semantically false**.

Thus, while the syntactic rules of Boolean logic remain constant, semantic truth depends on the model's interpretation.
> **semantic true $\neq$ syntactic truth**
{: .prompt-tip }

In summary, **syntax** is about the form and structure of mathematical statements and provide a way to reason precisely without caring about the meaning of each statement or object, while **semantics** assign their meaning and truth. **Models** are the bridge between syntax and semantics, each model provides a way to concretize the objects that comply with the axioms and appear in the statements.

#### Example of the Peano Axioms:

The Peano axioms are a set of axioms for defining the natural numbers proposed by Giuseppe Peano. They can be summarized as follows:

1. **1 is a natural number.**
2. **Every natural number has a successor, which is also a natural number.**
3. **1 is not the successor of any natural number.**
4. **Different natural numbers have different successors.**
5. **If a property is possessed by 1 and also by the successor of every number that possesses it, then it is possessed by all natural numbers (Principle of Mathematical Induction).**

Here are two example models (semantics) of natural numbers that satisfy Peano axioms:

1. **Standard Natural Numbers**: This model includes the set of natural numbers $\mathbb{N} = \{1, 2, 3, \ldots\}$. In this model, every natural number has a unique successor, and the properties of arithmetic hold as expected.

2. **Non-Standard Natural Numbers**: This model extends the standard model to include "infinite" elements, such as $\infty$. In this model, we still have the standard natural numbers, but we also include non-standard elements like $\infty > n$ for every natural number $n$. This model allows for the existence of numbers that are larger than any standard natural number, thus introducing a notion of infinity while still being compatible with the axioms of Peano.

Both models satisfy the Peano axioms, they are **compatible** despite their differences in structure.

> Do not dare to ask whether 0 is a natural number or not. 
{: .prompt-danger }

### Orders of logic

Before jumping into Gödel's theorems we have to understand what is **First-Order-Logic (FOL)**, **Second-Order-Logic (SOL)**, etc.

- FOL: only considers statements over individuals (objects) in the domain.
  - Example: *All humans are mortal.* (mortal is a property of each individual human)
- SOL: considers also statements over sets of individuals in the domain.
  - Example: *Every property that is true of all humans is also true of me.* (notice here all humans is a set and we refer to a property of the set)
- TOL: considers also statements over sets of sets of individuals in the domain.
- Nth-Order-Logic (by induction): considers also statements over sets of sets ... (n-1 times) of individuals in the domain

And why is this relevant? Because **most reasoning in mathematics is FOL** and that is a good thing, since it has some desirable properties that we are going to see in the next section.

### Properties of First-Order-Logic

1. **Simplicity (kind of)**: well, it doesn't have the cascade of sets of sets that higher orders do, but you could argue that it is not *particularly simple*!
2. **Completeness**: "A statement is **semantically true** in *ALL* models compatible with our axioms $\iff$ exists a finite proof from the axioms (**syntactically true**)"
   - Then all the bunch of symbols and rules are *actually* deriving conclusions applicable to our models.
   - This is **GÖDEL'S COMPLETENESS THEOREM**. But wait, weren't we going to talk about *incompleteness*? Isn't this a contradiction?! Wait for the next section ;)
3. **Compactness**: "if every finite subset of a set of FOL has a model $\Rightarrow$ the entire set has a model"
   - Good for defining models in a global set by specifying them in a local finite subset.
4. **Undecidable**: we cannot demonstrate semantic truth for ALL statements with a SINGLE GENERAL procedure. But we might be able to do it for particular statements. 
   - There is no free lunch here, we are not going to find a universal proof of everything, no matter how hard we search for it. But that is what makes maths interesting, there will always be something else waiting for someone to think about it.
   - Disclaimer: this applies only to *sufficiently expressive theories*.

> By <u>sufficiently expressive theories</u> we mean those <u>capable enough to encode arithmetic</u>, like the example with Peano axioms we saw before. So basically, almost any system we might ever be interested in. 
{: .prompt-warning }

So what happens at higher order logics like SOL? We lose completeness, compactness and gain ambiguity! (ambiguity in the sense that semantics depend on the notion of how "all possible subsets" are defined). Pretty hostile territory here. Just imagine finishing a proof, and after all the effort someone told you that it might or might not be semantically true! I would cry and probably you would as well, let's be honest.

## Finally understanding Gödel incompleteness theorems

Now we are in good shape to state not one but TWO incompleteness theorems from Gödel (yuhu!). These theorems apply to FOL capable of expressing arithmetic (for simplicity let's just think about it like compatible with Peano axioms), our recently acquired area of expertise.

> Here we talk about **FOL + Peano axioms**

Before jumping into why in the previous section FOL is complete and now FOL is incomplete, let me tell you that they are talking about *different* meanings of complete. Just let me first introduce you the theorems:

- **First Incompleteness Theorem (FIT)**: In any consistent formal system that is capable of expressing basic arithmetic (FOL + Peano), there exist statements that cannot be proved nor disproved within the system. 

- **Second Incompleteness Theorem (SIT)**: No consistent system of axioms is capable of proving its own consistency. 
  -  In reality it applies to a *recursively enumerable set of axioms*, but I omitted that part because it is not relevant for our purpose. Just remember that it is the case for Peano axioms and for Zermelo-Fraenkel as well.

Focus on the FIT: IF our **system is consistent** THEN there are statements that cannot be proved or disproved. So are those statements True or False then? NEITHER. Since those statements are not axioms, they need to be derived. But they cannot be derived within our system, so they live in the unknown forever! 

> Other systems may be able to prove or disprove them. So we could maybe develop a different theory where they would be reachable. Which theory? Who knows.
{: .prompt-info }

But wait, that is only IF our system is consistent. The other possibility is that our **system is inconsistent**, so that we might or might not have those unknown (there is no theorem that proves or rejects that) and we also have *contradictions*. This alternative is even worse! And if you look at the SIT, you will notice that we cannot justify the consistency of our system within it! So we cannot even know in which scenario we are at: the bad one or the worst one.

### Contradictions with the completeness property of FOL

There is no contradiction, the properties mention cases:
  - **Completeness property** says that if a statement is semantically true, it has a finite proof.
  - **Incompleteness theorem** says that there exists statements that cannot be proved nor disproved. So those statements are neither True or False and therefore the completeness property says NOTHING about them.
    - Well, it does say something: if those statements were true, they would have a finite proof. So they cannot have a finite proof.
  
> Notice that we only say prove truth of a statement because proving it false, would be the same as proving true the negation. So both cases can be modeled as proving a statement true.
{: .prompt-tip }


## Why should we care

Is all **hope lost**? Is **math completely broken** without possible fix? No, **calm down**. 

We have said that there will always be <u>statements that cannot be proved or disproved</u>. So we can <u>append them to our set of axioms</u> by taking them as True or as False (axioms are always true so again, you would take the negation as true in that case). You are changing the rules, **creating more math games!** 

You would also know there are no contradictions because they cannot be proved or disproved, so if our previous axioms where consistent, this addition will keep them consistent. 

And for how long will we have to be appending axioms? Since all those systems will keep being capable of expressing arithmetic, you would never end.

In conclusion, rather than viewing the absence of a defined and limited framework in mathematics as a drawback, I prefer to see it as a sign of the richness of possibilities it offers. It is also a reminder of the importance of having a carefully chosen and solid foundation.

>Just one last thing you might notice. How do we know if a statement is unprovable or is it that we just haven't found the proof? You don't, so you will have to try hard enough to convince yourself it is unprovable. That is the beauty of it. What an *awful* game would be the math game if it didn't pose a challenge!
{: .prompt-tip }

## And what now

Remember the beautiful awesome flawless truth table up there about the evaluation of different connectives? It is clear and unique in our well known comfortable boolean logic. But when we start studying fuzzy logic, turns out there are LOTS of ways to define them. And since I want to really understand why and how to choose one, I'm spending quite some time doing more philosophy than other things. For now, I have yet to understand Pavelka's Rational Logic and why it allows for graded proofs while Lukasiewicz Logic doesn't. Stay tuned on LinkedIn for future updates on my journey!
