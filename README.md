# Solutions of different js problems

## Contents

* [Rotate matrix to the right](#rotate-matrix-to-the-right-table-of-contents)
* [Rotate matrix to the left](#rotate-matrix-to-the-left-table-of-contents)
* [Mirror the matrix horizontally](#mirror-the-matrix-horizontally-table-of-contents)

### Rotate matrix to the right([Table of Contents](#contents))

#### Example

```js
const matrix = [
  [1, 2, 3, 4],
  [5, 6, 7, 8],
  [9, 0, 1, 2],
];

rotateRight(matrix);
// [
//   [9, 5, 1],
//   [0, 6, 2],
//   [1, 7, 3],
//   [2, 8, 4],
// ]
```
#### Solution

<details>
  <summary>Solution</summary>
  <img width="719" alt="image" src="https://github.com/nat-davydova/solving-js-problems/assets/52240221/1477f356-7651-4d19-a6c2-9da3ee7e05f6">
  <img width="959" alt="image" src="https://github.com/nat-davydova/solving-js-problems/assets/52240221/a5eb04bb-6533-411c-a3eb-1922ede39506">

  ```js
    export function rotateRight(matrix) {
      const result = [];
    
      for (let i = 0; i < matrix.length; i++) {
        const line = matrix[i];
    
        for(let j = 0; j < line.length; j++) {
          if(!result[j]) {
            result.push([line[j]]);
          } else {
            result[j].unshift(line[j]);
          }
        }
      }
    
      return result;
  }
  ```
</details>

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

#### Solution

<details>
  <summary>Solution</summary>
  <img width="715" alt="image" src="https://github.com/nat-davydova/solving-js-problems/assets/52240221/5207bcfb-4c50-4465-a028-bc30397809c8">
  <img width="703" alt="image" src="https://github.com/nat-davydova/solving-js-problems/assets/52240221/fb63a0d9-291b-4012-9112-0b2c75ddf560">
  
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
