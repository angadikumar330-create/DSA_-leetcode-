class Solution(object):
    def findMedianSortedArrays(self, nums1, nums2):
        nums=nums1+nums2
        nums.sort()
        k=len(nums)
        if k%2==1:
            return nums[k//2]
        return (nums[k//2] + nums[k//2 - 1])/2.0
