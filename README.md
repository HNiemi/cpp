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
```markdown
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
```
## Coin Change
Difficulty: Medium

You are given coins of different denominations and a total amount of money amount. Write a function to compute the fewest number of coins that you need to make up that amount. If that amount of money cannot be made up by any combination of the coins, return -1.
### Example:
Input: coins = [1, 2, 5], amount = 11

Output: 3 

Explanation: 11 = 5 + 5 + 1
### My Solution:
```markdown
    int coinChange(vector<int>& coins, int amount) {
        vector<int> dp;
        dp.resize(amount + 1);
        dp[0] = 0;
        for (int i = 1; i < dp.size(); i++) {
            dp[i] = INT_MAX;
        }
        for (int i = 1; i < amount + 1; i++) {
            for (int j = 0; j < coins.size(); j++) {
                if(coins[j] <= i && i - coins[j] >= 0) {
                    int subres = dp[i - coins[j]];
                    if (subres != INT_MAX && subres + 1 < dp[i]) {
                        dp[i] = subres + 1;
                    }
                }
            }
        }
        
        if (dp[amount] == INT_MAX) {
            return -1;
        }
        return dp[amount];
    }
```
## Remove Nth Node From End of Linked List
Difficulty: Medium

Given a linked list, remove the n-th node from the end of list and return its head.
### Example:
Given linked list: 1->2->3->4->5, and n = 2.

After removing the second node from the end, the linked list becomes 1->2->3->5.
### My Solution:
```markdown
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    ListNode* removeNthFromEnd(ListNode* head, int n) {
        if (head->next == NULL) {
            return NULL;
        }

        ListNode* first = head;
        ListNode* second = head;
        for(int i = 0; i < n; i++) {
            first = first->next;
        }
        if (first == NULL) {
            second = second->next;
            return second;
        }
        else {
            while (first->next != NULL) {
                first = first->next;
                second = second->next;
            }
        }
        ListNode* temp = second; 
        if (temp) {
            temp = temp->next;
        }
        if (temp) {
            temp = temp->next;
        }
        second->next = temp;
        return head;
    }
};
```
## Number of Islands 
Difficulty: Medium

Given a 2d grid map of '1's (land) and '0's (water), count the number of islands. An island is surrounded by water and is formed by connecting adjacent lands horizontally or vertically. You may assume all four edges of the grid are all surrounded by water.
### Example:
Given linked list: 1->2->3->4->5, and n = 2.

After removing the second node from the end, the linked list becomes 1->2->3->5.
### My Solution:
```markdown
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    ListNode* removeNthFromEnd(ListNode* head, int n) {
        if (head->next == NULL) {
            return NULL;
        }

        ListNode* first = head;
        ListNode* second = head;
        for(int i = 0; i < n; i++) {
            first = first->next;
        }
        if (first == NULL) {
            second = second->next;
            return second;
        }
        else {
            while (first->next != NULL) {
                first = first->next;
                second = second->next;
            }
        }
        ListNode* temp = second; 
        if (temp) {
            temp = temp->next;
        }
        if (temp) {
            temp = temp->next;
        }
        second->next = temp;
        return head;
    }
};
```
## Remove Nth Node From End of Linked List
Difficulty: Medium

Given a linked list, remove the n-th node from the end of list and return its head.
### Example:
Given linked list: 1->2->3->4->5, and n = 2.

After removing the second node from the end, the linked list becomes 1->2->3->5.
### My Solution:
```markdown
/**
 * Definition for singly-linked list.
 * struct ListNode {
 *     int val;
 *     ListNode *next;
 *     ListNode(int x) : val(x), next(NULL) {}
 * };
 */
class Solution {
public:
    ListNode* removeNthFromEnd(ListNode* head, int n) {
        if (head->next == NULL) {
            return NULL;
        }

        ListNode* first = head;
        ListNode* second = head;
        for(int i = 0; i < n; i++) {
            first = first->next;
        }
        if (first == NULL) {
            second = second->next;
            return second;
        }
        else {
            while (first->next != NULL) {
                first = first->next;
                second = second->next;
            }
        }
        ListNode* temp = second; 
        if (temp) {
            temp = temp->next;
        }
        if (temp) {
            temp = temp->next;
        }
        second->next = temp;
        return head;
    }
};
```
