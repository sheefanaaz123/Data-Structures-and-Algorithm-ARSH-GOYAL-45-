#include <iostream>
#include <vector>
#include <string>

using namespace std;

const int ALPHABET_SIZE = 256;

// Function to precompute the bad character array
void precomputeBadCharacter(const string& pattern, vector<int>& badChar) {
    int m = pattern.size();

    // Initialize bad character array with -1
    badChar.assign(ALPHABET_SIZE, -1);

    // Fill the array with the last occurrence of each character in the pattern
    for (int i = 0; i < m; ++i) {
        badChar[pattern[i]] = i;
    }

}

// Boyer-Moore algorithm for pattern matching
void boyerMoore(const string& text, const string& pattern) {
    int m = pattern.size();
    int n = text.size();

    vector<int> badChar;

    // Precompute the bad character array
    precomputeBadCharacter(pattern, badChar);

    int s = 0; // Shift of the pattern with respect to the text

    while (s <= n - m) {
        int j = m - 1;

        // Check for a match starting from the end of the pattern
        while (j >= 0 && pattern[j] == text[s + j]) {
            --j;
        }

        if (j < 0) {
            // Pattern is found at index s
            cout << "Pattern found at index " << s << endl;

            // Move the pattern to the next possible match
            s += (s  < n - m) ? m - badChar[text[s + m]] : 1;
        } else {
            // Shift the pattern to align the bad character
            s += max(1, j - badChar[text[s + j]]);
        }
    }
}

int main() {
    string text = "ABAAABCD";
    string pattern = "ABC";

    cout << "Text: " << text << endl;
    cout << "Pattern: " << pattern << endl;

    boyerMoore(text, pattern);
   
   
    return 0;
}
