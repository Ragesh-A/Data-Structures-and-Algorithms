## Questions

### Create a function that looks through an array arr and returns the first element in it that passes a 'truth test'. This means that given an element x, the 'truth test' is passed if `func(x)` is `true`. If no element passes the test, return `undefined`.

```js
function findElement(arr, func){
  return arr.find(num=> func(num))
}


const result = findElement([1, 3, 5, 8, 9, 10], num => num % 2 === 0 )
console.log(result)
```

### Remove all the falsy value from an array

```js
function bouncer(arr) {
  return arr.filter(ele=> {
    if(ele){
      return ele
    }
  });
}

console.log(bouncer([7, "ate", "", false, 9]))
```

### Return the lowest index at which a value (second argument) should be inserted into an array (first argument) once it has been sorted. The returned value should be a number.

```js
function getIndexToIns(arr, num) {
  arr.push(num);
  arr.sort(function(a, b) {
    return a - b;
  });
  return arr.indexOf(num);
}

const arr = [1,2,3,4,6,7]
console.log(`value will insert ${getIndexToIns(arr, 5)} th position`)
```

# Search algorithms

-> Linear search algorithm O(n) <br />
-> Binary Search algorithm O(log n) <br />

### Given an array of `n` elements and target element `t`, find the index of `t` in the array. Return `-1` if target element not found

<h3 align="center">Linear search</h3>

```js
const arr = [1, 7, 8, 92, 3, 4, 5, 6,];
const t = 92;
function linearSearch(arr, t) {
  for (let i = 0; i <= arr.length; i++) {
    if (arr[i] === t) {
      return i;
    }
  }
  return -1;
}
console.log(linearSearch(arr, t));
```
<h3 align="center">Binary search</h3>

### Given a sorted array of `n` elements and target element `t`, find the index of `t` in the array. Return `-1` if target element not found

```js
const arr = [1, 2, 3, 4, 5, 6, 7, 8, 9];
const t = 5;
function binarySearch(arr, t) {
  let l = 0;
  let r = arr.length - 1;
  let mid = Math.floor((r + l) / 2);

  while (l <= r) {
    if (arr[mid] === t) {
      return mid;
    } else if (t > arr[mid]) {
      l = mid + 1;
      mid = Math.floor((l + r) / 2);
    } else {
      r = mid - 1;
      mid = Math.floor((l + r) / 2);
    }
  }
  return -1;
}
console.log(binarySearch(arr, t));
```

# Sorting algorithms
-> Bubble sort.<br />
   compare the adjacent elements in the array and swap the position if they are not in order. check the element are in order other wise repeat the process.<br />
-> Insertion sort.<br />
    The array is virtually split into a sorted and an unsorted part. Values from the unsorted part are picked and placed at the correct position in the sorted part. <br />
-> Quick sort.<br />
-> Selection sort.<br />

 ### Given an array of integer sort it.

<h3 align="center">Bubble sort O(n^2)</h3>

```js
const arr = [-6, 20, 8, -2, 4];

function bubbleSort(arr) {
  for (let j = 0; j < arr.length - 1; j++) {
    for (let i = 0; i < arr.length; i++) {
      if (arr[i] > arr[i + 1]) {
        let temp = arr[i];
        arr[i] = arr[i + 1];
        arr[i + 1] = temp;
      }
    }
  }
  return arr;
}

console.log(bubbleSort(arr));

```
<h3 align="center">Insertion sort O(n^2)</h3>

```js
const arr = [-6, 20, 8, -2, 4];

function insertionSort(arr) {
  
  for(let i = 1; i < arr.length; i++){
      let NTI = arr[i]
      let j = i - 1;
      while( j >= 0 && arr[j] > NTI){
          arr[j + 1 ] = arr[j]
          j = j -1
      }
      arr[j+1] = NTI
  }
  
  
  return arr;
}

console.log(insertionSort(arr));
```
<h3 align="center">Quick sort O(n log n)</h3>

```js
const arr = [-6, 20, 8, -2, 4];

function quickSort(arr) {
  if (arr.length < 2) {
    return arr;
  }
  let p = arr[arr.length - 1];
  let l = [];
  let r = [];

  for (let i = 0; i < arr.length - 1; i++) {
    if (arr[i] < p) {
      l.push(arr[i]);
    } else {
      r.push(arr[i]);
    }
  }

  return [...quickSort(l), p, ...quickSort(r)];
}

console.log(quickSort(arr));
```

<h3 align="center">Merge sort O(n log n)</h3>

```js
const arr = [-6, 20, 8, -2, 4];

function mergeSort(arr) {
    
    if(arr.length < 2){
        return arr
    }
    
    let mid = Math.floor(arr.length/2)
    let left = arr.slice(0, mid)
    let right = arr.slice(mid)
    return merge(mergeSort(left),mergeSort(right))

}

function merge(left, right){
    let sorted = []
    while(left.length && right.length){
        if(left[0]<=right[0]){
            sorted.push(left.shift())
        }else{
            sorted.push(right.shift())
        }
    }
    return [...sorted,...left,...right]
    
}

console.log(mergeSort(arr));
```
### flatten the array

```js
function flat(arr ){
  let flatten = []
  const length = arr.length
  for(let i =0; i < length; i++){
    if(Array.isArray(arr[i])){
     flatten = flatten.concat(flat(arr[i]))
    }else{
      flatten.push(arr[i])
    }
  }
  return flatten;
}
const arr = [1,2,[3,4,5],[6,[7,8,[9]]]]
const flattened =flat(arr)
console.log(flattened)

```