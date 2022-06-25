# bank
#include<stdio.h>
#include<stdlib.h>
#include<string.h>
#include<conio.h>
#define N 1000

struct chuhu
{
	char idnum[9];//账户 
	char name[10];//姓名
	char idnumber[20];//省份证号
	char password[7];//密码 
	double cunkuan;//存款 
}hu[N]; 

void date();//显示当前日期
void dateEnglish(); 
int a,a1;//主界面选择变量 
void Flag0();//选择语言界面 
void Flag1();//主界面
void Flag1enlish();
void Flag2();//用户界面 
void Flag2enlish();
void Flag3();//用户功能选择界面
void Flag3enlish();
void zhuce();//注册 
void signUp();
int yanzheng();//验证存单号或密码 
int cheking();
//&&&&&&&&&&&&&&&&&&&&&&&
void qukaun();//取款
void drawMoney(); 
void cunkaun();//存款
void saveMoney();
void zhuan();//转账 
void transfer();
void xiugai();//密码修改 
void updatePassword();
void chaxun();//查找 
void enquiry();
//&&&&&&&&&&&&&&&&&&&&&&&&&&
int A,key;//开户人数 
int i;//控制密码循环 
char ch='y';//是否继续注册 
double jin;//存的钱 
int t;

char id[11],password[7];

int main()
{
    system("COLOR 05"); 
	int a,b,t;
	Flag0();
	scanf("%d",&b);
	switch(b)
	{
		case 1:
			{
				Flag1();//引入主界面
				do{
					printf("\n\n\t\t##请输入你的选择：\n");
					scanf("%d",&a); 
					switch(a)
					{
							case 1:{
									zhuce(); 
									Flag1(); 
									break;
						           }
							case 2:{
									t=yanzheng();
									fflush(stdin);
									Flag2();
									break;
							       } 
							case 3:exit(0);
							       break;
							default:printf("\n\n\n\t\t您输入的数据不符合要求!!!\n\n\n\n\n");	
				            }
				   }while(1);
			}
		case 2:
			{
				Flag1enlish();//引入主界面
				do{
					printf("\n\n\t\t##请输入你的选择：\n");
					scanf("%d",&a); 
					switch(a)
					{
							case 1:{
									signUp();//注册 
									Flag1enlish(); 
									break;
						           }
							case 2:{
									t=cheking();
									fflush(stdin);
									Flag2enlish();
									break;
							       } 
							case 3:exit(0);
							       break;
							default:printf("\n\n\n\t\t您输入的数据不符合要求!!!\n\n\n\n\n");	
				            }
				   }while(1);
			}
		default:printf("\n\n\n\t\t您输入的数据不符合要求!!!\n\n\n\n\n");
	}
	
}

void Flag0()
{
	printf("###########################################################\n");
	printf("|||              欢迎使用中国人民银行                   |||\n");
	printf("|||    Welcome to use People's bank in China            |||\n");
	printf("###########################################################\n");
	printf("|||                   请选择你需要的语言                |||\n");
	printf("|||            please select the language you need      |||\n");
	printf("###########################################################\n");
	printf("|||                    1.  中文                         |||\n");
	printf("|||                    2.  Enlish                       |||\n");
	printf("###########################################################\n");
	
	
}

void Flag1()
{
	printf("\n$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$\n");
    printf("\n▓                           * 自动取款机系统  *                               ▓\n");
    printf("\n$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$\n");
	printf("\n          ◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆\n");
	printf("          |◆|!!!!!!|◆|                                     |◆|!!!!!!|◆|\n");
	printf("          |◆|!!!!!!|◆|       ☆ 开户业务    请按 1         |◆|!!!!!!|◆|\n"); 
	printf("          |◆|!!!!!!|◆|       ☆ 登录系统    请按 2         |◆|!!!!!!|◆|\n");
	printf("          |◆|!!!!!!|◆|       ☆ 退出        请按 3         |◆|!!!!!!|◆|\n");
	printf("          |◆|!!!!!!|◆|                                     |◆|!!!!!!|◆|\n");
	printf("          ◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆\n");
	printf("\n$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$\n");
	
} 

void Flag1enlish()
{
	printf("\n$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$\n");
    printf("\n                                   * WELCOME  *                                  \n");
    printf("\n$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$\n");
	printf("\n          ◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆\n");
	printf("          |◆|******|◆|                                     |◆|******|◆|\n");
	printf("          |◆|******|◆|       ☆1. Sign  Up                 |◆|******|◆|\n"); 
	printf("          |◆|******|◆|       ☆2. Sign  In                 |◆|******|◆|\n");
	printf("          |◆|******|◆|       ☆3. Sign  Out                |◆|******|◆|\n");
	printf("          |◆|******|◆|                                     |◆|******|◆|\n");
	printf("          ◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆\n");
	printf("\n$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$\n");
		
}



//********************************************************************************************************************

//用户界面 
void Flag2()
{
       int a;//选择功能的变量
       char ch;
	   do{
	   	printf("\n\n按ENTER键进入、返回主菜单 \n");
	   	fflush(stdin);
	   	scanf("%c",&ch);
	   	system("cls");//清屏
		   date(); 
	printf("\n#################################################################################\n");
    printf("\n▓                               * 欢迎使用  *                                 ▓\n");
    printf("\n#################################################################################\n");
	printf("\n          ◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆\n");	
	printf("          |◆|******|◆|        ☆ 存款业务       请按 1        |◆|******|◆|\n"); 
	printf("          |◆|******|◆|        ☆ 取款业务       请按 2        |◆|******|◆|\n");
	printf("          |◆|******|◆|        ☆ 查询业务       请按 3        |◆|******|◆|\n"); 
	printf("          |◆|******|◆|        ☆ 转账业务       请按 4        |◆|******|◆|\n");
	printf("          |◆|******|◆|        ☆ 修改密码       请按 5        |◆|******|◆|\n");
	printf("          |◆|******|◆|        ☆ 退出系统       请按 6        |◆|******|◆|\n"); 
	printf("          |◆|******|◆|                                        |◆|******|◆|\n");
	printf("          ◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆\n");
    printf("\n$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$\n");
    printf("\n$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$\n");
	printf("\n\n\t\t##请输入你的选择：\n");
	fflush(stdin);
	scanf("%d",&a);
	switch(a)
	{//注册
		case 1: 
		{ 
			system("cls");fflush(stdin);cunkaun();break;//存款
		} 
		case 2:  
		{
			system("cls");fflush(stdin);qukaun();break;//取款
		}
		case 3: 
		{
			chaxun();//查询业务
			break;
		}
		case 4:
		{
			system("cls");fflush(stdin);zhuan();break;//转账 
		}
		case 5: 
		{
			system("cls");fflush(stdin);xiugai();break;//密码修改
		}
		case 6: exit(0);
		default:printf("您输入的选择有误，请输入正确的选项：\n");
	                                            	         
	}
	 } while(1);
} 

