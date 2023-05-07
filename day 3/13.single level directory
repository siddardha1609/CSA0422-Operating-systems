#include <stdio.h>
#include <stdlib.h>

int main()
{
    int n = 3, i;
    char dirname[20], filename[20];

    printf("Enter directory name: ");
    scanf("%s", dirname);

    if (mkdir(dirname) == -1) {
        printf("Error: Could not create directory.\n");
        exit(EXIT_FAILURE);
    }

    chdir(dirname);

    for (i = 0; i < n; i++) {
        printf("Enter file name: ");
        scanf("%s", filename);
        FILE* fp = fopen(filename, "w");
        if (fp == NULL) {
            printf("Error: Could not create file %s.\n", filename);
            exit(EXIT_FAILURE);
        }
        fclose(fp);
    }

    printf("%d files created successfully in directory %s.\n", n, dirname);
    return 0;
}
