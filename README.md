# C++
A collection of my C++ coding challenges I have completed through online resources

## Backspace String Compare
Difficult: Easy

Given two strings S and T, return if they are equal when both are typed into empty text editors. # means a backspace character.
Note that after backspacing an empty text, the text will continue empty.
### Example:
Input: S = "ab#c", T = "ad#c"

Output: true

Explanation: Both S and T become "ac".
### My Solution:
class Solution {
public:
    bool backspaceCompare(string S, string T) {
        stack<char> stackS;
        stack<char> stackT;

        for (int i = 0; i < S.size(); i++) {
            if (S[i] == '#') {
                if (!stackS.empty()) {
                    stackS.pop();
                }
            }
            else {
                stackS.push(S[i]);
            }
        }
        for (int i = 0; i < T.size(); i++) {
            if (T[i] == '#') {
                if (!stackT.empty()) {
                    stackT.pop();
                }
            }
            else {
                stackT.push(T[i]);
            }
        }
        return stackS == stackT;
    }
};