void Flag2enlish()
{
       int a;//选择功能的变量
       char ch;
	   do{
	   	printf("\n\nPress ENTER to ENTER and return to the main menu\n");
	   	fflush(stdin);
	   	scanf("%c",&ch);
	   	system("cls");//清屏
		   date(); 
	printf("\n$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$\n");
    printf("\n▓                               *  Weclome  *                                 ▓\n");
    printf("\n$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$\n");
	printf("\n          ◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆\n");	
	printf("          |◆|******|◆|      ☆1.Deposit    business           |◆|******|◆|\n"); 
	printf("          |◆|******|◆|      ☆2.Withdrwal  business           |◆|******|◆|\n");
	printf("          |◆|******|◆|      ☆3.Enquiry    Service            |◆|******|◆|\n"); 
	printf("          |◆|******|◆|      ☆4.Money Transfer Service        |◆|******|◆|\n");
	printf("          |◆|******|◆|      ☆5.Change the password           |◆|******|◆|\n");
	printf("          |◆|******|◆|      ☆6.Exit the system               |◆|******|◆|\n"); 
	printf("          |◆|******|◆|                                        |◆|******|◆|\n");
	printf("          ◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆◆\n");
    printf("\n$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$\n");
    printf("\n▓                          #################################                    ▓\n");
    printf("\n$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$\n");
	printf("\n\n\t\t##请输入你的选择：\n");
	fflush(stdin);
	scanf("%d",&a);
	switch(a)
	{//注册
		case 1: 
		{ 
			system("cls");fflush(stdin);saveMoney();break;//存款
		} 
		case 2:  
		{
			system("cls");fflush(stdin);drawMoney();break;//取款
		}
		case 3: 
		{
			enquiry();//查询业务
			break;
		}
		case 4:
		{
			system("cls");fflush(stdin);transfer();break;//转账 
		}
		case 5: 
		{
			system("cls");fflush(stdin);updatePassword();break;//密码修改
		}
		case 6: exit(0);
		default:printf("You have entered an incorrect selection. Please enter the correct selection:\n");
	                                            	         
	}
	 } while(1);
} 
//********************************************************************************************************************
//用户功能选择界面 
void Flag3()
{
	printf("\n\n\t\t##请输入你的选择：\n");
	scanf("%d",&a1);
	switch(a1)
	{
		case 1:printf("存款业务");break; 
		case 2:printf("取款业务");break; 
		case 3:printf("查询业务");break; 
		case 4:printf("转账业务");break; 
		case 5:printf("密码修改");break;
		case 6:printf("退出");break;  
	} 
}

void Flag3enlish()
{
    printf("\n\n\t\t##Please enter your choice:\n");
	scanf("%d",&a1);
	switch(a1)
	{
		case 1:printf("Deposit business\n");break; 
		case 2:printf("Withdrwal business\n");break; 
		case 3:printf("Enquiry service \n");break; 
		case 4:printf("Money Transfer Service\n");break; 
		case 5:printf("Change the password\n");break;
		case 6:printf("Exit the system\n");break;  
	} 
}




//********************************************************************************************************************
//开户 
void zhuce(){
	FILE *nchuhu=fopen("D:/atm.txt","r");
	FILE *fchuhu=fopen("D:/atm.txt","a");
	int i;
	if((nchuhu=fopen("D:/atm.txt","r"))==NULL) printf("文件无，系统创建\n"); 
	do{
	 system("cls");
	date();//显示当前日期 
	printf("\n\n\t\t请输入新储户的信息：");
	fscanf(nchuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[A].idnum,hu[A].name,hu[A].idnumber,hu[A].password,&hu[A].cunkuan); 
	
	printf("--------------------\n");
	printf("\n\n\t\t储户存单：");
	printf("--------------------\n");
	fflush(stdin);
	gets(hu[A].idnum);
	printf("--------------------\n");
	printf("\n\t\t姓名：");
	printf("--------------------\n");
	fflush(stdin);
	gets(hu[A].name);
	printf("--------------------\n");
	printf("\n\t\t储户密码（6位）：");
	printf("--------------------\n");
	for(i=0;i<6;i++){
		fflush(stdin);
		hu[A].password[i]=getch();
		printf("*");
	//	scanf("%d",&hu[A].password[i]);
	} 
	
	do{
		printf("--------------------\n");
		printf("请输入省份证号码(18位)：");
		printf("--------------------\n");
		fflush(stdin);
		gets(hu[A].idnumber);
		if(strlen(hu[A].idnumber)!=18)//strlen 代表的意思
		printf("\n------------------------------------------------------------\n");
		printf("\n\t\t输入错误！\n\t\t身份证请输入18位数字或者字母\n");
		printf("\n--------------------\n");
		for(i=0;i<A;i++)
		if(strcmp(hu[A].idnumber,hu[i].idnumber)==0&&strcmp(hu[A].name,hu[i].name)==0) 
		break;

		  	 
	}
	while(((strlen(hu[A].idnumber)!=18)||(strcmp(hu[A].idnumber,hu[i].idnumber)==0))&&(strcmp(hu[A].name,hu[i].name)!=0) );
	
	printf("------------------------------------------------------------\n");
	printf("输入存储的金额：");
	printf("------------------------------------------------------------\n");
	fflush(stdin);
	scanf("%lf",&hu[A].cunkuan);
	
	fprintf(fchuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[A].idnum,hu[A].name,hu[A].idnumber,hu[A].password,hu[A].cunkuan);
	A++;
	printf("------------------------------------------------------------\n");
	printf("是否继续是(y)/否(n)?\n");
	printf("------------------------------------------------------------\n");
	fflush(stdin);
	scanf("%c",&ch); 
	}while(ch=='y'||ch=='Y');
	printf("------------------------------------------------------------\n");
	printf("存入成功！\n");
	printf("------------------------------------------------------------\n");
	system("cls");
	fclose(nchuhu);
	fclose(fchuhu);
}


