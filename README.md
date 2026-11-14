# Construct-Uniform-Parity-Array-I
class Solution:
    def uniformArray(self, nums1: list[int]) -> bool:
        n=len(nums1)
        nums2=[0]*n
        for i in range(n):
            if nums1[i]%2==0:
                nums2[i]=nums1[i]
            else:
                for j in range(n):
                    if i!=j and nums1[j]%2==1:
                        nums2[i]=nums1[i]-nums1[j]
                        break
                if nums2[i]%2!=0:
                    return False
        for i in nums2:
            if i%2!=0:
                return False
        return True
