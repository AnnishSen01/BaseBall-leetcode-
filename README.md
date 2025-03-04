# BaseBall-leetcode-
int calPoints(char** operations, int operationsSize) {
    
int stack[operationsSize];
int top=-1;
    for(int i=0;i<operationsSize;i++)
    {
        if(strcmp("+",operations[i])==0)
        {
            top++;
            stack[top]=stack[top-1]+stack[top-2];
        
        }
        else if(strcmp("D",operations[i])==0)
        {
            top++;
            stack[top]=2*stack[top-1];
        }
        else if (strcmp("C",operations[i])==0)
        {
            top--;
        }
        else
        {
            top++;
            stack[top]=atoi(operations[i]);
        }

    }
    int sum=0;
    for(int i=0;i<=top;i++)
    {
        sum+=stack[i];
    }
    return sum;
}