//登录 
void signUp()
{
	FILE *nchuhu=fopen("D:/atm.txt","r");
	FILE *fchuhu=fopen("D:/atm.txt","a");
	int i;
	if((nchuhu=fopen("D:/atm.txt","r"))==NULL) printf("No files, system created\n"); 
	do{
	 system("cls");
	date();//显示当前日期 
	printf("------------------------------------------------------------\n");
	printf("\n\n\t\tPlease enter the information of the new depositor：\n");
	printf("------------------------------------------------------------\n");
	fscanf(nchuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[A].idnum,hu[A].name,hu[A].idnumber,hu[A].password,&hu[A].cunkuan); 
	printf("------------------------------------------------------------\n");
	printf("\n\n\t\tDepositor's certificate of deposit：\n");
	printf("------------------------------------------------------------\n");
	fflush(stdin);
	gets(hu[A].idnum);
	printf("------------------------------------------------------------\n");
	printf("\n\t\tname：\n");
	printf("------------------------------------------------------------\n");
	fflush(stdin);
	gets(hu[A].name);
	printf("------------------------------------------------------------\n");
	printf("\n\t\tUser Password (6 digits)：\n");
	printf("------------------------------------------------------------\n");
	for(i=0;i<6;i++){
		fflush(stdin);
		hu[A].password[i]=getch();
		printf("*");
	//	scanf("%d",&hu[A].password[i]);
	} 
	
	do{
		printf("------------------------------------------------------------\n");
		printf("Please enter the provincial card number (18 digits)：\n\n");
		printf("------------------------------------------------------------\n");
		fflush(stdin);
		gets(hu[A].idnumber);
		if(strlen(hu[A].idnumber)!=18)//strlen 代表的意思
		{
			printf("--------------------------------------------------------------------------\n");
			printf("\n\t\tINPUT ERROR!\n\t\tPlease enter 18 digits or letters for your ID card\n");
			printf("--------------------------------------------------------------------------\n");
			continue;
		}
		for(i=0;i<A;i++)
		if(strcmp(hu[A].idnumber,hu[i].idnumber)==0&&strcmp(hu[A].name,hu[i].name)==0) 
		break;
		
		if(i<A) 
		printf("------------------------------------------------------------\n");
		  printf("\n\n\t\t\n\n\t\tPlease re-enter the provincial card number：\n");
		  printf("------------------------------------------------------------\n");
		  	 
	}while(((strlen(hu[A].idnumber)!=18)||(strcmp(hu[A].idnumber,hu[i].idnumber)==0))&&(strcmp(hu[A].name,hu[i].name)!=0) );
	
	printf("------------------------------------------------------------\n");
	printf("Enter the amount saved：\n");
	printf("------------------------------------------------------------\n");
	fflush(stdin);
	scanf("%lf",&hu[A].cunkuan);
	printf("----------------------------------------------------------------------------------------------\n");
	fprintf(fchuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[A].idnum,hu[A].name,hu[A].idnumber,hu[A].password,hu[A].cunkuan);
	printf("----------------------------------------------------------------------------------------------\n");
	A++;
	printf("Is it still (Y)/No (N) ?\n");
	fflush(stdin);
	char ch;
	scanf("%c",&ch); 
	}while(ch=='y'||ch=='Y');
	printf("------------------------------------------------------------\n");
	printf("Deposit successful！\n\n");
	printf("------------------------------------------------------------\n");
//	system("pause");
	system("cls");
	fclose(nchuhu);
	fclose(fchuhu);	
}




//********************************************************************************************************************
//验证存单号或密码 
int yanzheng(){
	FILE *fchuhu=fopen("D:/atm.txt","r");
	int count=0;
	char id[9];
	for(i=0;i<=100;i++){
		fscanf(fchuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,&hu[i].cunkuan);
	}
	do{
		system("cls");
			    printf("\n\n\n\t\t$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$\n");
				printf("\t\t|#|                                                          |#|\n");
				printf("\t\t|#|                    ☆☆☆☆☆☆☆☆☆☆                  |#|\n");
				printf("\t\t|#|                    ☆                ☆                  |#|\n");
				printf("\t\t|#|             ☆   存单号或者密码有误自动返回   ☆         |#|\n");
				printf("\t\t|#|                    ☆                ☆                  |#|\n");
				printf("\t\t|#|                    ☆☆☆☆☆☆☆☆☆☆                  |#|\n");
				printf("\t\t|#|                                                          |#|\n");
				printf("\t\t$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$\n");
				printf("------------------------------------------------------------\n");
		printf("\n\n\n\t\t      请输入您的存单号：  ");
		printf("------------------------------------------------------------\n");
		scanf("%s",id);
		printf("------------------------------------------------------------\n");
		printf("\n\n\n\t\t      请输入您的密码：  ");
		printf("------------------------------------------------------------\n");
		for(i=0;i<6;i++){
			fflush(stdin);
		password[i]=getch();
			printf("*");
		} 
		password[6]='\0';
		fflush(stdin);
		scanf("%c",&ch);
		printf("\n\n\t\t");
		for(i=0;i<99;i++){
			if(strcmp(id,hu[i].idnum)==0&&strcmp(password,hu[i].password)==0){
				fclose(fchuhu);
				return 0;
			}
		}
	
		
	}while(count==0);
	fclose(fchuhu);
	//return count;
}

