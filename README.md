# C-p90-1-
C语言学习笔记 p90 函数与递归(1)
#include<time.h>
#include<stdio.h>
#include<stdlib.h>
#include<string.h>
//猜数字游戏
void menu()
{
    printf("**********************\n");
    printf("****1.play  0.exit****\n");
    printf("**********************\n");
}
//RAND_MAX:0-32767之间
void game()
{
    //1.生成一个随机数
    int ret=0;
    srand((unsigned int)time(NULL));//在生成随机数时，这里要求输入一个无时无刻发生变化的数
    //时间戳：当前计算机的时间-计算机的起始时间（1970.1.1 0:00）
    ret=rand()%100+1;//rand()专门生成随机数的库函数
    printf("%d\n",ret);
    //2.猜数字
    while(1)
    {
        printf("请猜数字>:");
        scanf("%d",&guess);
        if(guess>ret)
        {
            printf("猜大了\n");
        }
        else if(guess<ret)
        {
            printf("猜小了\n");
        }
        else
        {
            printf("猜对了\n");
            break;
        }
    }
}
int main()
{
    int input=0;
    srand((unsigned int)time(NULL));//在生成随机数时，这里要求输入一个无时无刻发生变化的数
    do
    {
        menu();
        printf("请选择>:");
        scanf("%d",&input);
        switch(input)
        {
            case 1:
                game();//猜数字游戏
                break;
            case 0:
                printf("退出游戏\n");
                break;
            default:
                printf("选择错误\n");
                break;
        }
    }
    while(input);
    return 0;
}



int main()
{
again:
    printf("helli,bit\n");
    goto again//goto放哪里这行代码跳哪里
    return 0;
}


//关机程序
int main()
{
    //shutdown -s -t 60 关机指令
    //system()-执行系统命令
    system("shutdown-s -t 60");
again
    printf("请注意，你的电脑在1分钟内关机，如果输入：我是猪，则取消关机\n请输入>:");
    scanf("%s",input);
    if(strcmp(input,"我是猪“）==0)//比较两个字符串-strcmp()
    {
        system("shutdown-a");
    }
    else
    {
        goto again;
    }
    return 0;
}




