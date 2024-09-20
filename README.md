# Find-the-max-X

Ninu gives an array A with N elements to Yash. Yash's task is to find the maximum non-negative integer X such that:
No element in the array belongs to the range [−X, X]. In other words, for all (1 ≤ i ≤ N), either Ai​< -X or Ai​ > X.
Help Yash to find the maximum non-negative integer X for which the given condition is satisfied or determine if no such X exists.

def find_max_x(N, A):
    min_abs_value = float('inf')
    
    for a in A:
        min_abs_value = min(min_abs_value, abs(a))
    
    if min_abs_value == 0:
        return -1
    
    return min_abs_value - 1

import sys
input = sys.stdin.read
data = input().split()

t = int(data[0])
index = 1
results = []

for _ in range(t):
    n = int(data[index])
    A = list(map(int, data[index + 1: index + 1 + n]))
    index += n + 1
    
    results.append(str(find_max_x(n, A)))

sys.stdout.write("\n".join(results) + "\n")