int cheking()
{
	FILE *fchuhu=fopen("D:/atm.txt","r");
	int count=0;
	char id[9];
	for(i=0;i<=100;i++){
		fscanf(fchuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,&hu[i].cunkuan);
	}
	do{
		system("cls");
			    printf("\n\n\n\t\t$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$\n");
				printf("\t\t|#|                                                                        |#|\n");
				printf("\t\t|#|                            ☆☆☆☆☆☆☆☆☆☆                        |#|\n");
				printf("\t\t|#|                            ☆                ☆                        |#|\n");
				printf("\t\t|#|The deposit slip number or password is returned automatically in error  |#|\n");
				printf("\t\t|#|                            ☆                ☆                        |#|\n");
				printf("\t\t|#|                            ☆☆☆☆☆☆☆☆☆☆                        |#|\n");
				printf("\t\t|#|                                                                        |#|\n");
				printf("\t\t$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$$\n");
				printf("------------------------------------------------------------\n");
		printf("\n\n\n\t\t  Please enter your deposit slip number：  \n");
		printf("------------------------------------------------------------\n");
		scanf("%s",id);
		printf("------------------------------------------------------------\n");
		printf("\n\n\n\t\t  Please enter your password：  \n");
		printf("------------------------------------------------------------\n");
		for(i=0;i<6;i++){
			fflush(stdin);
		password[i]=getch();
			printf("*");
		} 
		password[6]='\0';
		fflush(stdin);
		scanf("%c",&ch);
		printf("\n\n\t\t");
		for(i=0;i<99;i++){
			if(strcmp(id,hu[i].idnum)==0&&strcmp(password,hu[i].password)==0){
				fclose(fchuhu);
				return 0;
			}
		}	
	}while(count==0);
	fclose(fchuhu);
	return count;
}



//********************************************************************************************************************
//********************************************************************************************************************
//存款
void cunkaun()
{
	FILE *fchuhu=fopen("D:/atm.txt","r");
	FILE *achuhu=fopen("D:/back.txt","w");
	char id[9];int i;
	printf("------------------------------------------------------------\n");
	if(!fchuhu) printf("不能打开文件：");
	printf("------------------------------------------------------------\n");
	if(!achuhu) printf("不能创建文件");
	printf("------------------------------------------------------------\n");
	for(i=0;i<=100;i++){
	fscanf(fchuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,&hu[i].cunkuan);
	}	//
	int a;
		date();
		printf("------------------------------------------------------------\n");
		printf("\n\n\t\t##请再次输入并确认存单：\n");
		printf("------------------------------------------------------------\n");
		scanf("%s",id);
		for(i=0;i<=100;i++){
			if(strcmp(id,hu[i].idnum)==0){		
		   printf("\n\n"); 
	 		printf("\t\t||================================================================||\n");
	 		printf("\t\t||                           *存款金额*                           ||\n");
	 		printf("\t\t||================================================================||\n");
	 		printf("\t\t||                                                                ||\n");
	 		printf("\t\t||                                                                ||\n");
	 		printf("\t\t||         1、200        2、400        3、600        4、800       ||\n");
	 		printf("\t\t||                                                                ||\n");
	 		printf("\t\t||                                                                ||\n");
	    	printf("\t\t||         5、1000        6、2000        7、4000        8、6000   ||\n");
	 		printf("\t\t||                                                                ||\n");
	 		printf("\t\t||================================================================||\n");
	 		printf("\t\t||================================================================||\n");
	 		printf("------------------------------------------------------------\n");
	 		printf("\n\n\t\t\t请输入你的取款金额：\n");
	 		printf("------------------------------------------------------------\n");
	 		scanf("%d",&a);
	 		switch(a){
	 			case 1:{jin=200;
	 				 printf("\t\t\t存款%lf元",jin);
			     	printf("\n\n\n\t\t\t^^^^存款成功^^^^"); 
			    	hu[i].cunkuan+=jin;
			    	printf("\n\n\t\t\t$您的余额为：%lf",hu[i].cunkuan);
			    	fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
					break;
				 }
				 case 2:{jin=400;
	 			    printf("\t\t\t存款%lf元",jin);
			     	printf("\n\n\n\t\t\t^^^^存款成功^^^^");  
			    	hu[i].cunkuan+=jin;
			    	printf("\n\n\t\t\t$您的余额为：%lf",hu[i].cunkuan);
				    fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
					break;
				 }
				 case 3:{
				 	jin=600;
				 	 printf("\t\t\t存款%lf元",jin);
			     	printf("\n\n\n\t\t\t^^^^存款成功^^^^");  
			    	hu[i].cunkuan+=jin;
			    	printf("\n\n\t\t\t$您的余额为：%lf",hu[i].cunkuan);
			    	fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
					break;
				 }
				 case 4:{
				 		jin=800;
				  printf("\t\t\t存款%lf元",jin);
			     	printf("\n\n\n\t\t\t^^^^存款成功^^^^"); 
			    	hu[i].cunkuan+=jin;
			    	printf("\n\n\t\t\t$您的余额为：%lf",hu[i].cunkuan);
			    	fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
					break;
				 }
				 	 			case 5:{jin=1000;
	 			 printf("\t\t\t存款%lf元",jin);
			     	printf("\n\n\n\t\t\t^^^^存款成功^^^^"); 
			    	hu[i].cunkuan+=jin;
			    	printf("\n\n\t\t\t$您的余额为：%lf",hu[i].cunkuan);
			    	fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
					break;
				 }
				 case 6:{jin=2000;
	 			 printf("\t\t\t存款%lf元",jin);
			     	printf("\n\n\n\t\t\t^^^^存款成功^^^^"); 
			    	hu[i].cunkuan+=jin;
			    	printf("\n\n\t\t\t$您的余额为：%lf",hu[i].cunkuan);
				    fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
					break;
				 }
				 case 7:{
				 	jin=4000;
				  printf("\t\t\t存款%lf元",jin);
			     	printf("\n\n\n\t\t\t^^^^存款成功^^^^"); 
			    	hu[i].cunkuan+=jin;
			    	printf("\n\n\t\t\t$您的余额为：%lf",hu[i].cunkuan);
			    	fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
					break;
				 }
				 case 8:{
				 		jin=6000;
				 	 printf("\t\t\t存款%lf元",jin);
			     	printf("\n\n\n\t\t\t^^^^存款成功^^^^"); 
			    	hu[i].cunkuan+=jin;
			    	printf("\n\n\t\t\t$您的余额为：%lf",hu[i].cunkuan);
			    	fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
					break;
				 }
				 default:printf("\n\n\n\t\t\t您的选择金额不在服务范围内！！！\n\n\n\t\t\t请重新选择业务："); 
				 
			 }			
				fclose(fchuhu);
	            fclose(achuhu);
            	system("del D:/atm.txt");
              	rename("D:/back.txt","D:/atm.txt");//rename(旧的，新的） 
                break;		
				}
				}
}


