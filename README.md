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

  The simpliciest part is to grab the **top side**, push it's elements into result and remove the line:

  <img width="270" alt="image" src="https://github.com/nat-davydova/solving-js-problems/assets/52240221/d423b4f5-942d-40b8-bc51-873f8e748fc5">

  ```js
  matrix[0].forEach(elem => result.push(elem));
  matrix.shift();
  ```

  Now we need **right side**. To map through each row we have and to get the last elem of every row, than - delete it:

  <img width="274" alt="image" src="https://github.com/nat-davydova/solving-js-problems/assets/52240221/c08018ec-e234-44e0-878c-3a0c06b340b7">

  ```js
  matrix.forEach(row => {
      result.push(row[row.length - 1]);
      row.pop();
  })
  ```

  **Bottom side** is a bit trickier: the last row elements should be grabbed from the right to the left:

  <img width="233" alt="image" src="https://github.com/nat-davydova/solving-js-problems/assets/52240221/0cc71a03-741e-42fc-8710-5c9a124467fa">

  ```js
  const bottomRow = matrix[matrix.length - 1]; // can be 'undefined' if the matrix is empty on this stage
    for (let i = bottomRow?.length - 1; i >= 0; i--) {
      result.push(bottomRow[i]);
    }
    matrix.pop();
  ```

  The last part of the circle - **left side**. Here we loop through all the rows from bottom to top and grab evary first row item:

  <img width="202" alt="image" src="https://github.com/nat-davydova/solving-js-problems/assets/52240221/69ac1fc9-da7a-43b5-87d0-046b44fd5cea">

  ```js
    for (let i = matrix.length - 1; i >= 0; i--) {
      const row = matrix[i];
      result.push(row[0]);
      row.shift();
    }
  ```

  And then if there are any more rows in the matrix, we start a new circle.

  ```js
  function snail(matrix) {
    const result = [];

    // while we have non-empty rows
    while(matrix.length > 0) {
      // top side
      matrix[0].forEach(elem => result.push(elem));
      matrix.shift();
  
      // right side
      matrix.forEach(row => {
        result.push(row[row.length - 1]);
        row.pop();
      })
  
      //bottom side
      const bottomRow = matrix[matrix.length - 1];
      for (let i = bottomRow?.length - 1; i >= 0; i--) {
        result.push(bottomRow[i]);
      }
      matrix.pop();
  
      //left side
      for (let i = matrix.length - 1; i >= 0; i--) {
        const row = matrix[i];
        result.push(row[0]);
        row.shift();
      }
    }
  
    return result;
  }
  ```
</details>

### Rotate matrix to the right ([Table of Contents](#contents))

### Rotate matrix to the left ([Table of Contents](#contents))
