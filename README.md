NFA: Nondeterministic finite automaton
==============

[![GitHub license](https://img.shields.io/badge/license-MIT-blue.svg)](https://raw.githubusercontent.com/kkdai/nfa/master/LICENSE)  [![GoDoc](https://godoc.org/github.com/kkdai/nfa?status.svg)](https://godoc.org/github.com/kkdai/nfa)  [![Build Status](https://travis-ci.org/kkdai/nfa.svg?branch=master)](https://travis-ci.org/kkdai/nfa)


![image](https://upload.wikimedia.org/wikipedia/commons/thumb/f/f9/NFASimpleExample.svg/423px-NFASimpleExample.svg.png)

What is Nondeterministic finite automaton
=============
In automata theory, a finite state machine is called a deterministic finite automaton (DFA), if

- each of its transitions is uniquely determined by its source state and input symbol, and
reading an input symbol is required for each state transition.
- A nondeterministic finite automaton (NFA), or nondeterministic finite state machine, does not need to obey these restrictions. In particular, every DFA is also an NFA.

Using the subset construction algorithm, each NFA can be translated to an equivalent DFA, i.e. a DFA recognizing the same formal language.[1] Like DFAs, NFAs only recognize regular languages. Sometimes the term NFA is used in a narrower sense, meaning an automaton that properly violates an above restriction, i.e. that is not a DFA.

NFAs were introduced in 1959 by Michael O. Rabin and Dana Scott,[2] who also showed their equivalence to DFAs.  (sited from [here](https://en.wikipedia.org/wiki/Nondeterministic_finite_automaton))


Looking for DFA implement?
=============

I also write a DFA implenent in Go here. [https://github.com/kkdai/dfa](https://github.com/kkdai/dfa)


Installation and Usage
=============


Install
---------------

```go

go get github.com/kkdai/nfa

```

Usage
---------------

```go

package main

import (
    "github.com/kkdai/nfa"
    "fmt"
)

func main() {
	nfa := NewNFA(0, false)
	nfa.AddState(1, false)
	nfa.AddState(2, true)

	nfa.AddTransition(0, "a", 1, 2)
	nfa.AddTransition(1, "b", 0, 2)

	var inputs []string
	inputs = append(inputs, "a")
	inputs = append(inputs, "b")
	fmt.Println("If input a, b will go to final?", nfa.VerifyInputs(inputs) )
}

```

Inspired By
=============

- [NFA: Wiki](https://en.wikipedia.org/wiki/Nondeterministic_finite_automaton)
- [Coursera: Automata](https://class.coursera.org/automata-004/)

Project52
---------------

It is one of my [project 52](https://github.com/kkdai/project52).


License
---------------

This package is licensed under MIT license. See LICENSE for details.
