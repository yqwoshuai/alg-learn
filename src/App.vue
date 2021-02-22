<template></template>
<script>
var findLongestWord = function (s, d) {
  // 将传入的数组按字典序排序
  let arr = d.sort();
  // 分割传入的字符串为数组
  let sArr = s.split("");
  // 定义返回值
  let str = "";
  // 对匹配数组的每一项都进行遍历
  for (let i = 0; i < arr.length; i++) {
    // 将当前项拆分为数组，定义当前满足条件子字符串的长度k
    let item = arr[i].split("");
    let k = 0;
    // 对字符逐个匹配，匹配成功时k指针右移
    for (let p = 0; p < sArr.length; p++) {
      if (sArr[p] === item[k]) {
        k++;
      }
    }
    // k值等于当前单词的长度时表示当前单词匹配成功
    // 在大于之前匹配成功的单词长度时更新单词
    if (k === item.length && k > str.length) {
      str = arr[i];
    }
  }
  return str;
};
console.log(findLongestWord("abpcplea",["ale", "apple", "monkey", "plea"]));
</script>
