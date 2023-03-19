# CMPS 2200 Reciation 5
## Answers

**Name:**___Sam DeMarinis & Zoe Oboler______________________


Place all written answers from `recitation-06.md` here for easier grading.







- **1b.**

- Unsorted List:
|     n |   qsort-fixed-pivot |   qsort-random-pivot |   tim_sort |    ssort |
|-------|---------------------|----------------------|------------|----------|
|    10 |               0.001 |                0.044 |      0.006 |    0.022 |
|    20 |               0.001 |                0.003 |      0.002 |    0.035 |
|    50 |               0.001 |                0.002 |      0.006 |    0.152 |
|   100 |               0.001 |                0.003 |      0.014 |    0.498 |
|   200 |               0.001 |                0.003 |      0.026 |    1.973 |
|   500 |               0.001 |                0.005 |      0.095 |   10.239 |
|  1000 |               0.001 |                0.004 |      0.155 |   97.755 |
|  2000 |               0.002 |                0.005 |      0.331 |  365.794 |
|  5000 |               0.002 |                0.006 |      6.105 | 1892.900 |
| 10000 |               0.003 |                0.005 |      2.195 | 8582.826 |
- Sorted list 
|     n |   qsort-fixed-pivot |   qsort-random-pivot |   tim_sort |    ssort |
|-------|---------------------|----------------------|------------|----------|
|    10 |               0.002 |                0.008 |      0.003 |    0.019 |
|    20 |               0.001 |                0.003 |      0.002 |    0.044 |
|    50 |               0.001 |                0.003 |      0.003 |    0.114 |
|   100 |               0.000 |                0.003 |      0.003 |    0.318 |
|   200 |               0.000 |                0.002 |      0.004 |    2.409 |
|   500 |               0.001 |                0.005 |      0.010 |   11.798 |
|  1000 |               0.002 |                0.013 |      0.024 |   56.920 |
|  2000 |               0.002 |                0.013 |      0.116 |  222.436 |
|  5000 |               0.002 |                0.013 |      2.332 | 1345.324 |
| 10000 |               0.002 |                0.012 |      0.140 | 5278.129 |

No matter the variant of qsort, ssort has much higher runtime for all values of n. For both sorted and unosrted input lists ssort had a significantly longer runtime than any of the other formulas. However, ssort did perform better for every size of n when the list was sorted. The asymptotic upper bound of qsort is O(nlogn) and ssort is O(n^2).

Therefore at low values of n, such as n = 10, while ssort is slower, it is a somewhat marginal difference in runtime (for example 0.002 vs 0.019). However as n increases, because ssort has an exponential worst case runtime, for both sorted and unsorted lists the runtime is significantly longer than all the versions of qsort. Because of the nature of selection sort, whether or not the list is sorted, it must iterate through every item in the list. This is why we do not see significant improvement with the sorted list over the unsorted list.
- **1c.**

|      n |   qsort-fixed-pivot |   qsort-random-pivot |   tim_sort |
|--------|---------------------|----------------------|------------|
|    100 |               0.001 |                0.004 |      0.018 |
|    200 |               0.001 |                0.003 |      0.026 |
|    500 |               0.001 |                0.003 |      0.070 |
|   1000 |               0.001 |                0.003 |      0.159 |
|   2000 |               0.001 |                0.003 |      3.218 |
|   5000 |               0.002 |                0.005 |      1.194 |
|  10000 |               0.003 |                0.006 |      3.572 |
|  20000 |               0.003 |                0.006 |      5.888 |
|  50000 |               0.003 |                0.006 |     38.698 |
| 100000 |               0.002 |                0.006 |     33.340 |

Our fastest sorting algorithm is qsort-fixed-pivot. For each value of n, the runtime is smaller than that of tim_sort. 

Although both have 0(nlogn) worst case runtimes, in the majority of situations Qsort is faster when the list is completely randomized. Tim_sort relies on "natural runs" or sections of ordered data within the larger list/array. Because our data is completely randomized using random.shuffle(), quick sort is performing better. If our data was partially sorted, either on purpose or randomly, we would get a better runtime with tim_sort. Although we sometimes have slightly longer runtimes than qsort even with a presorted list, the values are significantly closer when the values are sorted.
  