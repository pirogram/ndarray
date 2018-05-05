title: Create ndarray
--- |

  Let's start with a couple of examples in the context of 1D arrays. That would help us get going.

  Create an `ndarray` from the list `[1, 2, 3]`

---
type: live-code
code: |
  import numpy as np

  a = np.array([1, 2, 3])
  a

--- |

  Create an `ndarray` of a specific data type.

---
type: live-code
code: |
  import numpy as np

  # As float64
  a1 = np.array([1, 2, 3], np.float64)
  print("float64 array:", a1)

  # As unicode string of 8 bytes
  a2 = np.array([1,2,3], "U8")
  print("string array:", a2)

--- |

  `ndarray` can be indexed or sliced just like regular `array` in Python. The slices are, of course, `ndarray`.

---
type: live-code
code: |
  import numpy as np

  # Create an array of 10 random numbers between 1 to 100.
  a = np.random.randint(low=1, high=100, size=10)

  print("Generated array:", a)
  print("Element at index 3:", a[3])
  print("Slice 4 to 7:", a[4:7])

  # You can also specify an array as indexes
  print("Array based indexing ([1,4,7]):", a[[1, 4, 7]])

--- |

  A 2-dimensional array is just a 1-dimensional array of 1-dimensional arrays (basically, an array of arrays).

---
type: live-code
code: |
  import numpy as np

  one_d_arr = np.array([0, 1, 2])
  print("1d array:", one_d_arr)

  two_d_arr = np.array([
      [0, 1, 2],
      [3, 4, 5]
  ])
  print("2d array:", two_d_arr)

--- |

  N-dimensional array is an array of array of array of array ... (upto N levels). So, a 2-dimensional array is an `array of array`. A 3-dimensional array is an `array of an array of an array`. A 4-dimensional array is an ... (you got the idea. right?).

---
type: live-code
code: |
  import numpy as np

  # 2-d array (array of array)
  two_d_arr = np.array([
      [0, 1, 2],
      [3, 4, 5]
  ])
  print("2d array:", two_d_arr)

  # 3-d array (array of array of array)
  three_d_arr = np.array([[
      [0, 1, 2],
      [3, 4, 5]
    ],[
      [6, 7, 8],
      [9, 10, 11]
  ]])
  print("3d array:", three_d_arr)
