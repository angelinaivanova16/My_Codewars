# Minimize Sum Of Array (Array Series #1)
## DESCRIPTION:
Given an array of integers , Find the minimum sum which is obtained from summing each Two integers product .

Array/list will contain positives only.

Array/list will always have even size

minSum({5,4,2,3}) ==> return (22) 

`Explanation:`
The minimum sum obtained from summing each two integers product ,  5*2 + 3*4 = 22
## My solution:
```
function minSum(arr){
  return minSumRec(arr, 0)
}

function minSumRec(arr, result) {
  if (arr.length < 2) {
    return result
  } else {
    result += (Math.min.apply(null, arr) * Math.max.apply(null, arr));
    let min = arr.indexOf(Math.min.apply(null, arr));
    arr.splice(min, 1)
    let max = arr.indexOf(Math.max.apply(null, arr));
    arr.splice(max, 1)
    return minSumRec(arr, result)
  }
}
```
