## DSA

# Kth permutation

https://leetcode.com/problems/permutation-sequence/solutions/7518982/simple-clean-code-with-full-expl-and-com-3ou7

Code:

class Solution {
public int fact(int n){
int f=1;
for(int i=2;i<=n;i++){
f=f*i;
}
return f;
}
public String getPermutation(int n, int k) {
StringBuilder sb=new StringBuilder();
List<Integer> nums=new ArrayList<>();
for(int i=1;i<=n;i++){
nums.add(i);
}
k-=1;
int a=n;
for(int i=0;i<n;i++){
int size=fact(a-1);
int b=k/size;
sb.append(nums.get(b)+"");
k=k%size; //k%size because are next k will be the remains of what was not consumed by our current k

a--;
nums.remove(b); //because a is reduced
}
return sb.toString();
}
}