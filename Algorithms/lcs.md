---

layout: default-algo
title: Algorithms.
problem: LCS(Longest common sunsequence)

---

# Problem


* LCS(Longest common sunsequence):

# Implementation

~~~
cpp

#include<bits/stdc++.h>
#define MOD(ll)(1e9+7)
using namespace std;
typedef long long int ll;
int main()
{
        ios_base::sync_with_stdio(false);cin.tie(NULL);
    long long int n,i,j,k,p,c,x;
    
    string s,t,ans="";
    cin>>s>>t;
    vector<int>b(s.size()+1,0);
    vector<vector<int> >a(t.size()+1,b);
    vector<vector<int> >a1(t.size()+1,b);
    map<char,int>m;
    for(i=0;i<26;i++)
    {
        cin>>m[(char)('a'+i)];
    }
    for(i=1;i<t.size()+1;i++)
    {
        for(j=1;j<s.size()+1;j++)
        {
            if(s[j-1]==t[i-1])
            {
                a1[i][j]=-1;
                k=i;
                p=j;
                while(k<=t.size()&&p<=s.size())
                   {
                       a[k][p]=a[k-1][p-1]+m[s[j-1]];
                       k++;
                       p++;
                   }
            }
            else
            {
                a[i][j]=max(a[i][j-1],a[i-1][j]);
                if(a[i][j-1]>a[i-1][j])
                    a1[i][j]=1;
            }
        }
    }
    cout<<a[t.size()][s.size()]<<endl;
    i=t.size();
    j=s.size();
    while(i>0&&j>0)
    {
        if(s[j-1]==t[i-1])
           {
               ans+=s[j-1];
               j--;
               i--;
           }
           else if(a1[i][j]==1)
            j--;
           else
            i--;

    }
    reverse(ans.begin(),ans.end());
    cout<<ans;
}
~~~
