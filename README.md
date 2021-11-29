# kholuutrunhom6
#include <stdio.h>
#include<stdlib.h>
static int p_p=0,b_p=0;
int p_r,b_r;
char p[10];
int random()
{
	return 1+(rand()*(3.4-0.5))/(1+RAND_MAX);
}
main()
{
	while (1>0){
	start:
	fflush(stdin);
    printf("\n0:Thoat chuong trinh\n");
    printf("                    Diem nguoi choi: %d\n                    Diem Bot: %d",p_p,b_p);
	printf("\nNhap vao (bua,keo,bao): ");
	fgets(p,sizeof(p),stdin);
	b_r=random(); 
	if (p[0]=='b'&&p[1]=='u'&&p[2]=='a') p_r=1; 
	if (p[0]=='b'&&p[1]=='a'&&p[2]=='o') p_r=3;
	if (p[0]=='k'&&p[1]=='e'&&p[2]=='o') p_r=2;
	if(p[0]=='0') exit(0);
	if (p[0]!='b'&&p[0]!='k') { printf("Vui long nhap bua,keo,bao!\n");goto start;}
	if (b_r==p_r) 
	{
		if (b_r==1) {
			printf("Bot: Bua!\nHoa!\n");
		}
		if (b_r==2) {
			printf("Bot: Keo!\nHoa!\n");
		}
		if (b_r==3) {
			printf("Bot: Bao!\nHoa!\n");
		}
	} else
	{
		if (b_r==1) 
		{
			if (p_r==2) {printf("Bot: Bua!\nThua!\n");b_p++; }
			if (p_r==3) {printf("Bot: Bua!\nThang!\n");p_p++; }	
		}
		if (b_r==2) 
		{
			if (p_r==1) {printf("Bot: Keo!\nThang!\n");p_p++; }
			if (p_r==3) {printf("Bot: Keo!\nThua!\n");b_p++; }	
		}
		if (b_r==3) 
		{
			if (p_r==1) {printf("Bot: Bao!\nThua!\n");b_p++; }
			if (p_r==2) {printf("Bot: Bao!\nThang!\n");p_p++; }	
		}
	}
 }
 
}