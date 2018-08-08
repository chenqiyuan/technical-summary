
## 寻找旋转排序数组中的最小值
> 假设按照升序排序的数组在预先未知的某个点上进行了旋转。                      
> ( 例如，数组 [0,1,2,4,5,6,7] 可能变为 [4,5,6,7,0,1,2] )。                     
> 请找出其中最小的元素。                          
> 你可以假设数组中不存在重复元素。                     



### 示例 1
> 输入: [3,4,5,1,2]     
> 输出: 1

### 示例 2
> 输入: [4,5,6,7,0,1,2]       
> 输出: 0



### 解法
```javascript 1.8
let findMin = function (nums) {
    let len = nums.length;
    let left = 0,right = len - 1;
    //排除数组个数为一，或未旋转的情况
    if(nums[left] <= nums[right]){
        return nums[0];
    }
    //找到旋转的位置
    while (right - left > 1){
        let mid = ~~((left + right)/2),
            midVal = nums[mid];
        if(nums[left] < midVal){
            left = mid;
        }else if(midVal < nums[right]){
            right = mid;
        }
    }
    return nums[right];
};
```