# Phrase-abbreviation

Phrase abbreviation

Problem Description

定义：一个词组中每个单词的首字母的大写组合称为该词组的缩写。

比如，C语言里常用的EOF就是end of file的缩写。

Input

输入的第一行是一个整数T，表示一共有T组测试数据；

接下来有T行，每组测试数据占一行，每行有一个词组，每个词组由一个或多个单词组成；每组的单词个数不超过10个，每个单词有一个或多个大写或小写字母组成；
单词长度不超过10，由一个或多个空格分隔这些单词。

Output

请为每组测试数据输出规定的缩写，每组输出占一行。

Sample Input

1 end of file

Sample Output

EOF

代码：

#include"stdio.h"

int main()

{

    int t,i,n;
    
    char str[120],a[13];
    
    scanf("%d",&n);
    
    getchar();
    
    while(n--)
    
    {
    
        gets(str);
        
        if(str[0]!=' ')
        
        {
        
            a[0]=str[0];
            
            t=1;
            
            for(i=0;str[i]!='\0';i++)
            
            {
            
                if(str[i]==' '&&str[i+1]!=' ')
                
                    a[t++]=str[i+1];
                    
                if(a[t-1]>=97 && a[t-1]<=122)
                
                    a[t-1]-=32;
                    
            }
            
            a[t]='\0';
            
            puts(a);
            
        }
        
        else
        
        {
            t=0;
            
            for(i=0;str[i]!='\0';i++)
            
            {
            
                if(str[i]==' '&&str[i+1]!=' ')
                
                    a[t++]=str[i+1];
                    
                if(a[t-1]>=97 && a[t-1]<=122)
                
                    a[t-1]-=32;
                    
            }
            
            a[t]='\0';
            
            puts(a);
            
        }
    }
    
    
    return 0;
    
}
