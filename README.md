
# Fibonacci Algorithms

[![build](../../actions/workflows/build.yml/badge.svg)](../../actions/)
![Platforms: Linux, MacOS, Windows](https://img.shields.io/badge/Platform-Linux%20%7C%20MacOS%20%7C%20Windows-blue.svg)
[![Language: Python](https://img.shields.io/badge/Language-Python-blue.svg)](https://www.python.org/)
[![Code Style: Black](https://img.shields.io/badge/Code%20Style-Black-blue.svg)](https://github.com/psf/black)
[![Commits: Conventional](https://img.shields.io/badge/Commits-Conventional-blue.svg)](https://www.conventionalcommits.org/en/v1.0.0/)
[![Discord](https://img.shields.io/discord/872320492936257537?logo=discord)](https://discord.gg/kjah8MFYbR)

## Introduction

- Due date: Check Discord or the
  [Course Materials Schedule](https://github.com/allegheny-college-cmpsc-101-spring-2024/course-materials/blob/main/Schedule.md)
- This assignment is graded as
  described in the syllabus section for
  [Assignment Evaluation](https://github.com/allegheny-college-cmpsc-101-spring-2024/course-materials?tab=readme-ov-file#assignment-evaluation)
- Submit this assignment on GitHub following the expectations in the syllabus on
  [Assignment Submission](https://github.com/allegheny-college-cmpsc-101-spring-2024/course-materials#assignment-submission).
- To begin, read this `README` based on the Proactive Programmers' project
  [instructions](https://proactiveprogrammers.com/data-abstraction/engineering-efforts/fibonacci-algorithms/)
- This project has been adapted from Proactive Programmers' material, thus discrepancies are possible.
- Post to the #data-structures Discord channel for questions and clarifications.
- For reference, check the
  [starter repo](https://github.com/allegheny-college-cmpsc-101-spring-2024/fibonacci-algorithms-starter)
- Modifications to the gatorgrade.yml file are not permitted without explicit instruction.

## Learning Objectives

This assignment is about making a Command Line Interface to remove
duplicates in multiple ways.
The learning objectives of this assignment are to:

1. Use Git and GitHub to manage source code file changes
2. Implement and compare fibonacci algorithms using recursive and iterative constructions
3. Use Pythonic expressions to manipulate data containers and code cleanly
4. Use ruff instead of black, isort, flake8, pylint, pydocstyle
5. Write clearly about the programming concepts in this assignment

## Seeking Assistance

Please review the course expectations on the syllabus about
[Seeking Assistance](https://github.com/allegheny-college-cmpsc-101-spring-2024/course-materials#seeking-assistance).
Students are reminded to uphold the Honor Code. Cloning the assignment repository is a
commitment to the latter.

For this assignment, you may use class materials, textbooks, notes, and the
internet. Ensure that your writing is original and based on your own understanding
of the concepts.

To claim that work is your own, it is essential to craft the logic and the
writing together without copying or using the logical structure of another
source. The honor code holds everyone to this standard.

If outside of lab you have questions, the #data-structures Discord channel,
TL office hours, instructor office hours, and GitHub Issues can be utilized.

## Project Overview

After cloning this repository to your computer, please take the following
steps:

- Change into the program directory by typing `cd fibonaccicreator`.
- Install the dependencies for the project by typing `poetry install`.
  - `poetry run fibonaccicreator --number 10000 --approach iterativetuple`
  - Please note that this is not the only configuration you should try for your experiment
  - Please note that the program will not work unless you add the required source code
  - Please refer to the `writing/reflection.md` file for all ways to run the program
  - Please refer to the course web site for more details about this project's configurations
- Confirm that the program is producing the expected output described
  below and on the Proactive Programmers web site.
- Run the automated grading checks by typing
  `gatorgrade --config config/gatorgrade.yml`.
- You may also review the output from running GatorGrader in GitHub Actions.
- Don't forget to provide all of the required responses to the technical writing
  prompts in the `writing/reflection.md` file.
- Please make sure that you completely delete the `TODO` markers and their
  labels from all of the provided source code.
- Please make sure that you also completely delete the `TODO` markers and their
  labels from every line of the `writing/reflection.md` file.

## Project Details

This assignment invites you to implement a program that features multiple
algorithms for computing the numbers in the Fibonacci sequence that is
recursively defined by the following equations for the $n$-th Fibonacci number
$F(n)$.

$$
F(0) = 0
$$

$$
F(1) = 1
$$

$$
F(n) = F(n-1) + F(n-2)
$$

This recursive definition of the Fibonacci sequences yields the values $0, 1, 1,
2, 3, 5, \ldots$ where the value of any Fibonacci number, denoted $F(n)$, is
computed by adding together $F(n-1)$ and $F(n-2)$ and the other starting values
are defined in the first two equations. Since there are different ways to
compute the values in the Fibonacci sequence, this project invites you to
implement and evaluate their performance.

Specifically, you will implement and experimentally evaluate the following
Fibonacci algorithms: (i) a `list`-based approach that uses iteration, (ii) a
`list`-based approach that uses recursion, (iii) a `tuple`-based approach that
uses iteration, and (iv) a `tuple`-based approach using recursion. Along with
adding source code to the provided Python files, you will conduct an experiment
to determine which algorithm is the fastest and aim to understand why it is the
best based on its choice of a data container (i.e., `list` or `tuple`) and its
algorithmic approach (i.e., `iterative` or `recursive`).

## Expected Output

This project invites you to implement a Python program, called
`fibonaccicreator`, that features different ways to compute all of the numbers
in the Fibonacci sequence up to a specified maximum number. After you finish a
correct implementation of all the program's features, running it with the
command `poetry run fibonaccicreator --number 10 --approach recursivelist
--display`, it will produce output like the following.

```cmd
🧳 Awesome, the chosen type of approach is the recursivelist!

🧮 The program will compute up to the 10th Fibonacci number!

✨ This is the output from the recursivelist function:

[0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55]

🤷 So, was this an efficient approach for storing the Fibonacci sequence?

Estimated overall memory according to the operating system:
   30.484375 megabytes

Estimated peak memory according to the operating system:
   38.78515625 megabytes

Estimated execution time according to the simple timer:
    0.01 seconds
```

This output shows that, for instance, the zeroth Fibonacci number is `0`, the
fifth Fibonacci number is `5`, and the tenth Fibonacci number is `55`. This
program output also shows the amount of memory consumed by the `recursive`
implementation of the Fibonacci calculation that stores the data in a `list`
that contains 11 values in it. Importantly, this output also shows that, since
the program had to compute so few of the numbers in the Fibonacci sequence, it
did so in an amount of time that was not measurable by the program's execution
timer. It is worth noting that if you run the `fibonaccicreator` to request a
different data container and algorithm combination with a command like `poetry
run fibonaccicreator --number 10 --approach iterativetuple --display` it should
produce the same numbers in the Fibonacci sequence. With that said, remember
that if you are running an experiment to evaluate the performance of
`fibonaccicreator` when it computes a large Fibonacci number, you should not use
the `--display` parameter since it will cause too much output to appear in your
terminal window.

Don't forget that you can display `fibonaccicreator`'s help menu and learn more
about its features by typing `poetry run fibonaccicreator --help` to show the
following output. This help menu shows that `fibonaccicreator` also has a
`--pyinstrument` flag that enables it to produce a web-based output that shows
the function calls made by the `fibonaccicreator` and the performance results
created by the [Pyinstrument](https://github.com/joerick/pyinstrument) package.

```text
 Usage: fibonaccicreator [OPTIONS]

 Create the list of Fibonacci values in a specified approach.

╭─ Options ─────────────────────────────────────────────────────────────╮
│ *  --approach                TEXT                [default: None]      │
│                                                  [required]           │
│ *  --number                  INTEGER             [default: None]      │
│                                                  [required]           │
│    --display                                                          │
│    --pyinstrument                                                     │
│    --install-complet…        [bash|zsh|fish|pow  Install completion   │
│                              ershell|pwsh]       for the specified    │
│                                                  shell.               │
│                                                  [default: None]      │
│    --show-completion         [bash|zsh|fish|pow  Show completion for  │
│                              ershell|pwsh]       the specified shell, │
│                                                  to copy it or        │
│                                                  customize the        │
│                                                  installation.        │
│                                                  [default: None]      │
│    --help                                        Show this message    │
│                                                  and exit.            │
╰───────────────────────────────────────────────────────────────────────╯
```

Please note that the provided source code does not contain all of the
functionality to produce the output displayed in this section. As the next
section explains, you should add the features needed to ensure that
`fibonaccicreator` produces the expected output!

>Don't forget that if you want to run the `fibonaccicreator` program you must use
>your terminal window to first go into the GitHub repository containing this
>project and then go into the `fibonaccicreator` directory that contains the
>project's source code. Finally, remember that before running the program you
>must run `poetry install` to add its dependencies, such as Pyinstrument,
>Pytest, and Rich.

## Adding Functionality

If you study the file `fibonaccicreator/fibonaccicreator/main.py` you will see
that it has many `TODO` markers that designate the parts of the program that you
need to implement before `fibonaccicreator` will produce correct output. Once
you complete a task associated with a `TODO` marker, make sure that you delete
it and revise the prompt associated with the marker into a meaningful comment.
To ensure that the program works correctly, you must implement all of these
functions in the `fibonacci` module:

- `def fibonacci_recursivelist(number: int) -> List[int]`
- `def fibonacci_recursivetuple(number: int) -> Tuple[int, ...]`
- `def fibonacci_iterativelist(number: int) -> List[int]`
- `def fibonacci_iterativetuple(number: int) -> Tuple[int, ...]`

After finishing your implementation of `fibonaccicreator` you should conduct an
experiment to evaluate the efficiency of the different algorithms that it
provides. You should refer to the `writing/reflection.md` file for more details
about the experiment that you should conduct and how you must configure the
`fibonaccicreator` program to collect data. Ultimately, you need to answer the
following three research questions:

- Is the `fibonaccicreator` faster when it uses the `recursive` or the
  `iterative` method?
- Is the `fibonaccicreator` faster when it stores data in a `list` or a `tuple`
  data container?
- Which configuration of the `fibonaccicreator` is the most memory efficient?
- Overall, what is the fastest approach for computing and storing the Fibonacci
  sequence?
- Overall, are there modes of the `fibonaccicreator` that are less suitable for
  Python?

Please note that there may be certain configurations of the `fibonaccicreator`
program that prove to be very slow or prone to crashing if they receive certain
types of inputs. This type of behavior is expected and something that you must
investigate and work around whenever possible as you design and conduct your
experiments. As you are collecting and analyzing the experimental results for
this project, please do not report on performance data values that arise from a
run of the program that crashed during the experiment.

## Running Checks

If you study the source code in the `pyproject.toml` file you will see that it
includes the following section that specifies different executable tasks like
`ruff`. If you are in the `fibonaccicreator` directory that contains the
`pyproject.toml` file and the `poetry.lock` file, the tasks in this section
make it easy to run commands like `poetry run task ruff` to automatically run
the ruff linter designed to check the Python source code in your program and
its test suite to confirm that your source code adheres to the industry-standard.
You can also use the command `poetry run task fix` to automatically reformat the
source code. `poetry run task ruffdetails` will print out detailed linting errors
that point to exactly what ruff views as a linting error. Make sure to examine
the `pyproject.toml` file for other convenient tasks that you can use to both
check and improve your project!

Along with running tasks like `poetry run task ruff`, you can run the command
`gatorgrade --config config/gatorgrade.yml` to check your work. If your work
meets the baseline requirements and adheres to the best practices that proactive
programmers adopt you will see that all the checks pass when you run
`gatorgrade`. You can study the `config/gatorgrade.yml` file in your repository
to learn how the :material-github:
[GatorGrade](https://github.com/GatorEducator/gatorgrade) program runs
:material-github: [GatorGrader](https://github.com/GatorEducator/gatorgrader) to
automatically check your program and technical writing. If your program has all
of the anticipated functionality, you can run the command `poetry run task test`
and see that the test suite produces output like the following. Can you add
comments to the test suite to explain how the test cases work? It is worth
noting that the name of the test suite is `test_fibonacci` because the
functions mentioned in the previous section exist in the `fibonacci` module.
Can you add comments to explain how these tests work? What are the key
components of every test case created with Pytest?

```text
collected 5 items

tests/test_fibonacci.py .....
```

This project comes with other tasks that you can run once you have used Poetry
to install all of the dependencies. For instance, You
can also run commands like `poetry run task mypy` to check the program's use of
data types and `poetry run task markdownlint` to ensure that your source code
and writing adhere to other established conventions.

>Don't forget that when you commit source code or technical writing to your
>GitHub repository for this project, it will trigger the run of a GitHub
>Actions workflow. If you are a student at Allegheny College, then running
>this workflow consumes build minutes for the course's organization! As such,
>you should only commit to your repository once you have made substantive
>changes to your project and you are ready to confirm its correctness. Before
>you commit to your GitHub repository, you can still run checks on your own
>computer by using Poetry and GatorGrader.

## Project Reflection

Once you have finished both of the previous technical tasks, you can use a text
editor to answer all of the questions in the `writing/reflection.md` file. For
instance, you should provide the output of the Python program in a fenced code
block, explain the meaning of the Python source code segments that you
implemented, and answer all of the other questions about your experiences in
completing this project. A specific goal of the reflection for this project is
to evaluate the efficiency of the different algorithms and data containers
implemented as part of the `fibonaccicreator` program.

In addition to explicitly answering the aforementioned research questions,
please make sure that you explain why the performance trends are evident in your
data by referencing and explaining the source code that implements each of the
algorithms implemented in the `fibonaccicreator`. Once you have finished
addressing the prompts in the `writing/reflection.md` file that have `TODO`
makers given as reminders, make sure that you either delete the prompt or
carefully integrate a revised version of it into your writing.

## Project Assessment

Since this project is an engineering effort, it is aligned with the
**evaluating** and **creating** levels of [Bloom's
taxonomy]. For more details about how to effectively learn technical skills
see Merriam-Webster for the definition of
[Teaching Tech Together](https://teachtogether.tech/en/index.html) and
[How to write SMART goals](https://www.atlassian.com/blog/productivity/how-to-write-smart-goals)
for an overview of how to create SMART goals that are specific, measurable,
achievable, relevant, and time-bound. In your view, what are the benefits of
ensuring that your goals fit into the SMART paradigm?
