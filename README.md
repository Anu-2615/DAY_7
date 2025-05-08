# DAY_7
ROTATE LIST & PLUS ONE


# 🔁 Rotate Linked List - LeetCode Problem

## Problem
Given the `head` of a linked list and an integer `k`, rotate the list to the right by `k` places.

## 📥 Input
- A singly linked list (e.g., 1 -> 2 -> 3 -> 4 -> 5)
- Integer `k` (e.g., 2)

## 📤 Output
- Rotated linked list (e.g., 4 -> 5 -> 1 -> 2 -> 3)

## 🚀 Approach

1. ✅ Handle edge cases (empty list or single node).
2. 📏 Count the length of the list.
3. 🔁 Optimize `k` using `k % length`.
4. 🐇 Use two pointers to find the new head.
5. 🔗 Rewire the last node to the old head.

## 💻 Code (Java)
```java
if (head == null || head.next == null) return head;

ListNode temp = head;
int cnt = 1;
while (temp.next != null) {
    temp = temp.next;
    cnt++;
}

k %= cnt;
if (k == 0) return head;

ListNode slow = head, fast = head;
while (k-- > 0) fast = fast.next;

while (fast.next != null) {
    fast = fast.next;
    slow = slow.next;
}

ListNode newHead = slow.next;
slow.next = null;
fast.next = head;
return newHead;

Sample Input
ini
head = [1,2,3,4,5], k = 2

Output

[4,5,1,2,3]






PLUS ONE

# LeetCode Problem: 66. Plus One

## Problem Statement
You are given a large integer represented as an array `digits`, where each element is a single digit. The digits are stored such that the most significant digit is at the start of the array. Increment this integer by one and return the resulting array of digits.

## Example

### Input

digits = [1, 2, 3]
[1, 2, 4]

public int[] plusOne(int[] digits) {
    for (int i = digits.length - 1; i >= 0; i--) {
        if (digits[i] < 9) {
            digits[i]++;
            return digits;
        }
        digits[i] = 0;
    }
    int[] newdigit = new int[digits.length + 1];
    newdigit[0] = 1;
    return newdigit;
}
Time and Space Complexity
Time Complexity: O(n)

Space Complexity: O(1) or O(n) (in case of carry like [9,9,9])

Key Concepts
Array traversal

Carry handling

Edge case handling for numbers like [9, 9, 9]

