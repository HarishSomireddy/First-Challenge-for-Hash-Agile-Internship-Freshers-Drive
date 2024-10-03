# First-Challenge-for-Hash-Agile-Internship-Freshers-Drive
~~~
HATFD1005
Longest Palindromic Substring
Write a program to find the longest palindromic substring in a given string without using any built-in 
substring or reverse functions. For example, for input "babad", the output should be "bab" or "aba".
Instructions: Avoid using any string handling libraries. Implement a solution that checks all substrings 
manually.


Program:
#include <stdio.h>
#include <stdbool.h>
#define MAX_LENGTH 1000
bool isPalindrome(char str[], int start, int end) {
 while (start < end) {
 if (str[start] != str[end]) {
 return false;
 }
 start++;
 end--;
 }
 return true;
}
void longestPalindromicSubstring(char str[]) {
 int maxLength = 1;
 int start = 0, end = 0;
 int tempStart, tempEnd;
 for (int i = 0; str[i] != '\0'; i++) {
 for (int j = i + 1; str[j] != '\0'; j++) {
 if (isPalindrome(str, i, j - 1)) {
 if (j - i > maxLength) {
 maxLength = j - i;
 start = i;
 end = j - 1;
 }
 }
 }
 }
 printf("Longest palindromic substring: ");
 for (int i = start; i <= end; i++) {
 printf("%c", str[i]);
 }
 printf("\n");
}
int main() {
 char str[MAX_LENGTH];
 printf("Enter a string: ");
 fgets(str, MAX_LENGTH, stdin);
 str[strlen(str) - 1] = '\0'; // remove newline character
 longestPalindromicSubstring(str);
 return 0;
 }
~~~
