# Solves of different js problems

## Contents

* [Rotate matrix to the left](#rotate-matrix-to-the-left-table-of-contents)
* [Mirror the matrix horizontally](#mirror-the-matrix-horizontally-table-of-contents)

### Rotate matrix to the left([Table of Contents](#contents))

#### Example

```js
const matrix = [
  [1, 2, 3, 4],
  [5, 6, 7, 8],
  [9, 0, 1, 2],
];

rotateLeft(matrix);
// [
//   [4, 8, 2],
//   [3, 7, 1],
//   [2, 6, 0],
//   [1, 5, 9],
// ]
```

<img width="595" alt="image" src="https://github.com/nat-davydova/solving-js-problems/assets/52240221/38e78306-c72a-4135-b788-4c451cdf74ae">

#### Solution

<details>
  <summary>Solution (in progress)</summary>
  <img width="853" alt="image" src="https://github.com/nat-davydova/solving-js-problems/assets/52240221/69e43f0e-7dcb-47ea-8c45-258a3837d2a4">
  <img width="977" alt="image" src="https://github.com/nat-davydova/solving-js-problems/assets/52240221/28038185-acf3-4166-9206-b24a70dc210a">
  <img width="1140" alt="image" src="https://github.com/nat-davydova/solving-js-problems/assets/52240221/2506df2c-88aa-4f1a-a3ff-d0f8ac8dd584">
  ```js
  export function rotateLeft(matrix) {
  const result = [];

  for(let i = 0; i < matrix.length; i++) {
    const line = matrix[i];

    for (let j = line.length - 1; j >= 0; j--) {
      const newMatrixLineIndex = line.length - 1 - j;

      if (!result[newMatrixLineIndex]) {
        result.push([line[j]])
      } else {
        result[newMatrixLineIndex].push(line[j])
      }
      
    }
  }

  return result;
}
  ```
</details>

### Mirror the matrix horizontally([Table of Contents](#contents))

#### Example
```js
getMirrorMatrix([
  [11, 12, 13, 14],
  [21, 22, 23, 24],
  [31, 32, 33, 34],
  [41, 42, 43, 44],
]); 
=>
//  [
//     [11, 12, 12, 11],
//     [21, 22, 22, 21],
//     [31, 32, 32, 31],
//     [41, 42, 42, 41],
//  ]
```

#### Solution

<details>
<summary>Solution</summary>
<img width="1142" alt="image" src="https://github.com/nat-davydova/solving-js-problems/assets/52240221/fbbdda73-9a46-4aa3-a30d-2e3c5a69ca13">

```js
function getMirrorLine(line) {
  const mirroredLine = [];
  const lineSize = line.length;

  for (let i = 0; i < lineSize; i++) {
    if (i <= lineSize/2 - 1) {
      mirroredLine.push(line[i])
    } else {
      const mirroredElemIndex = lineSize - i - 1;
      mirroredLine.push(line[mirroredElemIndex]);
    }
  }

  return mirroredLine;
}

function getMirrorMatrix(arr) {
  const result = [];
  
  for(let i = 0; i < arr.length; i++) {
    const mirroredLine = getMirrorLine(arr[i]);
    result.push(mirroredLine);
  }

  return result;
}
```
</details>
