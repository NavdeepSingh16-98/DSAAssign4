# DSAAssign4

# Q1

```
function arraysIntersection(arr1, arr2, arr3) {
    let i = 0;
    let j = 0;
    let k = 0;
    const result = [];
    
    while (i < arr1.length && j < arr2.length && k < arr3.length) {
        const num1 = arr1[i];
        const num2 = arr2[j];
        const num3 = arr3[k];
        
        if (num1 === num2 && num2 === num3) {
            result.push(num1);
            i++;
            j++;
            k++;
        } else {
            if (num1 <= num2 && num1 <= num3) {
                i++;
            } else if (num2 <= num1 && num2 <= num3) {
                j++;
            } else {
                k++;
            }
        }
    }
    
    return result;
}

```

# Q2

```

function findDisappearedNumbers(nums1, nums2) {
    const set1 = new Set(nums1);
    const set2 = new Set(nums2);
    const result = [];
    
    for (let num of nums1) {
        if (!set2.has(num)) {
            result.push(num);
        }
    }
    
    for (let num of nums2) {
        if (!set1.has(num)) {
            result.push(num);
        }
    }
    
    return [result, result.reverse()];
}

```

# Q3

```
function transpose(matrix) {
    const rows = matrix.length;
    const cols = matrix[0].length;
    const result = [];
    
    for (let j = 0; j < cols; j++) {
        const newRow = [];
        
        for (let i = 0; i < rows; i++) {
            newRow.push(matrix[i][j]);
        }
        
        result.push(newRow);
    }
    
    return result;
}

```

# Q4

```
function arrayPairSum(nums) {
    nums.sort((a, b) => a - b);
    let sum = 0;
    
    for (let i = 0; i < nums.length; i += 2) {
        sum += nums[i];
    }
    
    return sum;
}

```

# Q5

```
function arrangeCoins(n) {
    let left = 0;
    let right = n;
    
    while (left <= right) {
        const mid = Math.floor((left + right) / 2);
        const totalCoins = (mid * (mid + 1)) / 2;
        
        if (totalCoins === n) {
            return mid;
        } else if (totalCoins < n) {
            left = mid + 1;
        } else {
            right = mid - 1;
        }
    }
    
    return right;
}


```

# Q6

```
function sortedSquares(nums) {
    return nums.map(num => num * num).sort((a, b) => a - b);
}

```

# Q7

```
function maxCount(m, n, ops) {
    let minRow = m;
    let minCol = n;
    
    for (let [row, col] of ops) {
        minRow = Math.min(minRow, row);
        minCol = Math.min(minCol, col);
    }
    
    return minRow * minCol;
}

```

# Q8

```
function shuffle(nums, n) {
    const result = [];
    
    for (let i = 0; i < n; i++) {
        result.push(nums[i], nums[i + n]);
    }
    
    return result;
}

```



