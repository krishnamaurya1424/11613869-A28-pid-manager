#include<stdio.h>
#include <pthread.h>
#include<unistd.h>
#include <windows.h>                        //for working of Sleep() function in Dev c++

#define MIN_PID 300
#define MAX_PID 5000

int VarOfThread = 0;
pthread_mutex_t l;

struct Struct_pid
{
    int VarOfPid;
    bool ProcessBit;
}ArrForPid[4700];

int allocate_map(void)                      //For Creating & initialising data structure for represent pid(Ex 3.20)            
{
    int i,j;
    for(i = MIN_PID, j =0; i <= MAX_PID; i++, j++)
    {
        ArrForPid[j].VarOfPid= i;
        ArrForPid[j].ProcessBit = 0;
    }

    if(i == MAX_PID && j == 4700)
    return 1;
	else
    return -1;
}
int main()
{
}
