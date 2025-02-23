# 99-tech-problem-4
```typescript
  // Complexity: O(1)
  const sum_to_n_a = (n: number) => {
    return (n * (n + 1)) / 2;
  }

  // Complexity: O(logn) => Each step reduces the number of elements by half
  // let n = 5;
  // let numbers = Array.from({ length: n }, (_, i) => i + 1);
  // console.log(parallelSum(numbers));
  const sum_to_n_b = (arr: number[]) => {
    while (arr.length > 1) {
      let newArr = [];
      for (let i = 0; i < arr.length; i += 2) {
        newArr.push((arr[i] || 0) + (arr[i + 1] || 0));
      }
      arr = newArr;
    }
    return arr[0] || 0;
  }

  // Complexity: O(1)
  // In problems where a formula is not available and the calculation is complex, this approach can be a good choice
  // pros: Consumes extra memory.
  const sumLookup = new Map();
  const sum_to_n_c = (n: number) => {
    if (sumLookup.has(n)) return sumLookup.get(n);
    let sum = (n * (n + 1)) / 2;
    sumLookup.set(n, sum);
    return sum;
  }
```
