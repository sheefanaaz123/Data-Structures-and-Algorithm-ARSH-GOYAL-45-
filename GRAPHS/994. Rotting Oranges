class Solution {
public:
    typedef pair<int, int> P;
    vector<vector<int>> directions{{-1, 0}, {1, 0}, {0, -1}, {0, 1}};

    int orangesRotting(vector<vector<int>>& grid) {
        int m = grid.size();
        int n = grid[0].size();

        queue<P> que;
        int freshCount = 0;

        for(int i = 0; i < m; i++) {
            for(int j = 0; j < n; j++) {
                if(grid[i][j] == 2) {
                    que.push({i, j}); //Storing all possible sources at once in the queue
                }
                else if(grid[i][j] == 1) {
                    freshCount++;
                }
            }
        }
        
        if(freshCount == 0)
            return 0;
        
        auto isSafe = [&](int x, int y) {
            return x >= 0 && x < grid.size() && y >= 0 && y<grid[x].size() && grid[x][y] == 1;
        };
        
        //Applying Multi-Source BFS
        int time = 0;
        while(!que.empty()) {
            int n = que.size();
            //because we want to cover all neighbours of a node
            //at once which are affected in a particular time frame
            while(n--) {
                P curr = que.front();
                que.pop();
                int i = curr.first;
                int j = curr.second;
                
                for(auto &dir : directions) {
                    int new_i = i + dir[0];
                    int new_j = j + dir[1];
                    
                    if(isSafe(new_i, new_j)) {
                        grid[new_i][new_j] = 2;
                        que.push({new_i, new_j});
                        freshCount--;
                    }
                }
            }
            time++;
        }
        
        return (freshCount==0) ? time-1 : -1;
    }
};
