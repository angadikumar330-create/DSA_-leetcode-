class Solution:
    def minSwaps(self, grid):
        n = len(grid)
        arr = [0] * n

        # count trailing zeros
        for i in range(n):
            streak = 0
            for j in range(n - 1, -1, -1):
                if grid[i][j] == 0:
                    streak += 1
                else:
                    break
            arr[i] = streak

        steps = 0

        for i in range(n):
            # For row i to be valid, it must have at least (n - i - 1) zeros at the end
            # Example: first row needs n-1 zeros, second row needs n-2 zeros, etc.
            need = n - i - 1

            # Start checking from the current row
            j = i

            # Move downward to find a row that has enough trailing zeros
            # Keep going until we either find a valid row or reach the end
            while j < n and arr[j] < need:
                j += 1

            # If we reached the end and still didn't find a valid row,
            # it means no row below can satisfy this requirement
            # So making the grid valid is impossible
            if j == n:
                return -1

            # Option 1: Simulation
            # If we found a valid row at position j,
            # move it up to position i using adjacent swaps
            # (since only neighboring rows can be swapped)
            while j > i:
                arr[j], arr[j - 1] = arr[j - 1], arr[j]
                steps += 1   # count this swap
                j -= 1       # keep moving the row upward

#----------------------------------------

            # Option 2: Instead of performing swaps,
            # count how many positions the row must move upward.
            # Remove the element at index j and insert it at index i.
            steps += j - i
            val = arr.pop(j)
            arr.insert(i, val)

#--- note: comment out one of the two options ---

        return steps
