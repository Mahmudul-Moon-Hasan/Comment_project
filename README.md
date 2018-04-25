# Comment_project
This is my first project.
How can we delete comment from a program input in a file

#include<stdio.h>
int main()
{
    FILE *fp1,*fp2;
    char ch;

    fp1=fopen("input.txt","r");  // open a file to read input
    fp2=fopen("output.txt","w");  // open a file to show output

    while(1)   // infinite loop to take single character
    {
        ch=fgetc(fp1);
        if(ch==EOF)
            break;
        if(ch=='/')
        {
            ch=fgetc(fp1);
            if(ch=='*')
            {
                while(1)
                {
                    ch=fgetc(fp1);
                    if(ch=='*')
                    {
                        ch=fgetc(fp1);
                        if(ch=='/'||ch==EOF)
                        {
                            break;
                        }
                    }
                    if(ch==EOF)
                        break;
                }
            }
            else if(ch=='/')
            {
                while(1)
                {
                    ch=fgetc(fp1);
                    if(ch=='\n'||ch==EOF)
                        break;
                }
            }
        }
        else
        {
            putc(ch,fp2);
        }
    }
    fclose(fp1);
    fclose(fp2);
    return 0;
}

