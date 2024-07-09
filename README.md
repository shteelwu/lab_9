```c
#include <stdio.h>
#include <math.h>

int findMinSteps(int start, int end) {
    int distance = end - start;
    if (distance == 0) return 0;

    int stepsCount = 0;
    int increment = 0;
    int totalDistanceCovered = 0;

    while (totalDistanceCovered < distance) {
        stepsCount++;
        if (stepsCount % 2 == 1) {
            increment++;
        }
        totalDistanceCovered += increment;
    }

    return stepsCount;
}

int main() {
    int startPoint, endPoint;

    printf("Enter the starting point (start): ");
    scanf("%d", &startPoint);
    printf("Enter the ending point (end): ");
    scanf("%d", &endPoint);

    if (startPoint < 0 || endPoint >= pow(2, 31) || startPoint > endPoint) {
        printf("Invalid input\n");
        return 1;
    }

    int minStepsRequired = findMinSteps(startPoint, endPoint);
    printf("Minimum number of steps: %d\n", minStepsRequired);

    return 0;
}
