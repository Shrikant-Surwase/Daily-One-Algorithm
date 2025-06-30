# Daily-One-Algorithm
## 1.Union Find Algorithm
https://leetcode.com/explore/learn/card/graph/618/disjoint-set/3881/
```cpp
class Solution {
public:
vector<int>par;
int find(int a){
    return par[a]=par[a] == a ? a: find(par[a]);
}
void Union(int a, int b){
    int x = find(a);
    int y = find(b);
    par[max(x,y)] = min(x,y);
    return;
}
    string smallestEquivalentString(string s1, string s2, string baseStr) {
        par.resize(26);
        for(int i=0;i<26; i++) par[i] = i; //this is nothing but assign self root node
        //first thing first we have to find the root of the element
        for(int i=0; i<s1.size(); i++){
            int a = s1[i]-'a';
            int b = s2[i]-'a';
            Union(a,b);
        }
        for(int i=0;i<baseStr.size(); i++){
            baseStr[i] = find(baseStr[i]-'a')+'a';
        }
        return baseStr;
    }
}
```
