title: ndarray Reshaping
--- |

  To understand the concept of reshaping, we'll first develop a visual intuition for reshaping followed by the actual code for reshaping.

  Let's consider a 1-d array of 8 elements. This is how it would look like (conceptually as well as in memory):

  ![](assets/img/one-d-reshaping.png)

  The same data could also be represented in a `(2, 4)` shape:

  ![](assets/img/one-d-reshaping-to-42.png)

  It could also be represented in a `(2, 2, 2)` shape:

  ![](assets/img/one-d-reshaping-to-222.png)

  As you would see, the dataset continues to have 8 elements and it continues to be laid out exactly in the same way but it could be morphed into different shapes (`(8,)`, `(2, 4)` and `(2, 2, 2)` respectively).

  Here is the corresponding `ndarray` code that does the job:

---
type: live-code
code: |
  import numpy as np

  a_8 = np.array([1, 2, 3, 4, 5, 6, 7, 8])
  print("Shape (8,):", a_8)

---
type: live-code
code: |
  # Reshape to (2, 4)

  a_8.reshape(2, 4)

---
type: live-code
code: |
  # Reshape to (2, 2, 2)

  a_8.reshape(2, 2, 2)

---
type: live-code
code: |
  # Reshaping works in both the directions

  a_8.reshape(2, 2, 2).reshape(8)

---
type: coding-question
question: |
  Reshape the array `a` to shape `(2, 4)`
code: |
  import numpy as np
  a = np.arange(8)
solution: |
  import numpy as np
  a = np.arange(8).reshape(2, 4)
tests:
  assert a.shape == (2, 4)
