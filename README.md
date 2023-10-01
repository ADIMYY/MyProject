#include <bits/stdc++.h>
using namespace std;
#define ll long long int
#define dl "\n"
void ADIMY(){
    ll n;
    cin >> n;
    stack < string > st;
    while(n--){
        string s;
        cin >> s;
        if(s == "Header" || s == "Table" || s == "Row" || s == "Cell") st.push(s);
        else{
            if(s == "EndHeader")
                if(st.top() == "Header") st.pop();
                else st.push(s);
            else if(s == "EndRow")
                if(st.top() == "Row") st.pop();
                else st.push(s);
            else if(s == "EndCell")
                if(st.top() == "Cell") st.pop();
                else st.push(s);
            else
                if(st.top() == "Table") st.pop();
                else st.push(s);
        }
    }
    if(st.size() == 0) cout << "ACC" << dl;
    else cout << "WA" << dl;
}
int32_t main(){
    ios_base::sync_with_stdio(false),cin.tie(nullptr),cout.tie(nullptr);
    #ifndef ONLINE_JUDGE
        freopen("input.text", "r", stdin), freopen("output.text", "w", stdout);
    #endif
    int tt = 1;
    //cin >> tt;
    for (int tc = 1; tc <= tt; tc++){
        // cout << "Case #" << tc << ": ";
        ADIMY();
    }
    return 0;
}
