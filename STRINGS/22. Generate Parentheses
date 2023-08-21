#include <iostream>
#include <vector>
using namespace std;

class Solution {
public:
    vector<string> generateParenthesis(int n) {
        vector<string> result;
        makeCombinations("(", 1, 0, result, n);
        return result;
    }

    void makeCombinations(string current, int open, int close, vector<string>& result, int n) {
        if (current.length() == 2 * n) {
            result.push_back(current);
            return;
        }

        if (open < n) {
            makeCombinations(current + "(", open + 1, close, result, n);
        }

        if (close < open) {
            makeCombinations(current + ")", open, close + 1, result, n);
        }
    }
};

int main() {
    Solution solution;
    int n = 3;
    vector<string> combinations = solution.generateParenthesis(n);
    for (const string& comb : combinations) {
        cout << comb << endl;
    }
    return 0;
}
