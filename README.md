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

## Functions

### Function signature (positional and keyword only arguments)

Docs:

- [Example code -- mCoding](https://github.com/mCodingLLC/VideosSampleCode/blob/c13fcff31a34ccf767515134bf2c3e63a4e1acae/videos/094_positional_and_keyword_only_args/positional_and_keyword_only_args.py)
- [PEP 570 – Python Positional-Only Parameters](https://peps.python.org/pep-0570/)
- [PEP 3102 – Keyword-Only Arguments](https://peps.python.org/pep-3102/)

Videos:

- [Positional-only and keyword-only arguments in Python](https://youtu.be/R8-oAqCgHag)

## Static Type Checking

Docs:

- [PEP484](https://peps.python.org/pep-0484/)
- [typing — Support for type hints](https://docs.python.org/3/library/typing.html)

Videos:

- [Python's type system explained: Static vs dynamic typing | Guido van Rossum and Lex Fridman](https://www.youtube.com/watch?v=kSXZHRsWXfU)
- [Jukka Lehtosalo - Getting Started with Mypy and Type Checking (talk by author himself)](https://youtu.be/18nZ5xMeGno)
  - [Jukka Lehtosalo, David Fisher Static Types for Python PyCon 2017](https://www.youtube.com/watch?v=7ZbwZgrXnwY)
- [Static type checking with mypy | Swiss Python Summit 2022 (pretty complete)](https://youtu.be/CKZ6uXOT7sE)
  - [Python 3.10's new type hinting features](https://www.youtube.com/watch?v=mvJuxowIwIc)
  - [Python 3.12 Generic Types Explained](https://www.youtube.com/watch?v=q6ujWWaRdbA)
- [Static type checking with Mypy — Perfect Python (some information about config)](https://youtu.be/9gNnhNxra3E)
- [Carl Meyer - Type-checked Python in Real World - PyCon 2018](https://www.youtube.com/watch?v=pMgmKJyWKn8)
- [Python Typing - Type Hints & Annotations](https://www.youtube.com/watch?v=QORvB-_mbZ0)
- [Type hinting / annotation (PEP 484) for numpy.ndarray](https://www.youtube.com/watch?v=EbakDGeD-vk)

Mypy:

- W [gradual typing python (and my approach) (beginner - intermediate) anthony explains #308](https://www.youtube.com/watch?v=Rk-Y71P_9KE)
- [mypy: possible cyclic definition fix (intermediate) anthony explains #379](https://www.youtube.com/watch?v=O_CYtaDlOO4)
- [typing __getitem__ (python / mypy) (intermediate) anthony explains #045](https://www.youtube.com/watch?v=HESA7oukEqE)
- W [debugging mypy types (beginner - intermediate) anthony explains #299](https://www.youtube.com/watch?v=Pc6H3Pofhp8)
- [SUPER FAST cpython with mypyc (intermediate) anthony explains #280](https://www.youtube.com/watch?v=0Cjg3qvHBEY)
- [mypy! this key exists I promise! (beginner - intermediate) anthony explains #330](https://www.youtube.com/watch?v=HE0At4RrZIE)
- W [one-off 3rd party mypy types (intermediate) anthony explains #248](https://www.youtube.com/watch?v=mKmmZHMwXAY)
- W [mypy's "implicit optional" (and why I disable it) (intermediate) anthony explains #147](https://www.youtube.com/watch?v=sc1JfhSvSII)
- W [opinion: don't bother typing tests (intermediate) anthony explains #347](https://www.youtube.com/watch?v=lGCU0j-otls)
- W [typing Self (PEP 673) (intermediate) anthony explains #418](https://www.youtube.com/watch?v=ThATVufmTz8)
  - [python typing: why not self? (intermediate) anthony explains #076](https://www.youtube.com/watch?v=VumItqHMaTA)
- W [python typing: Optional is not optional! (intermediate) anthony explains #146](https://www.youtube.com/watch?v=7XZYlDpSxOU)
- W [python typing: object vs Any (intermediate) anthony explains #275](https://www.youtube.com/watch?v=ATS9MAo2Mjc)
- [python typing: re.match and Optional (intermediate) anthony explains #115](https://www.youtube.com/watch?v=yH6L3UiK9WM)
- [python typing: explicit TypeAlias (PEP 613) (intermediate) anthony explains #365](https://www.youtube.com/watch?v=50SqDLU-6RE)
- W [python Generics (intermediate) anthony explains #430](https://www.youtube.com/watch?v=LcfxUU1A-RQ)
  - [typing: what is Type\[X\]? (intermediate) anthony explains #096](https://www.youtube.com/watch?v=_7EXU9cjBkg)
  - [python variadic generics (PEP 646) (intermediate - advanced) anthony explains #433](https://www.youtube.com/watch?v=hAj3nGzeSiQ)
  - W [python typing: Generator\[T, S, R\] (intermediate) anthony explains #297](https://www.youtube.com/watch?v=DTegfCNAXoM)
- [fixing NameError / TypeError in python type annotations (intermediate) anthony explains #104](https://www.youtube.com/watch?v=zH_F2xC0LOk)
- [python typing: Final / @final (intermediate) anthony explains #132](https://www.youtube.com/watch?v=jCf3zi2m56c)
- [python: typing *args / **kwargs (intermediate) anthony explains #145](https://www.youtube.com/watch?v=CqafM-bsnW0)
- W [structural subtyping in python with Protocol! (intermediate) anthony explains #164](https://www.youtube.com/watch?v=QjFChmQHJxk)
- W [typing: why main() -˃ int (beginner - intermediate) anthony explains #110](https://www.youtube.com/watch?v=Kur4Y7j4vac)
- W [python: Ellipsis (...) and typing (beginner - intermediate) anthony explains #067](https://www.youtube.com/watch?v=yLwvOwTO068)
- [python typing: @property (beginner - intermediate) anthony explains #117](https://www.youtube.com/watch?v=Q0K8CKn5htI)
  - [decorator typing (PEP 612) (intermediate - advanced) anthony explains #386](https://www.youtube.com/watch?v=fwZoxWyMGM8)
- W [packaging python typed code (intermediate) anthony explains #252](https://www.youtube.com/watch?v=n4GJ8rp6DpE)
- W [is python with types faster? (intermediate) anthony explains #126](https://www.youtube.com/watch?v=mkT3KP2J15I)
- W [python typing: TYPE_CHECKING (intermediate) anthony explains #312](https://www.youtube.com/watch?v=BPE4p8HNLFM)
- W [typing: Protocol + @runtime_checkable (intermediate) anthony explains #187](https://www.youtube.com/watch?v=4y94mvp_rYw)
- W [python TypeGuard (PEP 647) (intermediate) anthony explains #439](https://www.youtube.com/watch?v=Zv2K2AVy5lA)
- W [python: NewType vs aliases (intermediate) anthony explains #368](https://www.youtube.com/watch?v=9rRYeunzX8c)
  - [python typing: aliases (beginner - intermediate) anthony explains #180](https://www.youtube.com/watch?v=4zcrkP2VPSs)
- [python typing: @overload (intermediate) anthony explains #163](https://www.youtube.com/watch?v=rY9NZ-tXiDQ)
- [python typing: NotImplemented is a bool? (intermediate) anthony explains #276](https://www.youtube.com/watch?v=5XBs_fM3Nac)
- [generator basics (+typing) (beginner - intermediate) anthony explains #077](https://www.youtube.com/watch?v=LjBa9sfJh7U)

- [Haki Benita: Practical Advice for Using Mypy](https://www.youtube.com/watch?v=fyiIJ2Qy8ss)
- [mypy Getting to Four Million Lines of Typed Python - Michael Sullivan](https://www.youtube.com/watch?v=FT_WHV4-QcU)
- [Convincing an entire engineering org to use and like mypy](https://www.youtube.com/watch?v=S75VVAZmqZ8)
- [Start Being Static with MyPy - Mark Koh - PyGotham 2017 (explains stub files)](https://www.youtube.com/watch?v=nnI2Iy8mVDA)

## Testing

Videos:

- [Automated Testing in Python with pytest, tox, and GitHub Actions](https://www.youtube.com/watch?v=DhUpxWjOhME)

## Python data structures

Docs:

- [builtin types -- python library](https://docs.python.org/3/library/stdtypes.html#set)

### set

Docs:

- [set -- bulitin types](https://docs.python.org/3/library/stdtypes.html#set-types-set-frozenset)

About:

- A set object is an unordered collection of distinct hashable objects. Common
  uses include membership testing, removing duplicates from a sequence, and
  computing mathematical operations such as intersection, union, difference, and
  symmetric difference.

- Like other collections, sets support `x in set`, `len(set)`, and `for x in set`.
  Being an _unordered_ collection, sets do not record element position or order of
  insertion. Accordingly, sets do not support indexing, slicing, or other
  sequence-like behavior.

- There are currently two built-in set types, `set` and `frozenset`. The `set` type is
  _mutable_ — the contents can be changed using methods like `add()` and `remove()`.
  Since it is mutable, it has no hash value and cannot be used as either a
  _dictionary key_ or as _an element of another set_. The `frozenset` type is _immutable_
  and hashable — its contents cannot be altered after it is created; it can
  therefore be used as a dictionary key or as an element of another set.

- Non-empty sets (not `frozensets`) can be created by placing a comma-separated
  list of elements within braces, for example: `{'jack', 'sjoerd'}`, in addition to
  the set constructor.

Create:

- Use a comma-separated list of elements within braces: `{'jack', 'sjoerd'}`
- Use a set comprehension: `{c for c in 'abracadabra' if c not in 'abc'}`
- Use the type constructor: `set()`, `set('foobar')`, `set(['a', 'b', 'foo'])`

```py
s = set() # not {}
s = {1}
s = {1, 1} # -> s = {1}
s = {1, 2, 3}
s = set([1, 2, 3]) # iterable must be passed
s = {1, '2', {3: ('Hello', 'world')} }
```

Methods ([ref](https://youtu.be/sBvaPopWOmQ)):

- `.add(...)`: add an element to a set (this has no effect if the element is already present)
  - if the type is not "hashable" it raises TypeError. e.g. you cannot pass a list
- `.update(iterable1[, iterable2, ...])`: add values in the iterable to the list
  - values in the iterable must be hashable
  - `set |= others | ...`
- `.pop()`: Remove and return an arbitrary element from the set. Raises `KeyError` if the set is empty.`
- `.remove(...)`: removes the element if it's a member, otherwise raises a `KeyError`
- `.discard(...)`: like `.remove`, but if the element is not a member, does nothing
- `.clear()`: to empty out the set
- `.union(<*others>)`: returns a new set that is the union of self and other
  - `set | other | ...`
- `.intersection(<*others>)`: returns a new set that is intersection of self and other
  `set & other & ...`
- `.difference(<*others>)`: returns set of values that are in self but not in <other> (asymmetric difference)
  - `set - other - ...`
- `.symmetric_difference(<*others>)`: returns set of values that are not shared by both self and other
  - `set ^ other ^ ...`
- `intersection_update(*others)`: Update the set, keeping only elements found in it and all others.
  - `set &= other & ...`
- use `in` and `not in` operators to check if a value is in the set

patterns:

- removing duplicates in a list

  ```py
  l = [...]
  l_nodup = list(set(l))
  ```

- intersection of two lists:

  ```py
  employees = [...]
  gym_members = [...]
  developers = [...]

  result = set(gym_members).intersection(developers)
  ```

- detect positive words

  ```py
  POS_WORDS = {'awesome', ...}
  NEG_WORDS = {'hate',...}

  def detect_positive(review: str) -> bool:
      words = review.split()
      count_positive = len(POS_WORDS.intersection(words))
      count_negative = len(NEG_WORDS.intersection(words))
      return count_positive >= count_negative
  ```

### dict

empty dict:

```py
d = dict()
#or
d = {}
```

methods ([ref](https://www.youtube.com/watch?v=u0yr9B3nH8c)):

- `.keys()`: returns an iterable (`dict_keys([.,.,.])`) containing keys only
- `.values()`: return an iterable (`dict_values([.,.,.])`) containing values only
- `.pop(<key>)`: removes the item with the specified `<key>` from the dictionary, and, also returns the value associated with the `<key>`
  - poping non-existing key raises `KeyError`.
- `.popitem()`: remove the last item from the dictionary and returns the item
  - popping an empty dictionary raises `KeyError`
- `.copy()`: shallow copy (only a new reference)
- `.get(<key>, default=None)`: returns the value associated with `key` if it exists, otherwise `None` or `<default>` value (if passed)
- `.setdefault(<key>, default=None)`: if `<key>` in dict, return it, otherwise add a new item and return the `<default>` value
- `.clear()`: remove all items from dictionary
- `.fromkeys(iterable, value=None)`: create a new dict when keys from iterable and values set to value
- `.items()`: returns an iterable containing tuples of key-value pair (iterable of items)
  - used in for loops:

  ```py
  for k, v in users.items():
      print(k, v)
  ```
- `.update(<somedict>)`: modify, update or expand dictionary
  ```py
  user.update({3: 'Mario', 4: 'Luigi', 5: 'James'})
  #or
  users = users | {3: 'Mario', 4: 'Luigi', 5: 'James'}
  #or even
  users |= {3: 'Mario', 4: 'Luigi', 5: 'James'}
  ```
