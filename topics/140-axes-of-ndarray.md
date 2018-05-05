title: Axes of ndarray
--- |

  `Dimensions` and `axes` mean the same thing in context of `ndarray`. It's just that the `NumPy` code has used different terms in different places. So far, we used the term `dimension` wherever we needed to. However, we'll now introduce the term `axes` since some of the `ndarray` methods use the term `axes` instead of `dimension`.

  Anyway, here is an array of 1 `axis` (aka 1 `dimension`):

  ```python
  a = np.array([0, 1, 2])
  ```

  Here is an array of 2 `axes` (aka 2 `dimensions`):

  ```python
  a = np.array([
    [0, 1, 2],
    [3, 4, 5]
  ])
  ```

  While we refer to `dimensions` only in the sense of _"how many total dimensions are there in the array?"_. However, we the `axes` are numbered. Here is an illustration of how the axes are numbered:

  ![](assets/img/axis.png)

  So, why is it relevant? Let's understand this through an example.

  Let's take a hypothetical dataset of tomato prices. On a given day, we did a survey of tomato prices in four grocery stores in our city. We found the tomato prices to be `$1.2`, `$1.1`, `$1.2`, `$1.3` per pound. We can find the `mean` price of tomatoes across all grocery stores as follows:

---
type: live-code
code: |
  import numpy as np

  prices = np.array([1.2, 1.1, 1.2, 1.3])
  mean_price = np.mean(prices)
  mean_price

--- |

  Now, let's say, we decided to monitor the tomato prices for a week. We can represent that as an array of shape `(7, 4)` (i.e. 7 days and 4 grocery stores). It could look like the following:

---
type: live-code
code: |
  import numpy as np

  prices_for_week = np.array([
    [1.2, 1.1, 1.2, 1.3],
    [1.2, 1.1, 1.2, 1.3],
    [1.1, 1.0, 1.2, 1.2],
    [1.0, 1.1, 1.3, 1.4],
    [1.0, 1.2, 1.1, 1.2],
    [1.2, 1.1, 1.2, 1.3],
    [1.2, 1.1, 1.2, 1.3]
  ])

--- |

  We can still find out the `mean` price across our dataset with `np.mean()` function:

---
type: live-code
code: |
  np.mean(prices_for_week)

--- |

  What if we want to find out the average weekly price for each grocery store separately? We can run the `np.mean()` method along `axis 0`:

---
type: live-code
code: |
  np.mean(prices_for_week, axis=0)

--- |
  This would give us the weekly prices for each grocery store separately. Here is how you can visualize the two axis of this array. Axis 0 cuts across the columns and performing a group operation along axis 0 would perform the operation column wise.

  ![](assets/img/tomato-price.png)

  What if we want to find out the average price for each day?

---
type: live-code
code: |
  np.mean(prices_for_week, axis=1)
