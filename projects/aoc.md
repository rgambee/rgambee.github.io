# Advent of Code

[Advent of Code](https://adventofcode.com/) is a programming challenge held
every year in December and has been running since 2015. A new proglem is
released on each day from the 1<sup>st</sup> to the 25<sup>th</sup>. The
problems all have numeric solutions and are split into two parts, with the
second being revealed once the first part is solved. They tend to become more
difficult as the month progresses.

Some participants use it as a way to build their programming skills. Others
complete to solve the problems as quickly as possible (points are given to the
first hundred people to finish each one). Still others try to find solutions
that are as concise or elegant as possible.

I've participated each year since 2018 along with some colleagues. I use it as
an opportunity to learn an entirely new language or become more proficient in
one I already know. All my solutions are available in my [`advent-of-code`
repository](https://github.com/rgambee/advent-of-code).

## 2018: Go

For my first year, I decided to write my solutions in Go, which is a statically
typed, compiled language. I went through the brief tutorial on Go's homepage in
advance, but otherwise went in completely cold. I had to learn on the fly
during the first few days, but by day 10 or so the difficulty of the problems
surpassed my ignorance of Go as the limiting factor.

Reflecting on my experience with Go, I appreciate how easy it is to use
pointers without the pitfalls that C and C++ have. On the other hand, the
relatively bare-bones standard library is a drawback. For instance, there's no
provided function for adding up a sequence of numbers. You need to implement it
yourself, which isn't difficult but can become tedious on your tenth project.
Since starting to learn it through Advent of Code, I’ve used Go for work a few
times, where the simplicity of cross compiling for other platforms is a major
boon.

Day 23 ([prompt](https://adventofcode.com/2018/day/23),
[solution](https://github.com/rgambee/advent-of-code/blob/master/2018/day23/solution23.go))
was challenging but fun. It involved overlapping cubes distributed in 3D space.
Part 1 required finding how many other cubes a particular one overlapped with,
which was feasible to do naively. Part 2 required finding which point in space
was within the largest number of cubes and was infeasible to solve naively.
After many attempts, I used [octrees](https://en.wikipedia.org/wiki/Octree) to
efficiently find a small volume containing the desired point and then searched
that exhaustively.  I had heard of octrees before, but this was my first time
using them.

## 2019: C++ 

In 2018 I wrote my solutions in C++. I had used C++ previously, but most of my
experience was working inside a single, large application for work. Using it
for Advent of Code gave me more experience with writing C++ programs from
scratch.

Many of the 2018 problems utilized an assembly-like language called Intcode.
The first few days required building up an Intcode interpreter bit by bit.
Later days provided a Intcode program as input and asked about its behavior,
culminating in day 25 ([prompt](https://adventofcode.com/2019/day/25),
[solution](https://github.com/rgambee/advent-of-code/blob/master/2019/day25/solution25.cpp))
with an adventure game written in Intcode. Fortunately, my Intcode interpreter
functioned correctly and didn't slow me down on later days.

My favorite problem that year was day 14
([prompt](https://adventofcode.com/2019/day/14),
[solution](https://github.com/rgambee/advent-of-code/blob/master/2019/day14/solution14.cpp)),
which required working through a large tree of chemical reactions to calculate
how many reactants were required to create the end product.

The most challenging problem for me was day 22
([prompt](https://adventofcode.com/2019/day/22),
[solution](https://github.com/rgambee/advent-of-code/blob/master/2019/day22/solution22.cpp)),
which didn't use Intcode. Instead, it involved shuffling a deck of cards by
repeating a sequence of steps many, many times. I realized the solution
required modular arithmetic but struggled with how to compose the sequence with
itself over and over and then with find the inverse of the entire operation.
After a while, I eventually had to look up an
[explanation](https://codeforces.com/blog/entry/72593).

## 2020: JavaScript

For 2020, I used JavaScript, which was brand new to me at the time. I realize
JavaScript isn't typically used for this sort of programming, but it was still
a useful introduction. Even though I'm far from a web developer, I've been able
to leverage the JavaScript knowledge I built through Advent of Code for other
projects that I otherwise wouldn't have worked on.

2020 was my favorite year so far in terms of problems. Day 19
([prompt](https://adventofcode.com/2020/day/19),
[solution](https://github.com/rgambee/advent-of-code/blob/master/2020/day19/solution19.js))
involved using formal grammar to see which strings matched a set of rules. Day
21 ([prompt](https://adventofcode.com/2020/day/21),
[solution](https://github.com/rgambee/advent-of-code/blob/master/2020/day21/solution21.js))
required deduction to determine which elements (food ingredients) had
particular properties (allergens) based on information about sets of those
elements (foods).

## 2021: Rust

For 2021, I wrote my answers in Rust, another statically typed, compiled
language. Like Go and JavaScript, Rust was completely new to me when I started.
I liked the way it handles errors and `None`. However the nuances of ownership
never really clicked with me, and I spent more time than I wanted wrestling
with compiler errors on later days.

The problem that took me the longest was day 23
([prompt](https://adventofcode.com/2021/day/23),
[solution](https://github.com/rgambee/advent-of-code/blob/master/2021/src/day23/solution23.rs)),
which boiled down to finding the shortest path through a graph, a common theme
in Advent of Code problems. I started with [Dijkstra's
algorithm](https://en.wikipedia.org/wiki/Dijkstra%27s_algorithm) and switched
to [A\*](https://en.wikipedia.org/wiki/A*_search_algorithm) to improve
efficiency but still had trouble finding a route to the goal. With enough
optimization, I eventually found one, but the total cost was too small. After
much fruitless bug hunting, I relented and looked up other people's solutions
to see where I'd gone wrong. It turned out I had overlooked a rule in the
problem statement, meaning I had solved a more general version. A valuable
lesson to always read the instructions!
