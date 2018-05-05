title: Boolean Indexing
--- |

  Early on, we had reviewed a few methods of indexing `ndarray`. In this topic, we'll work on another very powerful method called _boolean indexing_. However, before we dive into _boolean indexing_, let's review the methods that we already talked about.

  Let's first create an array of numbers 0-9 that we'd use for illustration.

---
type: live-code
code: |
  import numpy as np

  a = np.arange(10)
  a

--- |
  First, let's review the index number based. This is the most familiar form of indexing.

---
type: live-code
code: |
  a[1]

--- |
  Next, let's review the range based slicing. This is very Pythonic but within the Python language, it's a very common way to slice sequences.

---
type: live-code
code: |
  # Elements from index 1 to 4.
  a[1:5]

--- |
  We also looked at array based slicing earlier. This is `ndarray` specific feature and not something that Python's inbuilt sequence data structures support.

---
type: live-code
code: |
  # Elements at index 1, 3 and 7.
  a[ [1, 3, 7] ]

--- |

  Now, we are ready to look at another method of indexing/slicing `ndarray` and it's called _boolean indexing_. For this, we take an array of boolean values (`True` or `False`) and use that as index. The length of boolean array must be same as the length of array being indexed.

  Let's first look at an example followed by an illustration.

---
type: live-code
code: |
  # define an array of boolean values whose length is same as the length of
  # array being indexed. In this case, it is 10.
  index = [True, True, False, False, True, True, False, False, True, True]

  # Index our original array.
  a[index]

--- |

  Here is an illustration of this operation to develop visual intuition about this.

  ![](assets/img/boolean-indexing.png)
