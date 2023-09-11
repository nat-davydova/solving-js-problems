# Solves of different js problems

## Contents

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

#### Solution

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