void saveMoney()
{
		FILE *fchuhu=fopen("D:/atm.txt","r");
		FILE *achuhu=fopen("D:/back.txt","w");
		char id[9];int i;
		if(!fchuhu) printf("The file can not be opened：");
		if(!achuhu) printf("The file can not be created");
		for(i=0;i<=100;i++){
		fscanf(fchuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,&hu[i].cunkuan);
		}	
		int a;
			date();
			printf("------------------------------------------------------------\n");
			printf("\n\n\t\t##Please re-enter and confirm the certificate of deposit：");
			printf("------------------------------------------------------------\n");
			scanf("%s",id);
			for(i=0;i<=100;i++){
				if(strcmp(id,hu[i].idnum)==0){		
			   printf("\n\n"); 
		 		printf("\t\t||================================================================||\n");
		 		printf("\t\t||                       *Amount of deposit*                      ||\n");
		 		printf("\t\t||================================================================||\n");
		 		printf("\t\t||                                                                ||\n");
		 		printf("\t\t||                                                                ||\n");
		 		printf("\t\t||         1、200        2、400        3、600        4、800       ||\n");
		 		printf("\t\t||                                                                ||\n");
		 		printf("\t\t||                                                                ||\n");
		    	printf("\t\t||         5、1000        6、2000        7、4000        8、6000   ||\n");
		 		printf("\t\t||                                                                ||\n");
		 		printf("\t\t||================================================================||\n");
		 		printf("\t\t||================================================================||\n");
		 		printf("\n\n\t\t\tPlease enter your withdrawal amount：");
		 		scanf("%d",&a);
		 		switch(a){
		 			case 1:{jin=200;
		 				 printf("\t\t\tDeposit %lf yuan",jin);
				     	printf("\n\n\n\t\t\t^^^^Deposit success^^^^"); 
				    	hu[i].cunkuan+=jin;
				    	printf("\n\n\t\t\t$Your balance is:%lf yuan",hu[i].cunkuan);
				    	fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
						break;
					 }
					 case 2:{jin=400;
		 			    printf("\t\t\tDeposit %lf yuan",jin);
				     	printf("\n\n\n\t\t\t^^^^Deposit success^^^^");  
				    	hu[i].cunkuan+=jin;
				    	printf("\n\n\t\t\t$Your balance is:%lf yuan",hu[i].cunkuan);
					    fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
						break;
					 }
					 case 3:{
					 	jin=600;
					 	 printf("\t\t\tDeposit %lf yuan",jin);
				     	printf("\n\n\n\t\t\t^^^^Deposit success^^^^");  
				    	hu[i].cunkuan+=jin;
				    	printf("\n\n\t\t\t$Your balance is:%lf yuan",hu[i].cunkuan);
				    	fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
						break;
					 }
					 case 4:{
					 		jin=800;
					  printf("\t\t\tDeposit %lf yuan",jin);
				     	printf("\n\n\n\t\t\t^^^^Deposit success^^^^"); 
				    	hu[i].cunkuan+=jin;
				    	printf("\n\n\t\t\t$Your balance is:%lf yuan",hu[i].cunkuan);
				    	fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
						break;
					 }
					 	 			case 5:{jin=1000;
		 			 printf("\t\t\tDeposit %lf yuan",jin);
				     	printf("\n\n\n\t\t\t^^^^Deposit success^^^^"); 
				    	hu[i].cunkuan+=jin;
				    	printf("\n\n\t\t\t$Your balance is:%lf yuan",hu[i].cunkuan);
				    	fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
						break;
					 }
					 case 6:{jin=2000;
		 			 printf("\t\t\tDeposit %lf yuan",jin);
				     	printf("\n\n\n\t\t\t^^^^Deposit success^^^^"); 
				    	hu[i].cunkuan+=jin;
				    	printf("\n\n\t\t\t$Your balance is:%lf yuan",hu[i].cunkuan);
					    fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
						break;
					 }
					 case 7:{
					 	jin=4000;
					  printf("\t\t\tDeposit %lf yuan",jin);
				     	printf("\n\n\n\t\t\t^^^^Deposit success^^^^"); 
				    	hu[i].cunkuan+=jin;
				    	printf("\n\n\t\t\t$Your balance is:%lf yuan",hu[i].cunkuan);
				    	fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
						break;
					 }
					 case 8:{
					 		jin=6000;
					 	 printf("\t\t\tDeposit %lf yuan",jin);
				     	printf("\n\n\n\t\t\t^^^^Deposit success^^^^"); 
				    	hu[i].cunkuan+=jin;
				    	printf("\n\n\t\t\t$Your balance is:%lf yuan",hu[i].cunkuan);
				    	fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
						break;
					 }
					 default:printf("\n\n\n\t\t\tYour selection amount is not covered by the service！！！\n\n\n\t\t\tPlease re-select business：\n"); 
					 
				 }			
					fclose(fchuhu);
		            fclose(achuhu);
	            	system("del D:/atm.txt");
	              	rename("D:/back.txt","D:/atm.txt");//rename(旧的，新的） 
	                break;		
					}
					}
}



