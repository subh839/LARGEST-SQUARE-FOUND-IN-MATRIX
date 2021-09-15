# LARGEST-SQUARE-FOUND-IN-MATRIX

class Solution{
public:
    int maxSquare(int n, int m, vector<vector<int>> t){
        // code here int dp[n][m];
        
        if (n == 1 || m == 1)
return 1;
int dp[n][m];
int ans = 0;
for (int i = 0; i < n; i++) {
for ( int j = 0; j < m; j++) {
if (i == 0 || j == 0)
dp[i][j] = t[i][j];
else if (t[i][j] == 1) {
dp[i][j] = min(dp[i - 1][j], min(dp[i][j - 1], dp[i - 1][j - 1])) + 1;
ans = max(dp[i][j], ans);
}
else if (t[i][j] == 0)
dp[i][j] = 0;
}
}
return ans;
}
    
