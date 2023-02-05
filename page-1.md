---
description: 从小到大排列第k个
---

# 230. Kth Smallest Element in a BST

```java
class Solution {
    int cnt=0, res=0;
    public int kthSmallest(TreeNode root, int k) {
        inorder(root,k);
        return res;
    }
    public void inorder(TreeNode root,int k){
        if(root==null){return;}
        inorder(root.left,k);
        cnt+=1;
        if(cnt==k){
            res=root.val;
            return;
        }
        inorder(root.right,k);
    }
}
```

<pre class="language-java"><code class="lang-java"><strong>class Solution {
</strong>    public List&#x3C;Integer>ans=new ArrayList&#x3C;>();
    public int kthSmallest(TreeNode root, int k) {
        inorder(root,k);
        int res=ans.get(k-1);
        return res;
    }
    public void inorder(TreeNode root,int k){
        if(root==null){return;}
        inorder(root.left,k);
        ans.add(root.val);
        inorder(root.right,k);
    }
}
</code></pre>
