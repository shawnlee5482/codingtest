# Quick Sort

```
var arr = [1, -1, 2, -5, 6, 7];
var n= 6;
// var n = 100;

// function random_generate() {
//   arr = [];
//   for(var i = 0; i < n; i++) {
//     arr.push(Math.floor(Math.random() * n));
//   }
// }

function swap(i, j) {
  var temp;
  temp = arr[i];
  arr[i] = arr[j];
  arr[j] = temp;
}

function partition_left(left, right) {
  // set pivot as the first item
  var pivot_value = arr[left];
  var i = right; 
  // compare with pivot from the right
  for(var j = right; j > left; j--) {
    // if there is an item larger than pivot
    // move to the right slot (i is for the slot to move)
    if(arr[j] >= pivot_value) {
      // move first
      swap(i, j);
      // decrease slot
      i--;
    }
  }
  // i is 1 less than the position of the last value larger than pivot value
  // so, if we swap left with i, pivot will be in i
  // return i
  swap(i, left);
  return i;
}

function partition_right(left, right) {
  var pivot_value = arr[right];
  var i = left;
  for(var j = left; j < right; j++) {
    if(arr[j] <= pivot_value) {
      swap(i, j);
      i++;
    }
  }
  swap(i, right);
  return i;
}

function quick_sort(left, right) {
  if(left < right) {
    var p = partition_left(left, right);
    quick_sort(left, p-1);
    quick_sort(p+1, right);
  }
}

//random_generate();
console.log(new Date());
quick_sort(0, arr.length - 1);
console.log(arr);
console.log(new Date());


// random_generate();
// console.log(new Date());
// arr.sort();
// console.log(new Date());
```
