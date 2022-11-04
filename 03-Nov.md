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
### Best time to buy and sell stock 
```
impl Solution {
    pub fn max_profit(prices: Vec<i32>) -> i32 {
        use std::cmp::{min, max};
        let mut mx = 0;
        let mut b = std::i32::MAX;
        for value in prices.iter() {
            mx = max(mx, value - b);
            b = min(b, *value);
        }
        mx
    }
}
```
