# My solutions of different js problems

## Contents

* [Snail](#rotate-matrix-to-the-right-table-of-contents)
* [Rotate matrix to the right](#rotate-matrix-to-the-right-table-of-contents)
* [Rotate matrix to the left](#rotate-matrix-to-the-left-table-of-contents)

### Snail ([Table of Contents](#contents))

Given an n x m array, return the array elements arranged from outermost elements to the middle element, traveling clockwise.
<img width="220" alt="image" src="https://github.com/nat-davydova/solving-js-problems/assets/52240221/f83f4c0d-ffd0-4ce0-bfb1-d3e061bf92e8">

<details>
  <summary>Solution</summary>

  Let's say we have such a matrix:

  ```js
    const matrix = [
      [1, 2, 3, 4],
      [5, 6, 7, 8],
      [9, 10, 11, 12],
      [13, 14, 15, 16]
    ]
  ```

  We can split the snail's travel to circles, like that:

  <img width="276" alt="image" src="https://github.com/nat-davydova/solving-js-problems/assets/52240221/8b6c840e-5a3d-4832-b299-7cfc71720068">

  Here we have 2 circles: outer and inner. If the matrix will be bigger it will still have such a circles system:

  <img width="393" alt="image" src="https://github.com/nat-davydova/solving-js-problems/assets/52240221/8bc583bb-de77-4a35-a03c-db5ad0efe5af">

  We can split each circle in 4 parts: top side, right side, bottom side and left side. When we complete a part, we can remove it from the matrix, and do it again and again until the matrix become empty:

  <img width="1279" alt="image" src="https://github.com/nat-davydova/solving-js-problems/assets/52240221/7c753a12-8e02-467d-a3b7-1f99cf1c3845">

</details>

### Rotate matrix to the right ([Table of Contents](#contents))

### Rotate matrix to the left ([Table of Contents](#contents))
