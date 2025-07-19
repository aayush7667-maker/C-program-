# C-program-
Problems related to C programming 
#include <stdio.h>

void takeInput(int arr[], int n);
void findDuplicates(int arr[], int n);

int main() {
    int n;

    printf("Enter the number of elements: ");
    scanf("%d", &n);

    int arr[n];

    takeInput(arr, n);         // Function to input array elements
    findDuplicates(arr, n);    // Function to find and print duplicates

    return 0;
}

// Function to take input into the array
void takeInput(int arr[], int n)
 {
 	int i;
    printf("Enter %d elements:\n", n);
    for ( i = 0; i < n; i++) {
        scanf("%d", &arr[i]);
    }
}

// Function to find and print duplicate elements
void findDuplicates(int arr[], int n) {
    int found = 0;
	int i,j,k;
    printf("\nDuplicate elements are:\n");
    for (i = 0; i < n; i++) {
        for ( j = i + 1; j < n; j++) {
            if (arr[i] == arr[j]) {
                // Check if already printed
                int alreadyPrinted = 0;
                for ( k = 0; k < i; k++) {
                    if (arr[k] == arr[i]) {
                        alreadyPrinted = 1;
                        break;
                    }
                }
                if (!alreadyPrinted) {
                    printf("%d\n", arr[i]);
                    found = 1;
                }
            }
        }
    }

    if (!found) {
        printf("No duplicates found.\n");
    }
}