//*******************************************************************************************************************
//取款 
void qukaun()
{
	FILE *fchuhu=fopen("D:/atm.txt","r");
	FILE *achuhu=fopen("D:/back.txt","w");
	int i,a;
	char id[9];
	if(!fchuhu) printf("不能打开文件：");
	if(!achuhu) printf("不能创建新文件：");
	for(i=0;i<=100;i++){
	fscanf(fchuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,&hu[i].cunkuan);
	}

	 	date();
	 	printf("------------------------------------------------------------\n");
	 	printf("\n\n\t\t请再次输入并确认存单：");
	 	printf("------------------------------------------------------------\n");
	 	scanf("%s",id);
	 	for(i=0;i<=99;i++){
	 		if(strcmp(id,hu[i].idnum)==0&&id<hu[i].idnum){
	 	    printf("\n\n"); 
	     	printf("\t\t||================================================================||\n");
	 		printf("\t\t||                           *取款金额*                           ||\n");
	 		printf("\t\t||================================================================||\n");
	 		printf("\t\t||                                                                ||\n");
	 		printf("\t\t||                                                                ||\n");
	 		printf("\t\t||         1、200        2、400        3、600        4、800       ||\n");
	 		printf("\t\t||                                                                ||\n");
	 		printf("\t\t||                                                                ||\n");
	    	printf("\t\t||         5、1000        6、2000        7、4000        8、6000   ||\n");
	 		printf("\t\t||                                                                ||\n");
	 		printf("\t\t||================================================================||\n");
	 		printf("\t\t||================================================================||\n");
	 		printf("------------------------------------------------------------\n");
	 		printf("\n\n\t\t\t请输入你的取款金额：");
	 		printf("------------------------------------------------------------\n");
	 		scanf("%d",&a);
	 		if(a<jin)
	 		{
	 		switch(a){
	 			case 1:{jin=200;
	 				printf("\t\t\t取出%lf元",jin);
			     	printf("\n\n\n\t\t\t^^^^取款成功^^^^"); 
			    	hu[i].cunkuan-=jin;
			    	printf("\n\n\t\t\t$您的余额为：%lf",hu[i].cunkuan);
			    	fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
					break;
				 }
				 case 2:{jin=400;
	 				printf("\t\t\t取出%lf元",jin);
			     	printf("\n\n\n\t\t\t^^^^取款成功^^^^"); 
			    	hu[i].cunkuan-=jin;
			    	printf("\n\n\t\t\t$您的余额为：%lf",hu[i].cunkuan);
				    fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
					break;
				 }
				 case 3:{
				 	jin=600;
				 printf("\t\t\t取出%lf元",jin);
			     	printf("\n\n\n\t\t\t^^^^取款成功^^^^");  
			    	hu[i].cunkuan-=jin;
			    	printf("\n\n\t\t\t$您的余额为：%lf",hu[i].cunkuan);
			    	fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
					break;
				 }
				 case 4:{
				 		jin=800;
				 printf("\t\t\t取出%lf元",jin);
			     	printf("\n\n\n\t\t\t^^^^取款成功^^^^"); 
			    	hu[i].cunkuan-=jin;
			    	printf("\n\n\t\t\t$您的余额为：%lf",hu[i].cunkuan);
			    	fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
					break;
				 }
				 	 			case 5:{jin=1000;
	 				printf("\t\t\t取出%lf元",jin);
			     	printf("\n\n\n\t\t\t^^^^取款成功^^^^"); 
			    	hu[i].cunkuan-=jin;
			    	printf("\n\n\t\t\t$您的余额为：%lf",hu[i].cunkuan);
			    	fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
					break;
				 }
				 case 6:{jin=2000;
	 			printf("\t\t\t取出%lf元",jin);
			     	printf("\n\n\n\t\t\t^^^^取款成功^^^^"); 
			    	hu[i].cunkuan-=jin;
			    	printf("\n\n\t\t\t$您的余额为：%lf",hu[i].cunkuan);
				    fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
					break;
				 }
				 case 7:{
				 	jin=4000;
				 printf("\t\t\t取出%lf元",jin);
			     	printf("\n\n\n\t\t\t^^^^取款成功^^^^"); 
			    	hu[i].cunkuan-=jin;
			    	printf("\n\n\t\t\t$您的余额为：%lf",hu[i].cunkuan);
			    	fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
					break;
				 }
				 case 8:{
				 		jin=6000;
				 printf("\t\t\t取出%lf元",jin);
			     	printf("\n\n\n\t\t\t^^^^取款成功^^^^"); 
			    	hu[i].cunkuan-=jin;
			    	printf("\n\n\t\t\t$您的余额为：%lf",hu[i].cunkuan);
			    	fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
					break;
				 }
				 default:printf("\n\n\n\t\t\t您的选择金额不在服务范围内！！！\n\n\n\t\t\t请重新选择业务："); 
				 
			 }
		}
		else
		{
			printf("重新输入:\n");
		}
				fclose(fchuhu);
     	        fclose(achuhu);
             	system("del D:/atm.txt");
             	rename("D:/back.txt","D:/atm.txt");
				break;
			 }

		 }

}

