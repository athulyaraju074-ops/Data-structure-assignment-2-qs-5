#include <stdio.h>
#include <string.h>

int linearSearch(char arr[][30], int n, const char key[], int *comparisons) {
    *comparisons = 0;

    for (int i = 0; i < n; i++) {
        (*comparisons)++;

        if (strcmp(arr[i], key) == 0)
            return i;
    }

    return -1;
}

int binarySearch(char arr[][30], int n, const char key[], int *comparisons) {
    int low = 0;
    int high = n - 1;
    *comparisons = 0;

    while (low <= high) {
        int mid = (low + high) / 2;
        (*comparisons)++;

        int result = strcmp(arr[mid], key);

        if (result == 0)
            return mid;
        else if (result < 0)
            low = mid + 1;
        else
            high = mid - 1;
    }

    return -1;
}

int main() {
    /* Department names are already sorted alphabetically
       for Binary Search. */
    char departments[][30] = {
        "Backend",
        "CEO",
        "Development",
        "Finance",
        "Frontend",
        "HR",
        "IT",
        "Testing"
    };

    int n = 8;
    char key[30];
    int linearComparisons, binaryComparisons;

    printf("Enter department to search: ");
    scanf("%29s", key);

    int linearResult =
        linearSearch(departments, n, key, &linearComparisons);

    int binaryResult =
        binarySearch(departments, n, key, &binaryComparisons);

    if (linearResult != -1)
        printf("Linear Search: Found, comparisons = %d\n",
               linearComparisons);
    else
        printf("Linear Search: Not Found, comparisons = %d\n",
               linearComparisons);

    if (binaryResult != -1)
        printf("Binary Search: Found, comparisons = %d\n",
               binaryComparisons);
    else
        printf("Binary Search: Not Found, comparisons = %d\n",
               binaryComparisons);

    return 0;
}
