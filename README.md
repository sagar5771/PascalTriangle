# In Pascal's triangle, each number is the sum of the two numbers directly above it as shown:
Input: numRows = 5
Output: [[1],[1,1],[1,2,1],[1,3,3,1],[1,4,6,4,1]]
Solution:

  vector<vector<int>> generate(int numRows) {
        vector<vector<int>> r(numRows);
        for(int i=0;i<numRows;i++){
            r[i].resize(i+1);
            r[i][0] = r[i][i] = 1;
            for(int j=1;j<i;j++){
                r[i][j]=r[i-1][j-1] + r[i-1][j];
            }
        }
        return r;
    }