void drawMoney()
{
	FILE *fchuhu=fopen("D:/atm.txt","r");
		FILE *achuhu=fopen("D:/back.txt","w");
		int i,a;
		char id[9];
		printf("------------------------------------------------------------\n");
		if(!fchuhu) printf("The file can not be opened：\n");
		printf("------------------------------------------------------------\n");
		if(!achuhu) printf("A new file can not be created：");
		printf("------------------------------------------------------------\n");
		for(i=0;i<=100;i++){
		fscanf(fchuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,&hu[i].cunkuan);
		}
	
		 	date();
		 	printf("------------------------------------------------------------\n");
		 	printf("\n\n\t\tPlease re-enter and confirm the certificate of deposit：");
		 	printf("------------------------------------------------------------\n");
		 	scanf("%s",id);
		 	for(i=0;i<=99;i++){
		 		if(strcmp(id,hu[i].idnum)==0&&hu[i].idnum){
		 	    printf("\n\n"); 
		     	printf("\t\t||================================================================||\n");
		 		printf("\t\t||                      *Withdrawal Amount*                       ||\n");
		 		printf("\t\t||================================================================||\n");
		 		printf("\t\t||                                                                ||\n");
		 		printf("\t\t||                                                                ||\n");
		 		printf("\t\t||         1、200        2、400        3、600        4、800       ||\n");
		 		printf("\t\t||                                                                ||\n");
		 		printf("\t\t||                                                                ||\n");
		    	printf("\t\t||         5、1000        6、2000        7、4000        8、6000   ||\n");
		 		printf("\t\t||                                                                ||\n");
		 		printf("\t\t||================================================================||\n");
		 		printf("\t\t||================================================================||\n");
		 		printf("------------------------------------------------------------\n");
		 		printf("\n\n\t\t\tPlease enter your withdrawal amount：\n");
		 		printf("------------------------------------------------------------\n");
		 		scanf("%d",&a);
		 		switch(a){
		 			case 1:{jin=200;
		 				printf("\t\t\tGets the %lf yuan",jin);
				     	printf("\n\n\n\t\t\t^^^^The withdrawal was successful^^^^"); 
				    	hu[i].cunkuan-=jin;
				    	printf("\n\n\t\t\t$Your balance is：%lf",hu[i].cunkuan);
				    	fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
						break;
					 }
					 case 2:{jin=400;
		 				printf("\t\t\tGets the %lf yuan",jin);
				     	printf("\n\n\n\t\t\t^^^^The withdrawal was successful^^^^"); 
				    	hu[i].cunkuan-=jin;
				    	printf("\n\n\t\t\t$Your balance is：%lf",hu[i].cunkuan);
					    fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
						break;
					 }
					 case 3:{
					 	jin=600;
					 printf("\t\t\tGets the %lf yuan",jin);
				     	printf("\n\n\n\t\t\t^^^^The withdrawal was successful^^^^");  
				    	hu[i].cunkuan-=jin;
				    	printf("\n\n\t\t\t$Your balance is：%lf",hu[i].cunkuan);
				    	fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
						break;
					 }
					 case 4:{
					 		jin=800;
					 printf("\t\t\tGets the %lf yuan",jin);
				     	printf("\n\n\n\t\t\t^^^^The withdrawal was successful^^^^"); 
				    	hu[i].cunkuan-=jin;
				    	printf("\n\n\t\t\t$Your balance is：%lf",hu[i].cunkuan);
				    	fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
						break;
					 }
					 	 			case 5:{jin=1000;
		 				printf("\t\t\tGets the %lf yuan",jin);
				     	printf("\n\n\n\t\t\t^^^^The withdrawal was successful^^^^"); 
				    	hu[i].cunkuan-=jin;
				    	printf("\n\n\t\t\t$Your balance is：%lf",hu[i].cunkuan);
				    	fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
						break;
					 }
					 case 6:{jin=2000;
		 			printf("\t\t\tGets the %lf yuan",jin);
				     	printf("\n\n\n\t\t\t^^^^The withdrawal was successful^^^^"); 
				    	hu[i].cunkuan-=jin;
				    	printf("\n\n\t\t\t$Your balance is：%lf",hu[i].cunkuan);
					    fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
						break;
					 }
					 case 7:{
					 	jin=4000;
					 printf("\t\t\tGets the %lf yuan",jin);
				     	printf("\n\n\n\t\t\t^^^^The withdrawal was successful^^^^"); 
				    	hu[i].cunkuan-=jin;
				    	printf("\n\n\t\t\t$Your balance is：%lf",hu[i].cunkuan);
				    	fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
						break;
					 }
					 case 8:{
					 		jin=6000;
					 printf("\t\t\tGets the %lf yuan",jin);
				     	printf("\n\n\n\t\t\t^^^^The withdrawal was successful^^^^"); 
				    	hu[i].cunkuan-=jin;
				    	printf("\n\n\t\t\t$Your balance is：%lf",hu[i].cunkuan);
				    	fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
						break;
					 }
					 default:printf("\n\n\n\t\t\tYour selection amount is not covered by the service！！！\n\n\n\t\t\tPlease re-select business：\n"); 
					 
				 }
					fclose(fchuhu);
	     	        fclose(achuhu);
	             	system("del D:\atm.txt");
	             	rename("D:/back.txt","D:/atm.txt");
					break;
				 }
	
			 }
}



//********************************************************************************************************************
//转账
void transfer()
{
	FILE *fchuhu=fopen("D:/atm.txt","r+");
	int i;
	char id[9];
	if(!fchuhu) printf("The file can not be opened：");

	for(i=0;i<=100;i++){
	fscanf(fchuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,&hu[i].cunkuan);
	}

	 	date();
	 	printf("------------------------------------------------------------\n");
	 	printf("\n\n\t\tPlease enter the deposit slip number of the transferor：");
	 	printf("------------------------------------------------------------\n");
	 	scanf("%s",id);
	 	for(i=0;i<=99;i++){
	 		if(strcmp(id,hu[i].idnum)==0){
	 	      printf("\n\n\t\tPlease enter the amount to be transferred：");
			   scanf("%lf",&jin);
			   printf("------------------------------------------------------------\n");
			   printf("\n\n\t\t  Please confirm the number：%lf",jin); 
			   printf("------------------------------------------------------------\n");
				 hu[i].cunkuan+=jin;
				 printf("------------------------------------------------------------\n");
				 printf("\n\n\nThe transfer was successful"); 
				 printf("------------------------------------------------------------\n");
				 	fprintf(fchuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[A].idnum,hu[A].name,hu[A].idnumber,hu[A].password,hu[A].cunkuan);
				 		fclose(fchuhu);
	fclose(fchuhu);

				 break;
			 }

		 }

	
} 

void zhuan()
{
		FILE *fchuhu=fopen("D:/atm.txt","r+");
		int i;
		char id[9];
		if(!fchuhu) printf("不能打开文件：");
	
		for(i=0;i<=100;i++){
		fscanf(fchuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,&hu[i].cunkuan);
		}
	
		 	date();
		 	printf("------------------------------------------------------------\n");
		 	printf("\n\n\t\t请输入转账人的存单号：");
		 	printf("------------------------------------------------------------\n");
		 	scanf("%s",id);
		 	for(i=0;i<=99;i++){
		 		if(strcmp(id,hu[i].idnum)==0){
		 			printf("------------------------------------------------------------\n");
		 	      printf("\n\n\t\t请输入要转账的金额：");
		 	      printf("------------------------------------------------------------\n");
				   scanf("%lf",&jin);
				   printf("------------------------------------------------------------\n");
				   printf("\n\n\t\t请确认数目：%lf",jin); 
				   printf("------------------------------------------------------------\n");
					 hu[i].cunkuan+=jin;
					 printf("------------------------------------------------------------\n");
					 printf("\n\n\n转账成功"); 
					 printf("------------------------------------------------------------\n");
					 	fprintf(fchuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[A].idnum,hu[A].name,hu[A].idnumber,hu[A].password,hu[A].cunkuan);
					 		fclose(fchuhu);
		fclose(fchuhu);
	
					 break;
				 }
	
			 }
}



