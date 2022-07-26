# Advent of Code

[Advent of Code](https://adventofcode.com/) is a programming challenge held
every year in December that has been running since 2015. Each day, from the
1<sup>st</sup> to the 25<sup>th</sup>, a new problem is released. The problems
all have numeric solutions and are split into two parts, with the second being
revealed once the first part is solved. They tend to become more difficult as
the month progresses.

Some participants use it as a way to build their programming skills. Others
complete to solve the problems as quickly as possible (points are given to the
first hundred people to finish each one). Still others try to find solutions
that are as concise or elegant as possible.

I've participated each year since 2018 along with some colleagues. I use it as
an opportunity to learn an entirely new language or become more proficient in
one I already know.

## 2018: Go

For my first year, I decided to write my solutions in Go, which is a statically
typed, compiled language. I went through the brief tutorial on Go's homepage in
advance, but otherwise went in completely cold. I had to learn on the fly
during the first few days, but by day 10 or so the difficulty of the problems
surpassed my ignorance of Go as the limiting factor.

Reflecting on my experience with Go, I appreciate the ease of using pointers
without the pitfalls that C and C++ have. The relatively bare-bones standard
library is a drawback. For instance, there's no provided function for adding up
a sequence of numbers. You need to implement it yourself, which isn't difficult
but can become tedious on your tenth project. Since learning it through Advent
of Code, I've used Go for work a few times. I love how easy it is to
cross-compile for other platforms, though package management has been a pain
point.

## 2019: C++ 

In 2018 I wrote my solutions in C++. I had used C++ previously, but most of my
experience was working inside a single, large application for work.  Using it
for Advent of Code gave me more experience with writing C++ programs from
    scratch.

Many of the 2018 problems utilized an assembly-like language called Intcode.
The first few days required building up an Intcode interpreter bit by bit.
Later days provided a Intcode program as input and asked about its behavior,
culminating in [day 25](https://adventofcode.com/2019/day/25) with an adventure
game written in Intcode. Fortunately, my Intcode interpreter functioned
correctly and didn't slow me down on later days.

The most challenging problem for me was [day
22](https://adventofcode.com/2019/day/22), which wasn't an Intcode one. It
involved shuffling a deck of cards by repeating a sequence of steps many, many
times. I realized the solution required modular arithmetic but struggled with
how to compose the sequence with itself over and over and then with find the
inverse of the entire operation. After a while, I eventually had to look up an
explanation.

My favorite problem that year was [day
14](https://adventofcode.com/2019/day/14), which required working through a
large tree of chemical reactions to calculate how many reactants were required
to create the end product.

## 2020: JavaScript

For 2020, I used JavaScript, which was brand new to me at the time. I realize
JavaScript isn't typically used for this sort of programming, but it was still
a useful introduction. Even though I'm far from a web developer, I've been able
to leverage the JavaScript knowledge I built through Advent of Code for other
projects that I otherwise wouldn't have worked on.

2020 was perhaps my favorite so far in terms of problems. [Day
19](https://adventofcode.com/2020/day/19) involved using formal grammar to see
which strings matched a set of rules. [Day
21](https://adventofcode.com/2020/day/21) required deduction to determine which
elements (food ingredients) had particular properties (allergens) based on
information about sets of those elements (foods).

## 2021: Rust

For 2021, I wrote my answers in Rust, another statically typed, compiled
language. Like Go and JavaScript, Rust was completely new to me when I started.
I liked the way it handles errors and `None`. However the nuances of ownership
never really clicked with me, and I spent more time than I wanted wrestling
with compiler errors on later days.

The problem that took me the longest was [day
22](https://adventofcode.com/2021/day/23), which boiled down to finding the
shortest path through a graph, a common theme in Advent of Code problems. I
started with [Dijkstra's
algorithm](https://en.wikipedia.org/wiki/Dijkstra%27s_algorithm) and switched
to [A\*](https://en.wikipedia.org/wiki/A*_search_algorithm) to improve
efficiency but still had trouble finding a route to the goal. With enough
optimization, I eventually found one, but the total cost was too small. After
much fruitless bug hunting, I relented and looked up other people's solutions
to see where I'd gone wrong. It turned out I had overlooked a rule in the
problem statement, meaning I had solved a more general version. Always read the
instructions!
