<template></template>
<script>
var sortColors = function (nums) {
  // 定义左右指针和判定指针
  let l = -1;
  let r = nums.length;
  let i = 0;

  while (i < r) {
    // 将遇到的0都移动到数组的最左侧
    if (nums[i] === 0) {
      let mid = nums[i];
      nums[i] = nums[l + 1];
      nums[l + 1] = mid;
      l++;
      i++;
    }
    // 遇到1时不需要做任何操作，移动当前判定指针即可
    if (nums[i] === 1) {
      i++;
    }
    // 将遇到的2都移动到数组的最右侧
    if (nums[i] === 2) {
      // 右侧有已经移动过去的2的部分，交换这部分的前一个位置
      // 判定指针已经达到全部是2的部分的时候不需要继续循环了，直接返回
      r--;
      if (i >= r) {
        return nums;
      }
      let mid = nums[i];
      nums[i] = nums[r];
      nums[r] = mid;
    }
  }
};
console.log(sortColors([2,0,2,1,1,0]));
</script>
