<p align="center">
  <img width="556" height="112" src="https://github.com/ShikharJ/GSoC-2018-Work-Report/blob/master/src/gsoc.png">
</p>

My proposal for **Implementing Essential Deep Learning Modules** was selected as an official project under **Google Summer of Code 2018**. I worked with the organisation [Mlpack](https://github.com/mlpack/), under the mentorship of **Marcus Edel** ([@zoq](https://github.com/zoq)).

## Goal

`SymPy` is a `Python` based library for Symbolic Mathematics. It aims to become a full-featured Computer Algebra System (CAS) while keeping the code as simple as possible in order to be comprehensible and easily extensible.
The `SymPy` organization also supports `SymEngine`, a standalone fast `C++` symbolic manipulation library with wrappers in many languages, including `C`, `Python`, `Ruby`, `Julia` and `Haskell`.

Speed is of the utmost importance for any CAS.

`SymEngine`, was initially developed with the aim of serving as an optional core for the `SymPy` CAS in the future. Over the years, it has matured enough to be used as a symbolic backend. Using `SymEngine` can significantly increase speeds of various symbolic operations, and hence make `SymPy` an ideal choice for projects requiring fast manipulations, by giving them the option to switch over to `SymEngine`’s routines.

On the other hand, this will also lead to the development of a number of features currently lacking in `SymEngine` and its `Python` wrapper, which would be ported over from `SymPy` in order to provide smooth wrappers for optional use.

## Results

Considering that we had to deviate a lot from my original proposal plan, and also incorporate additional tasks and roadblocks due to inconsistency issues, I'd say that, overall, the basic idea of my project was achieved.

My first task under the official GSoC period was to implement some additional functionalities for `DenseMatrix` in `SymEngine` and introducing `MutableDenseMatrix`, `ImmutableDenseMatrix` and `Float` classes in `SymEngine.py`, all of which occurred during the first half of the Community Bonding Period.

During the second half of the Community Bonding, my focus shifted to implementing `Relationals` in `SymEngine` and making structural changes to `SymEngine.py`, along with wrapping `Min` and `Max` functions.

After this, the time till the first evaluations was utilised for a number of goals. Classes `Dummy`, `Floor`, `Sign`, `Ceiling` and `Conjugate` were implemented in `SymEngine` and the Parser support was improved, along with wrapping `Infinity`, `NaN` and `Relational` classes  and subclasses in `SymEngine.py` along with a huge portion of `Function` classes. During this time, I was asked by Isuru if we could work on porting `SymEngine` to `PyDy`, for which a number of additional tasks were made and completed.

The progress between the first and the second evaluations was albeit much slower. I started off by wrapping the `Logic` classes from `SymEngine`, along with improving some portions of our `C` wrappers. After this task, my focus was shifted to initiate the implementation of the `Singleton` pattern in `SymEngine.py`, which took quite a bit of time. I also spent a huge amount of time figuring out and keeping a hand-written log of the various `Assertion Failures`, `Wrong Outputs` and `Exceptions` incurred along the way of using `SymEngine` as a backend in `SymPy`. It was my first experience at realising the importance of software testing. During this time, we were succesfully able to port `SymEngine` under `LieAlgebras` module completely.

The time before the last evaluations was also a bit slow, partly due to the fact that my college had resumed after the summer vacations with a rather hectic schedule, and also because Isuru and Sumith were both busy for a week, and I couldn't make much headway during that time. Anyways, I was able to get a number of miscellaneous functionalities from `SymPy` ported over to `SymEngine.py`. I also worked on introducing `SymPy` style attributes (`is_commutative`, `is_integer`...). Finally, I pushed in a couple of PRs for updating `SymEngine` and `SymEngine.py`'s dev binaries in `Conda`, which allowed me to use all the functionalities I had implemented till the moment, in `SymPy`. The work is pushed in separate pull requests, and should be merged soon.

### Links To Commits

[SymEngine](https://github.com/symengine/symengine/commits?author=shikharj)

<p align="left">
  <img width="458" height="193" src="https://github.com/ShikharJ/GSoC-2017-Work-Report/blob/master/src/SymEngine.jpg">
</p>

[SymEngine.py](https://github.com/symengine/symengine.py/commits?author=shikharj)

<p align="left">
  <img width="459" height="198" src="https://github.com/ShikharJ/GSoC-2017-Work-Report/blob/master/src/SymEnginepy.jpg">
</p>

[SymPy](https://github.com/sympy/sympy/commits?author=shikharj)

## Pending Pull Requests

Since it was only much later that I was able to make use of the functionalities that I had worked on over the summer, my final work got a bit delayed. Thankfully, Isuru allowed me to work on this even after the GSoC period ends. The PRs mentioned here are mostly complete, requiring just some minor tweaks.

[SymPy](https://github.com/sympy/sympy/pulls/ShikharJ)


## Scope and Future Work

Work on this project is far from over. `SymPy` codebase is huge, and given the number of active contributors and beneficiaries, it's only going to increase and incorporate more and more functionalities in the future. During this summer, only the functionalities that were common to `SymEngine` and `SymPy` were ported over through `SymEngine.py`. However, still, a gargantuan amount of assertion failures, exceptions and inconsistencies had to be resolved to finally get the code running, which took up a lot of time during this project. We still currently don't have the assumptions and calculus module available in `SymEngine`, both being full-length `GSoC` projects on their own. Hence, this work is expected to continue for the time to come.

## Conclusion

I have no words to describe how grateful I am to my mentors - [Isuru](https://github.com/isuruf) and [Sumith](https://github.com/Sumith1896) - for all their support and for being extremely responsive and helpful with every one of my problems. Without their vote of confidence, this project would've been a lot harder and a lot less fun to do.

I would be lucky to get to work with them further as I continue work on this project till the time `SymEngine` becomes the default core of the `SymPy` library.

I am also thankful to `SymPy` and `Google` for the opportunity to work on this project, which helped me learn a lot in such a short period of time.
