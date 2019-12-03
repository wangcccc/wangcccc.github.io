# wangcccc.github.io
[testlink](a/a.md)
## Two sum
Given an array of integers, return indices of the two numbers such that they add up to a specific target.
You may assume that each input would have exactly one solution, and you may not use the same element twice.

```cpp
vector<int> twoSum(vector<int>& nums, int target) {
    unordered_map<int, int> dict;

    for (int i = 0; i < nums.size(); ++i) {
        auto pair = target - nums[i];
        if (dict.find(pair) != dict.end()) {
            return {dict[pair], i};
        }
        else {
            dict[nums[i]] = i;
        }
    }
    return {};
}
```
## Two sum
Given an array of integers, return indices of the two numbers such that they add up to a specific target.
You may assume that each input would have exactly one solution, and you may not use the same element twice.

```C++
vector<int> twoSum(vector<int>& nums, int target) {
    unordered_map<int, int> dict;

    for (int i = 0; i < nums.size(); ++i) {
        auto pair = target - nums[i];
        if (dict.find(pair) != dict.end()) {
            return {dict[pair], i};
        }
        else {
            dict[nums[i]] = i;
        }
    }
    return {};
}
```
