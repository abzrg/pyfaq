# Python FAQ

## How Python's import system works:

Docs:

- [The import system (ref)](https://docs.python.org/3/reference/import.html)
- [Modules (tutorial)](https://docs.python.org/3/tutorial/modules.html)
- [`importlib` -- the implementation of `import`](https://docs.python.org/3/library/importlib.html)
- [PEP 420 – Implicit Namespace Packages](https://peps.python.org/pep-0420/)

Videos:

- [Python's Import System - Module object\|Regular/Namespace Packages\|Finders \& Loaders\|Relative imports](https://www.youtube.com/watch?v=QCSz0j8tGmI)
- [David Beazley - Modules and Packages: Live and Let Die! - PyCon 2015](https://youtu.be/0oTh1CXRaQ0)

## How to debug Python codes (pdb)

Docs:

- [pdb -- The Python Debugger (library)](https://docs.python.org/3/library/pdb.html)

Videos:

- [Nathan Yergler: In Depth PDB - PyCon 2014](https://youtu.be/lnlZGhnULn4)
- [Clayton Parker - So you think you can PDB? - PyCon 2015](https://youtu.be/P0pIW5tJrRM)

  ```py
  # in the code
  import pdb; pdb.set_trace()
  # or from commandline: python -m pdb example.py
  ```

  - `help/?`:
    - `?`: to know what commands are available
    - `? help`: help on a command
  - `list/l`: shows, by default, the next 10 lines
    - `l`, `l 3,9`
  - `p`: to see what a variable is set to
  - `pp`: pretty print the result for easier reading (esp. dicts)
  - `next/n`: go to the next line
  - `step/s`: step into a function for further inspection
  - `<cr>`: returns the previous command
  - `until`: skip over the end of a loop
  - `return/r`: skip to the end of a function
  - `break/b`:
    - `b`: list break points
    - `b <linenum/funcname>`: set a breakpoint
    - `clear/cl <bpnum>`: clear breakpoint with breakpoint number `bpnum`
      - usefull when you don't want to hit a breakpoint again
  - `continue/c`: go to the next breakpoint or finish execution
  - conditional breakpoints:
    - breakpoints that take an expression to know when to break
    ```
    b 11, this_year == 2015  # bp at line 11 when `this_year` is 15
    ```
  - `where/w`: see the current stack. you can debug at any point in the stack
    - `>` symbol shows where on the stack you are.
    - `up/u`: go up the stack
    - `down/d`: go back down the stack

  - `interact`: open an interpreter in the current scope
    - write if-statements, create class, function,... in the current scope
    - drops you into a python prompt
  - `longlist/ll`: show the complete current function
  - `quit/q`: exit pdb and stop execution
  - PDB alternatives:
    - PDB++
    - ipdb
    - rpdb / remote-pdb
  - Helpers
    - vimpdb
    - flake8-debuggers: warns you when you left a pdb in your code
  - `.pdbrc`: personalize your experience
    - set up aliases / custom mapping
    - enhance with readline support
