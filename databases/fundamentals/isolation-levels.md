# Time Complexity

## Order-of-growth classifications
Name | Running time (T(n))
--- | ---
constant | O(1)
logarithmic | O(log n)
linear | O(n)
quasilinear | O(n log n)
quadratic | O(n^2)
cubic | O(n^3)
exponential (with linear exponent) | 2^O(n)
factorial | O(n!)

## Typical code
### Constant
#### Code example
```java
// Functionality: add two number
// Method: statement
a = b + c
```

#### Logarithmic
```java
// Functionality: binary search
// Method: divide in half
    public static int binarySearch(int key, int[] array) {
        int low = 0;
        int high = array.length - 1;
        while (low <= high) {
            int mid = low + (high - low) / 2;
            if (key < array[mid]) {
                high = mid - 1;
            } else if (key > array[mid]) {
                low = mid + 1;
            } else {
                return mid;
            }
        }
        return -1;
    }
```

#### Linear
```java
// Functionality: find the maximum
// Method: loop
    double max = a[0];
    for (int i = 1; i < N; i++)
        if (a[i] > max) max = a[i];
```

#### Quasilinear
```java
// Functionality: merge sort
// Method: divide and conquer
```

#### Quadratic
```java
// Functionality: check all pairs
// method: double loop
    for (int i = 0; i < N; i++)
        for (int j = i+1; j < N; j++)
            if (a[i] + a[j] == 0)
                count++;
```

#### Cubic
```java
// Functionality: check all triples
// Method: triple loop
    for (int i = 0; i < N; i++)
        for (int j = i+1; j < N; j++)
            for (int k = j+1; k < N; k++)
                if (a[i] + a[j] + a[k] == 0)
                    count++;
```

#### Exponential
```java
// Functionality: check all subsets
// Method: exhasutive search
```

#### Factorial
```java
// Functionality: 
// Method: 
```

## References

> 1. https://en.wikipedia.org/wiki/Time_complexity
> 2. Algorithms 4th Edition - Page 187