//********************************************************************************************************************
//修改 
void xiugai()
{
	FILE *fchuhu=fopen("D:/atm.txt","r");
	FILE *achuhu=fopen("D:/back.txt","w");
	int j,i;
	char id[9];
	if(!fchuhu) printf("不能打开文件：");
	if(!achuhu) printf("不能创建新文件：");
	for(i=0;i<=100;i++){
	fscanf(fchuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,&hu[i].cunkuan);
	}

	 	date();
	 	printf("------------------------------------------------------------\n");
	 	printf("\n\n\t\t请再次输入并确认存单：");
	 	printf("------------------------------------------------------------\n");
	 	scanf("%s",id);
	 	for(i=0;i<=99;i++){
	 		if(strcmp(id,hu[i].idnum)==0){
	 			printf("------------------------------------------------------------\n");
	 		printf("请输入新的密码：\n");
	 		printf("------------------------------------------------------------\n");
	 			printf("\n\t\t储户密码（6位）：");
	 			printf("------------------------------------------------------------\n");
	for(j=0;j<6;j++){
		fflush(stdin);
		hu[i].password[j]=getch();
		printf("*");

	} 
               	printf("------------------------------------------------------------\n");
				 printf("\n\n\t\t新的密码：%s\n",hu[i].password);
				 printf("------------------------------------------------------------\n");
			 
			 printf("------------------------------------------------------------\n");
				 printf("\n\n\t\t修改成功"); 
				 printf("------------------------------------------------------------\n");
				 	fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[A].idnum,hu[A].name,hu[A].idnumber,hu[A].password,hu[A].cunkuan);
				 		fclose(fchuhu);
	fclose(achuhu);
system("pause");
	system("del D:/atm.txt");
	rename("D:/back.txt","D:/atm.txt");
				 break;
			 }

		 }
}

void updatePassword()
{
		FILE *fchuhu=fopen("D:/atm.txt","r");
		FILE *achuhu=fopen("D:/back.txt","w");
		int j,i;
		char id[9];
		if(!fchuhu) printf("The file can not be opened：\n");
		if(!achuhu) printf("A new file can not be created：");
		for(i=0;i<=100;i++){
		fscanf(fchuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,&hu[i].cunkuan);
		}
	
		 	date();
		 	printf("------------------------------------------------------------\n");
		 	printf("\n\n\t\tPlease re-enter and confirm the certificate of deposit：\n");
		 	printf("------------------------------------------------------------\n");
		 	scanf("%s",id);
		 	for(i=0;i<=99;i++){
		 		if(strcmp(id,hu[i].idnum)==0){
		 			printf("------------------------------------------------------------\n");
		 		printf("Please enter a new password：\n");
		 		printf("------------------------------------------------------------\n");
		 			printf("\n\t\tUser Password (6 digits)：");
		 			printf("------------------------------------------------------------\n");
		for(j=0;j<6;j++){
			fflush(stdin);
			hu[i].password[j]=getch();
			printf("*");
	
		} 
	               	printf("------------------------------------------------------------\n");
					 printf("\n\n\t\t新的密码：%s\n",hu[i].password);
				 printf("------------------------------------------------------------\n");
				 
				 printf("------------------------------------------------------------\n");
					 printf("\n\n\t\tModification successful"); 
					 printf("------------------------------------------------------------\n");
					 	fprintf(achuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[A].idnum,hu[A].name,hu[A].idnumber,hu[A].password,hu[A].cunkuan);
					 		fclose(fchuhu);
		fclose(achuhu);
        system("pause");
		system("del D:/atm.txt");
		rename("D:/back.txt","D:/atm.txt");
					 break;
				 }
	
			 }
}



//&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&
//查询信息 
void chaxun()
{
	FILE *fchuhu=fopen("D:/atm.txt","r");
	int i,n=0;
	char fnumb[9];
	system("cls");
	for(i=0;i<=100;i++)
	{
		fscanf(fchuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,&hu[i].cunkuan);
	}
	
	printf("\n\n●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●\n");
	printf("\n\n\n\t\t\t\t\t请输入你的存单号：");
	printf("\n\n●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●\n");
	
	scanf("%s",fnumb);
	printf("\n\n\n");
	printf("-------------------------------------\n");
	printf("\t\t\t\t\t您的个人信息如下：\n");
		printf("-------------------------------------\n");
	printf("\n\n");
	for(i=0;i<=99;i++)
		if(strcmp(fnumb,hu[i].idnum)==0)
		{
			printf("--------------------------------------------------------------------------------------------------------------------------------\n");
			printf("\n存单号：%s\t姓名：%s\t身份证：%s\t密码：%s\t存款金额：%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
				printf("----------------------------------------------------------------------------------------------------------------------------\n");
			n=1;
			fclose(fchuhu);
			system("pause"); 
            break; 
		}
    if(n==0) printf("此账单不存在！！！\n");
    fclose(fchuhu);
}

void enquiry()
{
		FILE *fchuhu=fopen("D:/atm.txt","r");
		int i,n=0;
		char fnumb[9];
		system("cls");
		for(i=0;i<=100;i++)
		{
			fscanf(fchuhu,"%s\t%s\t%s\t%s\t%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,&hu[i].cunkuan);
		}
		
		printf("\n\n●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●\n");
		printf("\n\n\n\t\t\t\t\t Please enter your deposit slip number：");
		printf("\n\n●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●●\n");
		scanf("%s",fnumb);
		printf("\n\n\n");
		printf("-------------------------------------------------------\n");
		printf("\t\t\t\t\tYour personal information is as follows：");
		printf("-------------------------------------------------------\n");
		printf("\n\n");
		for(i=0;i<=99;i++)
			if(strcmp(fnumb,hu[i].idnum)==0)
			{
				printf("---------------------------------------------------------------------------------------------------------------------------------------------------\n");
				printf("Certificate number：%s\tname：%s\tid card：%s\tpassord：%s\tAmount of deposit：%lf\n",hu[i].idnum,hu[i].name,hu[i].idnumber,hu[i].password,hu[i].cunkuan);
				printf("---------------------------------------------------------------------------------------------------------------------------------------------------\n");
				n=1;
				fclose(fchuhu);
				system("pause"); 
	            break; 
			}
	    if(n==0) printf("\nThis bill does not exist！！！\n");
	    fclose(fchuhu);
}



//********************************************************************************************************************
void date()
{//显示当前日期
	printf("当前日期：");
	system("date/t");
	printf("当前时间：");
	system("time/t"); 
}

void dateEnglish()
{
	printf("Current date：");
	system("date/t");
	printf("Current time：");
	system("time/t"); 
}

