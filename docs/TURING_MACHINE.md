# Turing Machine

## Description

A turing machine is a mathematical model of a hypothetical computing device that can simulate any algorithmic process. It consists of a tape, a head, and a set of rules. The head can read and write symbols on the tape, and move left or right. The rules specify what to do when the head reads a symbol.

## Specific Rules

See:
[A Complete Web Page: Building a Turing Machine in JavaScript](https://medium.com/swlh/a-complete-web-page-building-a-turing-machine-in-javascript-d6c32d3708c4)

Symbols are 0, 1, B (blank).
Halting state is `sh`.
Tape is infinite to to both left and right.
Tape starts with '1', '0', '1'
Head starts at the first tape symbol.


## Code

Import this table:

startState symbolRead changeState symbolWrite moveHead
s1 0 s1 0 R
s1 1 s1 1 R
s1 B s2 B L
s2 0 s3 1 L
s2 1 s2 0 L
s2 B s3 1 L
s3 0 s3 0 L
s3 1 s3 1 L
s3 B sh B R

into this structure:

```typescript
interface Rule {
  changeState: string;
  symbolWrite: string;
  moveHead: string;
}

interface State {
  name: string;
  rules: Record<string, Rule>;
}

const states: Record<string, State> = {};
```

Write code to simulate the turing machine. 
Create a Tape class, that has a start state, `symbols`. It has two methods:

- `write(position: number, symbol: string)`: writes a symbol to the tape at a given position
- `read(position: number)`: reads a symbol from the tape at a given position
- `print()`: prints the tape, skip leading and trailing blanks

The Tape class has a `firstPosition` and `lastPosition`. If the head writes prior to the first position, the symbols array should be shifted to the right. If the head writes after the last position, the symbols array should push the newsymbol.

And create a TuringMachine class, that has a states table `states`, start head position, and start state, and a `tape`. It has a method `run()`, that simulates the turing machine.

Print the tape after the machine halts.

## Test

Create a test for the TuringMachine class. Use same input as in `Specific Rules` and check the output.