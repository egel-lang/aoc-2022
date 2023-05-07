# Advent of Code 2022 solutions

These are the Advent of Code 2022 Egel code solutions.

The daily input files are stored in `input.txt` files. Solutions
to the two tasks are often called `task1.eg` and `task2.eg`.
All scripts take their input from standard in. To run a 
script type `cat input.txt | egel taskx.eg`.

## Problem statements & solutions

<div align="center">

  | Problem | Solution 1 | Solution 2 | Answers |
  |:---:|:---:   |:---    |:---       |
  | **[01](https://adventofcode.com/2022/day/1)**  | [task1.eg](day01/task1.eg) | [task2.eg](day01/task2.eg) | |
  | **[02](https://adventofcode.com/2022/day/2)**  | [task1.eg](day02/task1.eg) | [task2.eg](day02/task2.eg) | |
  | **[03](https://adventofcode.com/2022/day/3)**  | [task1.eg](day03/task1.eg) | [task2.eg](day03/task2.eg) | |
  | **[04](https://adventofcode.com/2022/day/4)**  | [task1.eg](day04/task1.eg) | [task2.eg](day04/task2.eg) | |
  | **[05](https://adventofcode.com/2022/day/5)**  | [task1.eg](day05/task1.eg) | [task2.eg](day05/task2.eg) | |
  | **[06](https://adventofcode.com/2022/day/6)**  | [task1.eg](day06/task1.eg) | [task2.eg](day06/task2.eg) | |
  | **[07](https://adventofcode.com/2022/day/7)**  | [task1.eg](day07/task1.eg) | [task2.eg](day07/task2.eg) | |
  | **[08](https://adventofcode.com/2022/day/8)**  | [task1.eg](day08/task1.eg) | [task2.eg](day08/task2.eg) | |
  | **[09](https://adventofcode.com/2022/day/9)**  | [task1.eg](day09/task1.eg) | [task2.eg](day09/task2.eg) | |
  | **[10](https://adventofcode.com/2022/day/10)** | [task1.eg](day10/task1.eg) | [task2.eg](day10/task2.eg) | |
  | **[11](https://adventofcode.com/2022/day/11)** | [task1.eg](day11/task1.eg) | [task2.eg](day11/task2.eg) | |
  | **[12](https://adventofcode.com/2022/day/12)** | [task1.eg](day12/task1.eg) | [task2.eg](day12/task2.eg) | |
  | **[13](https://adventofcode.com/2022/day/13)** | [task1.eg](day13/task1.eg) | [task2.eg](day13/task2.eg) | |
  | **[14](https://adventofcode.com/2022/day/14)** | [task1.eg](day14/task1.eg) | [task2.eg](day14/task2.eg) | |
  | **[15](https://adventofcode.com/2022/day/15)** | [task1.eg](day15/task1.eg) | [task2.eg](day15/task2.eg) | |
  | **[16](https://adventofcode.com/2022/day/16)** | [task1.eg](day16/task1.eg) | [task2.eg](day16/task2.eg) | |
  | **[17](https://adventofcode.com/2022/day/17)** | [task1.eg](day17/task1.eg) | [task2.eg](day17/task2.eg) | |
  | **[18](https://adventofcode.com/2022/day/18)** | [task1.eg](day18/task1.eg) | [task2.eg](day18/task2.eg) | |
  | **[19](https://adventofcode.com/2022/day/19)** | [task1.eg](day19/task1.eg) | [task2.eg](day19/task2.eg) | |
  | **[20](https://adventofcode.com/2022/day/20)** | [task1.eg](day20/task1.eg) | [task2.eg](day20/task2.eg) | |
  | **[21](https://adventofcode.com/2022/day/21)** | [task1.eg](day21/task1.eg) | [task2.eg](day21/task2.eg) | |
  | **[22](https://adventofcode.com/2022/day/22)** | [task1.eg](day22/task1.eg) | [task2.eg](day22/task2.eg) | |
  | **[23](https://adventofcode.com/2022/day/23)** | [task1.eg](day23/task1.eg) | [task2.eg](day23/task2.eg) | |
  | **[24](https://adventofcode.com/2022/day/24)** | [task1.eg](day24/task1.eg) | [task2.eg](day24/task2.eg) | |
  | **[25](https://adventofcode.com/2022/day/25)** | [task1.eg](day25/task1.eg) | [task2.eg](day25/task2.eg) | |

</div>

## Conclusions

This year's Advent of Code was rather uneventful. I stopped half way to take a break since there was little
point to showing that egel is mostly up to the task.

The lessons learned:

  * As the previous year had shown, egel is far too slow to be very useful. Egel has a robust but expensive
    implementation of a directed acyclic graph rewriter in straightforward C++. That manner, an explicit
    garbage collector is avoided by exploiting smart pointers, but all egel runtime objects are
    rather heavyweight C++ objects resulting in a performance two or three orders of where the author
    would like it to be. A rewrite of the interpreter for the 0.2 version should fix that, hopefully.

  * As a minor point, the pipe `|>` operator, where for example `x |> f |> g` abbreviates `g (f x)`, 
    was added since that allows for a pleasant, now popular, expression of chained function applications.

    Since piping values now becommes an important idiom in egel programs, the `do` notation was also
    added, where `do f |> g` abbreviates `[X -> g (f X)]`, to support a consice manner
    of expressing more complex pipes.

Also, this year's Advent of Code had multiple problematic cases where a solution ran fine on test
input, seemed to implement the specification, but gave the wrong answer on the supplied task. Moreover,
it seems a few Python solutions don't implement the specification right but do pass the given task.
Something seems fishy or sloppy about this year's advent. Moreover, day 22 wasn't done since it more
or less boils down to getting all corner cases right instead of something algorithmically interesting;
for short, just too much boring work.
