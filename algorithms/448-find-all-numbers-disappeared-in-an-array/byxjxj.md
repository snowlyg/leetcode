```golang
func findDisappearedNumbers(nums []int) []int {
    
    for i := range nums {
        for nums[i] != nums[nums[i]-1] {
            nums[i], nums[nums[i]-1] = nums[nums[i]-1], nums[i]
        }
    }
    
    res := make([]int, 0, len(nums))
    
    for i, v := range nums {
        if i+1 != v {
            res = append(res, i+1)
        }
    }
    
    return res
}
```
