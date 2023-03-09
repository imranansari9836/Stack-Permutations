# Stack-Permutations
#Stack Permutations
Input:
N = 3
A = {1,2,3}
B = {2,1,3}
Output:
1
Explanation:
1. push 1 from A to stack
2. push 2 from A to stack
3. pop 2 from stack to B
4. pop 1 from stack to B
5. push 3 from A to stack
6. pop 3 from stack to B

class Solution {
    public static int isStackPermutation(int n, int[] ip, int[] op) {
        // code here
     Stack<Integer> s = new Stack<>();
        int j=0;
        for(int i=0; i<n; i++) {
            s.push(ip[i]);
            while(!s.isEmpty()) {
                if(op[j]==s.peek()) {
                    s.pop();
                    j++;
                }
                else break;
            }
        }
       if(s.size()==0)
       {
                return 1;
        }
        return 0;
    }
}
 
