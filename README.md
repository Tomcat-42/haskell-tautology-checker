# haskell-tautology-checker

Project under development for
[(LAMBDA (PET)) MAROMBA::FUNCTIONAL Edition® 2021](https://github.com/petcomp-unioeste/lambda-pet/tree/Lambda2021).

<figure>
  <img src="https://i.imgur.com/ftAfZwt.png" alt="my alt text" width=60%/>
  <figcaption><b>Figure 1:</b> Average LAMBDAPET member</figcaption>
</figure>

Also, it serves as a way for me to try to learn haskell ~~for the third time~~.

## Table of Contents

-   [haskell-tautology-checker](#haskell-tautology-checker)
    -   [Propositional Logic](#propositional-logic)
        -   [Propositions](#propositions)
        -   [Logical connectives](#logical-connectives)
        -   [Logical Formulas](#logical-formulas)
            -   [Tautology](#tautology)
            -   [Truth table](#truth-table)
    -   [Goal](#goal)
    -   [Building and installation](#building-and-installation)
    -   [Usage](#usage)

## Propositional Logic

[Propositional logic](https://en.wikipedia.org/wiki/Propositional_calculus) is a
branch of [logics](https://en.wikipedia.org/wiki/Logic) that deals with
[propositions](https://en.wikipedia.org/wiki/Proposition)(sentences) that can be
true or false, and studies the relations between them and the construction and
analysis of arguments.

### Propositions

A proposition is a statement like _"Socrates is a man"_ or _"All man is mortal"_
that can be true or false. Variables names like _p_, _q_, _r_ and so on are
generally associated with logic propositions:

_p_ = "All man is mortal"

_q_ = "Socrates is a man"

_r_ = "Socrates is mortal"

### Logical connectives

Logical connectives are symbols used to connect semantically sentences such that
the value of the compound sentence produced depends on the propositions and the
meaning of the connective.
[Some common connectives and the corresponding symbols](https://en.wikipedia.org/wiki/Logical_connective#Common_logical_connectives)
are:

| Meaning                                | Symbol | Example |
| -------------------------------------- | ------ | ------- |
| And                                    | ∧      | p∧q     |
| Or                                     | ∨      | p∨q     |
| Implies(if...then)                     | →      | p→q     |
| Biconditional(if and only if ... then) | ↔      | p↔q     |
| Not                                    | ¬      | ¬p      |

For example, if _p_ is _true_ and q is _false_ then _p∨q_ is _true_, _p∧q_ is
_false_, and so on.

### Logical Formulas

The combination of propositions and connectives creates a
[logic formula](https://en.wikipedia.org/wiki/Well-formed_formula#Propositional_calculus)(or
compound proposition), that also is true or false. A logic formula is parsed
recursively as follows: Each proposition for itself is a formula and the unary
and binary connectors applied to propositions are also a formula. Parenthesis
can be used to explicitly choose the order of operations, which by default
follow an
[order of precedence](https://en.wikipedia.org/wiki/Logical_connective#Order_of_precedence)
and are parsed from left to right.

For example, the formula _(p→q)∧(p↔¬q)_ is parsed and evaluated as follows:

| _p_ | _q_ | _¬q_ | _p→q_ | _p↔¬q_ | _(p→q)∧(p↔¬q)_ |
| --- | --- | ---- | ----- | ------ | -------------- |
| v   | v   | f    | v     | f      | f              |
| v   | f   | v    | f     | v      | f              |
| f   | v   | f    | v     | v      | v              |
| f   | f   | v    | v     | f      | f              |

#### Tautology

If a logic formula is true under any possible boolean evaluation of its
propositions, then its called a
[tautology](<https://en.wikipedia.org/wiki/Tautology_(logic)>).

#### Truth table

If there are _n_ propositional variables occurring in a formula, then there are
2<sup>n</sup> distinct valuations for the formula. So, to determine if a formula
is a tautology it is necessary to evaluate a formula under every possible
combination of values for the propositional variables

For instance, the formula _p∨(p→q)_ is a tautology because its _true_ for every
possible boolean value of _p_ and _q_:

| _p_ | _q_ | _p → q_ | _p ∨ (p → q)_ |
| --- | --- | ------- | ------------- |
| v   | v   | v       | v             |
| v   | f   | f       | v             |
| f   | v   | v       | v             |
| f   | f   | v       | v             |

The truth table method complexity is exponential, because the numbers of
valuations that must be checked increases as 2<sup>k</sup>, where _k_ is the
number of propositional variables. This exponential growth renders the truth
table method impracticable as _k_ becomes really large, however, for smaller _k_
this method is very effective and viable.

## Goal

The goal of this project is to evaluate a logical formula using the truth table
method and consequently check if it is a tautology.

## Building and installation

This project uses [stack](https://docs.haskellstack.org/en/stable/README/), so
for building it:

```bash
# Download and setup ghc
stack setup
# Build and Execute
stack build
stack exec haskell-tautology-checker
# Or just run a REPL
stack ghci

```

[Good luck installing stack m8](https://docs.haskellstack.org/en/stable/README/#how-to-install).

## Usage

-   [ ] TODO
