title: Updating ndarray
--- |
  Updating `ndarray` slices is very similar to updating `list` slices in Python. Here is an example:

---
type: live-code
code: |
  import numpy as np

  a = np.array([0, 1, 2, 3, 4, 5])
  a[2] = 20
  a

--- |

  We can also update a slice of the `ndarray` (just like `list`):

---
type: live-code
code: |
  import numpy as np

  a = np.array([0, 1, 2, 3, 4, 5])
  a[1:3] = [10, 20]
  a

--- |

  We can also use array-based indexing while updating `ndarray` slice:

---
type: live-code
code: |
  import numpy as np

  a = np.array([0, 1, 2, 3, 4, 5])
  a[ [1, 3, 5] ] = [10, 30, 50]
  a

--- |

  Boolean indexing also works as we would expect it:

---
type: live-code
code: |
  import numpy as np

  a = np.array([0, 1, 2, 3, 4, 5])
  a[ a%2 == 0 ] = [0, 20, 40]
  a

--- |
  You can also throw-in broadcasting and it would give you the expected results.

---
type: live-code
code: |
  import numpy as np

  a = np.array([0, 1, 2, 3, 4, 5])

  # Set all odd numbers to -1.
  a[ a%2 == 1 ] = -1
  a

---
type: coding-question
question: In the given code, update array `a` to set all even numbers to `99`.
code: |
  import numpy as np

  # Generate 10 random numbers between 0 - 100.
  a = np.random.randint(0, 100, 10)

  # your code goes here.
tests: |
  # No more even numbers in the array.
  assert a[ a%2 == 0 ].shape == (0,)
solution: |
  a[ a%2 == 0 ] = 99

---
type: coding-question
question: In the given code, update array `a` to set all negative numbers to `0`.
code: |
  import numpy as np

  # Generate 10 random numbers between -100 to 100.
  a = np.random.randint(-100, 100, 10)

  # your code goes here.
tests: |
  # No more negative numbers in the array.
  assert a[ a < 0 ].shape == (0,)
solution: |
  a[ a < 0 ] = 0
