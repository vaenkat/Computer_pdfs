# program 5a

#include <stdio.h>
int main() {
int num;
printf("Enter numbers continuously (enter a negative number to stop):\n");
while (1) { // Infinite loop, will break when a negative number is entered
printf("Enter a number: ");
scanf("%d", &num);
if (num < 0) {
printf("Negative number detected. Stopping input.\n");
break; // Exit the loop
}
printf("You entered: %d\n", num);
}
printf("Program terminated.\n");
return 0;
}

# program 5b

#include <stdio.h>
int main() {
int i;
printf("Numbers from 1 to 50 (excluding multiples of 5):\n");
for (i = 1; i <= 50; i++) {
if (i % 5 == 0)
continue; // Skip multiples of 5
printf("%d ", i);
}
printf("\n");
return 0;
}

# program 5c

#include <stdio.h>
int main() {
char password[20];
const char correctPassword[] = "Cprogram123"; // predefined correct password
int i, isMatch;
start: // label for retry
printf("Enter your password: ");
scanf("%s", password);
// Manual string comparison
isMatch = 1; // assume match unless proven otherwise
for (i = 0; correctPassword[i] != '\0' || password[i] != '\0'; i++) {
if (password[i] != correctPassword[i]) {
isMatch = 0; // not a match
break;
}
}
if (isMatch)
printf("Access Granted \n");
else {
printf("Incorrect Password! Try again.\n\n");
goto start; // jump back to retry
}
return 0;
}

# program 6b

#include <stdio.h>
int main() {
int n, i, j;
float scores[100], temp;
printf("Sports Result Sheet - 100 Meter Race\n");
printf("------------------------------------\n");
// Input number of students
printf("Enter the number of students: ");
scanf("%d", &n);
// Input scores
printf("Enter the scores (timing or points) of %d students:\n", n);
for (i = 0; i < n; i++) {
printf("Student %d: ", i + 1);
scanf("%f", &scores[i]);
}
// Sort scores in descending order (using Bubble Sort)
for (i = 0; i < n - 1; i++) {
for (j = 0; j < n - i - 1; j++) {
if (scores[j] < scores[j + 1]) {
temp = scores[j];
scores[j] = scores[j + 1];
scores[j + 1] = temp;
}
}
}
// Display sorted results
printf("\n Final Result Sheet (Highest to Lowest):\n");
printf("------------------------------------------\n");
for (i = 0; i < n; i++) {
printf("Position %d: %.2f\n", i + 1, scores[i]);
}
return 0;
}