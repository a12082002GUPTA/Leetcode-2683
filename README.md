# Leetcode-2683

# C++ Brute Force

class Solution {
public:
    bool doesValidArrayExist(vector<int>& derived) {
        int n=derived.size();
        vector<int>v(n);
        v[0]=0;
        for(int i=1;i<n;i++)
        {
            if(derived[i-1]==0)
            {
                v[i]=v[i-1];
            }
            else
            {
                if(v[i-1]==1)v[i]=0;
                else 
                v[i]=1;
            }
        }
        int a=v[0]^v[n-1];
        if(a!=derived[n-1])return false;
        return true;
    }
};


# C++ Optimised

class Solution {
public:
    bool doesValidArrayExist(vector<int>& derived) {
        int ans=0;
        for(int i=0;i<derived.size();i++)
        {
            ans^=derived[i];
        }
        if(ans==0)return true;
        return false;
    }
};


# Python

class Solution:
    def doesValidArrayExist(self, derived):
        ans = 0
        for num in derived:
            ans ^= num
        return ans == 0


# Java

class Solution {
    public boolean doesValidArrayExist(int[] derived) {
        int ans = 0;
        for (int i = 0; i < derived.length; i++) {
            ans ^= derived[i];
        }
        return ans == 0;
    }
}
