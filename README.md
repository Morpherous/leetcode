---
description: 因为超过数组的一半，要不是1x1x1,要不就是111xx或者1x11x etc
---

# 169. Majority Element

```java
class Solution {
    public int majorityElement(int[] nums) {
        int major=nums[0],count=1;
        for(int i=1;i<nums.length;i++){
            if(count==0){
                major=nums[i];
                count+=1;
            }else if(nums[i]==major){
                count+=1;
            }else{
                count-=1;
            }
        }
        return major;
    }
}
```
