# Python Relative Imports
===

This is a small repository for me to work out some details with Python's
relative importing process.

There are two directories here: `foo` and `bar`. The `foo` directory contains
`foo.py`. The `bar` directory contains `bar.py` and `entry.py`

My hope is to be able to run `bar/entry.py`, which would import both `bar/bar.py`
as well as `foo/foo.py`. The second, `foo/foo.py` is proving problematic and
I'm not sure why.

I've found, but may not have understood, resources like [PEP 328](https://www.python.org/dev/peps/pep-0328/), [PEP 366](https://www.python.org/dev/peps/pep-0366/), and
references to things like `__package__`, dot syntax in import statements, and
several other things. I'm sure that somewhere there is a combination of it all
that works - I just haven't understood what that is yet.

## Motivation

My motivation for this is the [2019 Advent of Code](https://adventofcode.com/2019) activity,
for which I want to create directories to hold each day's challenge answer and
associated data. However, in order to prevent code duplication I'd like to be
able to load code from earlier solutions as needed. If I create `planet.py`
on day 3, and need to use it again for the solution to day 5, I'd like to just
do something like `from day3 import planet` rather than needing to create
multiple copies of the file in each directory where I need it.

It may be that I need to abandon this structure, and adopt something else -
perhaps putting each day's solution at the root level, placing data inside the
folders, and maintaining a common folder of code to load as needed from the
repository root.
