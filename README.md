# Ex-10-IMPLEMENTATION-OF-SIMPLE-CODE-OPTIMIZATION-TECHNIQUES
IMPLEMENTATION OF SIMPLE CODE OPTIMIZATION TECHNIQUES 
# Date:
# Aim:
To write a C program to implement simple code optimization techniques such as Common subexpression elimination and Dead Code elimination.
# ALGORITHM :
1. Start the program.
2. The ‘L’values and their corresponding ‘R’ values are given as input.
3. After common subexpression elimination, the subexpressions that are common are identified and are removed.
4. After Dead code elimination, the subexpression that is of no use can be identified and is eliminated.
5. Stop the program.
# PROGRAM
exp10.c
```
#include<stdio.h>
#include<ctype.h>

int main() {
    int i = 2, j = 0, k = 2, k1 = 0;
    char ip[10], kk[10];
    FILE *fp;

    printf("\nEnter the filename of the intermediate code: ");
    scanf("%s", kk);

    fp = fopen(kk, "r");
    if(fp == NULL) {
        printf("\nError in opening the file\n");
        return 1; // Exiting the program with error code
    }

    printf("\n");
    while(fscanf(fp, "%s", ip) != EOF) {
        printf("\t\t%s\n", ip);
    }
    rewind(fp);

    printf("\n \n");
    printf("\tStatement\t\tTarget Code\n");
    printf("\n \n");

    while(fscanf(fp, "%s", ip) != EOF) {
        printf("\t%s", ip);
        printf("\t\tMOV %c,R%d\n\t", ip[i + k], j);

        if(ip[i + 1] == '+') {
            printf("\t\tADD");
        } else {
            printf("\t\tSUB");
        }

        if(islower(ip[i])) {
            printf("%c,R%d\n\n", ip[i + k1], j);
        } else {
            printf("%c,%c\n", ip[i], ip[i + 2]);
        }
        j++;
        k1 = 2;
        k = 0;
    }

    printf("\n \n");
    fclose(fp);
    return 0; // Indicating successful execution
}
```
# OUTPUT
![image](https://github.com/ttamizharasi/Ex-10-IMPLEMENTATION-OF-SIMPLE-CODE-OPTIMIZATION-TECHNIQUES/assets/119657317/3d49f6f5-5f5c-4610-8909-43a2dd742ca1)

# RESULT
The simple code optimization techniques such as common subexpression elimination and dead code elimination are implemented successfully and the output is verified.

