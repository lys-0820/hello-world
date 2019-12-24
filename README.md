#include <stdio.h>

int main(int argc, const char * argv[]) {
    int T;
    scanf("%d",&T);
    int i,j;
    char s[T][10000],t[T][10000];
    for(i=0;i<T;i++)
    {
        scanf("%s",&s[i]);
        scanf("%s",&t[i]);
    }
//input
    
    int judge[T];
    int count[T];
    for(i=0;i<T;i++)
    {
        int k=0;
        count[i]=0;
        for(j=0;j<strlen(s[i]);j++)
        {
            for(;k<strlen(t[i]);k++)
            {
                if(s[i][j]==t[i][k])
                {
                    count[i]++;
                    break;
                }
            }
        }
        if(count[i]==strlen(s[i]))
            judge[i]=1;
        else
            judge[i]=0;
    }
    for(i=0;i<T-1;i++)
    {
        if(judge[i]==1)
            printf("Yes\n");
        else
            printf("No\n");
    }
    if(judge[i]==1)
        printf("Yes");
    else
        printf("No");
    return 0;
}
