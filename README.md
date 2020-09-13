# Chefina-and-Swap
#include <bits/stdc++.h>
using namespace std;
#define ull unsigned long long

int main() {
    ios_base::sync_with_stdio(false);
    cin.tie(NULL);
  int t;
  cin>>t;
  while(t--){
    ull n;
    cin>>n;
    ull sum=n*(n+1)/2;
    if(sum%2==0){
    ull swaps=0;
    ull m=(sqrt(1+4*sum)-1)/2;
    if(ceil((sqrt(1+4*sum)-1)/2)==(sqrt(1+4*sum)-1)/2){
            swaps=(m*(m-1))/2+((n-m)*(n-m-1))/2;
            m--;
    }
    for(ull i=m;i>=1  && (sum/2-(i*(i+1))/2)<=n-1;i--){
            ull diff=sum/2-(i*(i+1))/2;
            if(i+diff>=n){
                swaps+=min(n-diff,n-i);
            }else{
                swaps+=min(i,diff);
            }

        }
        cout<<swaps<<endl;
    }
    else cout<<0<<endl;

  }
 return 0;
}


