class Solution(object):
    def bitwiseComplement(self, n):
        if n == 0:
            return 1
        if n == 1:
            return 0
        
        ans = 0
        cnt = 0
        
        while n > 0:
            if n % 2 == 0 and n // 2 != 0:
                ans += 2 ** cnt
            cnt += 1
            n //= 2
        
        return ans
