#### Two Sum 
```
use std::collections::HashMap;

impl Solution {
    pub fn two_sum(nums: Vec<i32>, target: i32) -> Vec<i32> {
        let mut map = HashMap::with_capacity(nums.len());
        for(index , num) in nums.into_iter().enumerate(){
            if map.contains_key(&num) {
                return vec![map[&num] as i32, index as i32];
            }
            else {
                map.insert(target-num, index);
            }
        }
        unreachable!();
    }
}
```
