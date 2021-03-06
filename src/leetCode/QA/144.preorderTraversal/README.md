
## 二叉树的前序遍历
> 给定一个二叉树，返回它的 前序 遍历。



### 示例
> 输入: [1,null,2,3]          
> 输出: [1,2,3]   




### 树结构
```javascript 1.8
function TreeNode(val) {
    this.val = val;
    this.left = this.right = null;
}
```

### 递归解法
```javascript 1.8
let helper = function (root,res) {
    if(!root){
        return ;
    }
    res.push(root.val);
    helper(root.left,res);
    helper(root.right,res);
};


let preorderTraversal = function(root) {
    let res = [];
    helper(root,res);
    return res;
};
```

### 调用栈解法
```javascript 1.8
let preorderTraversal = function (root) {
    if(!root){
        return [];
    }
    let res = [];
    let list = [root];
    while (list.length){
        let cur = list.pop();
        res.push(cur.val);
        if(cur.right){
            list.push(cur.right)
        }
        if(cur.left){
            list.push(cur.left)
        }
    }
    return res;
};
```
 