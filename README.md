// Online C compiler to run C program online
#include <stdio.h>
#include <string.h>

    struct Student
    { char Student_name[25];
      int roll_no;
      float Obt_marks;
    };
     //Write C code here
    int main() {
     
     struct Student Assign[20];
     int Max_marks=100,n;
     printf("Enter number of students :");
     scanf("%d",&n);
     printf("\n");
     
     for(int i=0;i<n;i++) {
        printf("Enter name of the student:");
        scanf("%s", Assign[i].Student_name);
        printf("Enter roll number of the student:");
        scanf("%d",&Assign[i].roll_no);
        printf("Enter marks obtained in assignment:");
        scanf("%f",&Assign[i].Obt_marks);
        printf("\n");
      }
      
       for(int i=0;i<n;i++) {
         for(int j=i+1;j<n+1;j++) {
           if(Assign[i].Obt_marks<Assign[j].Obt_marks) {
                 int temp=Assign[i].Obt_marks;
                 Assign[i].Obt_marks= Assign[j].Obt_marks;
                 Assign[j].Obt_marks=temp;
                 
                 char S1[25];
                 strcpy(S1, Assign[i].Student_name);
                 strcpy( Assign[i].Student_name, Assign[j].Student_name);
                 strcpy( Assign[j].Student_name, S1);
                 
                 int Roll=Assign[i].roll_no;
                 Assign[i].roll_no=Assign[j].roll_no;
                 Assign[j].roll_no=Roll;
           } 
       }
       }
       //Display details of the student
       printf("\n=================Student Details====================\n");
       printf("\n");
       for(int i=0;i<n;i++)
        {printf("Name of the student is:%s",Assign[i].Student_name);
         printf("\n--------------------------------------------------\n");
         printf("Roll number of the student is:%d",Assign[i].roll_no);
         printf("\n--------------------------------------------------\n");
         printf("Maximum marks:%d",Max_marks);
         printf("\n--------------------------------------------------\n");
         printf("Marks obtained in assignment:%f",Assign[i].Obt_marks);
         printf("\n**************************************************\n");
         printf("\n");
        }
       printf("\n====================================================\n");
       
      
    return 0;
}
