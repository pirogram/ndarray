title: Memory Layout
--- |

  Before we get into the usefulness of n-dimensional array, let's understand this data structure better. As next step, we'll look into how n-dimensional array is laid out in memory. Here is an illustration from our temperature dataset example:

  ![](assets/img/three-d-layout.png)

  Leftmost, we have the code representation of our dataset. In the center, we have the same dataset represented in n-dimensional model. On the rightmost, we have the illustration of how this dataset is laid out in memory.

  Interesting thing is that the data is laid out in contagious memory block. However, we have the ability to slice and dice the data as we wish. For example, let's say, we want to pick all the readings from station 1 (across all three sensors). This is how we could visualize our data.

  ![](assets/img/three-d-station-1.png)

  As you would notice, there is a pattern here. Even though all the readings are laid out in a single contagious memory block, you can hop through it and pick all data from station 1.

  What if you want all the readings generated at 6AM? Here is a visual for the same:

  ![](assets/img/three-d-6-am.png)

  What if you want all readings of 1st sensor across all stations all hours? Here is a visual for that.

  ![](assets/img/three-d-sensor-1.png)

  Later, we'll look at the syntax and code samples for actual slicing operations. The objective here is to create a visual intuition for n-dimensional data structure (`ndarray`).
