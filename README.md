# Hello-World

#include <stdio.h>
#include <stdlib.h>

/* run this program using the console pauser or add your own getch, system("pause") or input loop */

#include<stdio.h>
void main()
{
 char *Eng1[20]={"zero","one","two","three","four","five","six","seven",
   "eight","nine","ten","eleven","twelve","thirteen","fourteen","fifteen",
   "sixteen","seventeen","eighteen","nineteen"};
 char *Eng2[8]={"twenty","thirty","fourty","fifty","sixty","seventy","eighty","ninety"};
 int num;
 printf("请输入数字: ");
 scanf("%d",&num);
 printf("对应的英文为: ");
 if(num>=0&&num<=19)
  printf("%s\n",Eng1[num]);
 else if(num<100)
 {
  int s,y;
  s=num/10;
  y=num%10;
  printf("%s %s\n",Eng2[s-2],Eng1[y]);
 }
 else if(num<1000)
 {
  int b,s,y;
  b=num/100; 
  y=num%100;
  if(y>19)//十位有数 ，大于19 
  {
   s=(num%100)/10;
   y=(num%100)%10;
   if(y==0)
    printf("%s hundred and %s\n",Eng1[b],Eng2[s-2]);
   else
    printf("%s hundred and %s %s\n",Eng1[b],Eng2[s-2],Eng1[y]);
  }
  else if(y<=19&&y>9){
  	printf("%s hundred and %s\n",Eng1[b],Eng1[y]);
  } 
  else
   printf("%s hundred and %s\n",Eng1[b],Eng1[y]);
 }
 else if(num<20000)
 {
 	int a,b,c,d,e,f;
 	a=num/1000;
 	b=num%1000;
 	if(b>99) 
 	{
 		c=b/100;
		d=b%100;
		if(d>19)//十位有数
		{ 
		 e=d/10;//十位数 
		 f=d%10;//个位数 
		 if(f==0)
		 printf("%s thousand %s hundred and %s\n",Eng1[a],Eng1[c],Eng2[e-2]); 
		 else 
		 printf("%s thousand %s hundred and %s %s\n",Eng1[a],Eng1[c],Eng2[e-2],Eng1[f]); 
	    }
	    else if(d<19&&d>9)
	    printf("%s thousand %s hundred and %s\n",Eng1[a],Eng1[c],Eng1[d]);
	    else
		printf("%s thousand %s hundred",Eng1[a],Eng1[c]); 
    }
    else
    printf("%s thousand",Eng1[a]);
}
 else if(num<100000)
 {
 	int a,b,c,d,e,f,g,h;
 	a=num/10000;
 	b=num%10000;
 	if(b>999)//千位有数
	 {
	 	c=b/1000;
		d=b%1000;
		if(d>99){//百位有数
		 e=d/100;
		 f=d%100;
		 if(f>19){//十位有数
		   g=f/10;
		   h=f%10;
		   if(h==0)
		   printf("%s %s thousand %s hundred and %s\n",Eng2[a-2],Eng1[c],Eng1[e],Eng2[g-2]);
		   else
		   printf("%s %s thousand %s hundred and %s %s\n",Eng2[a-2],Eng1[c],Eng1[e],Eng2[g-2],Eng1[h]);
	    }
	    else if(f<19&&f>9)
	    printf("%s %s thousand %s hundred and %s\n",Eng2[a-2],Eng1[c],Eng1[e],Eng1[f]);
	    else
	    printf("%s %s thousand %s hundred\n",Eng2[a-2],Eng1[c],Eng1[e]);
	}
	else
	printf("%s %s thousand\n",Eng2[a-2],Eng1[c]);
	 } 
 }//在这之前全部正确 
 else if(num<1000000){
 	int a,b,c,d,e,f,g,h,i,j,p,q;
 	a=num/100000;//a hundred thousand
 	b=num%100000;
 	if(b>9999){
      p=b/1000;
      if(p>19){//jishi
      	c=b/10000;//几十 or十几thousand 
 	    d=b%10000; 
 	  if(d>999){
 	  	e=d/1000;
 	  	f=d%1000;
 	  	if(f>99){
 	  		g=f/100;
 	  		h=f%100;
 	  		if(h>19){
 	  			i=h/10;
 	  			j=h%10;
 	  			if(j==0)
 	  			printf("%s hundred and %s %s thousand %s hundred and %s\n",Eng1[a],Eng2[c-2],Eng1[e],Eng1[g],Eng1[i-2]);
 	  			else
 	  			printf("%s hundred and %s %s thousand %s hundred and %s %s\n",Eng1[a],Eng2[c-2],Eng1[e],Eng1[g],Eng2[i-2],Eng1[j]);
			   }
			else if(h<19&&h>9){
 	  			printf("%s hundred and %s %s thousand %s hundred and %s\n",Eng1[a],Eng2[c-2],Eng1[e],Eng1[g],Eng1[h]);
			}
			else
			printf("%s hundred and %s %s thousand %s hundred\n",Eng1[a],Eng2[c-2],Eng1[e],Eng1[g]);
		   }
		   else
		   printf("%s hundred and %s %s thousand\n",Eng1[a],Eng2[c-2],Eng1[e]);
	   }
	   else
	   printf("%s hundred and %s thousand\n",Eng1[a],Eng2[c-2]);
	 }
 	  
   else if(p<19&&p>9){//十几
 	    d=b%10000;  
   	if(d>999){
 	  	e=d/1000;
 	  	f=d%1000;
 	  	if(f>99){
 	  		g=f/100;
 	  		h=f%100;
 	  		if(h>19){
 	  			i=h/10;
 	  			j=h%10;
 	  			if(j==0)
 	  			printf("%s hundred and %s thousand %s hundred and %s\n",Eng1[a],Eng1[p],Eng1[g],Eng1[i-2]);
 	  			else
 	  			printf("%s hundred and %s thousand %s hundred and %s %s\n",Eng1[a],Eng1[p],Eng1[g],Eng2[i-2],Eng1[j]);
			   }
			else if(h<19&&h>9){
 	  			printf("%s hundred and %s thousand %s hundred and %s\n",Eng1[a],Eng1[p],Eng1[g],Eng1[h]);
			}
			else
			printf("%s hundred and %s thousand %s hundred and %s\n\n",Eng1[a],Eng1[p],Eng1[g],Eng2[i-2]);
		   }
		   else
		   printf("%s hundred and %s thousand\n",Eng1[a],Eng1[p]);
	   }
	   else
	   printf("%s hundred and %s thousand\n",Eng1[a],Eng1[p]);
	 }
}
	 else
	 printf("%s hundred  thousand\n",Eng1[a]);
	 
 }
else if(num<20000000){
 	int p,q,a,b,c,d,e,f,g,h,i,j,k,l,m,n;
 	p=num/1000000;
 	q=num%1000000;
	a=q/100000;//a hundred thousand
 	b=q%100000;
 	if(b>9999){
      p=b/1000;
      if(p>19){//jishi
      	c=b/10000;//几十 or十几thousand 
 	    d=b%10000; 
 	  if(d>999){
 	  	e=d/1000;
 	  	f=d%1000;
 	  	if(f>99){
 	  		g=f/100;
 	  		h=f%100;
 	  		if(h>19){
 	  			i=h/10;
 	  			j=h%10;
 	  			if(j==0)
 	  			printf("%s million %s hundred and %s %s thousand %s hundred and %s\n",Eng1[p],Eng1[a],Eng2[c-2],Eng1[e],Eng1[g],Eng1[i-2]);
 	  			else
 	  			printf("%s million %s hundred and %s %s thousand %s hundred and %s %s\n",Eng1[p],Eng1[a],Eng2[c-2],Eng1[e],Eng1[g],Eng2[i-2],Eng1[j]);
			   }
			else if(h<19&&h>9){
 	  			printf("%s million %s hundred and %s %s thousand %s hundred and %s\n",Eng1[p],Eng1[a],Eng2[c-2],Eng1[e],Eng1[g],Eng1[h]);
			}
			else
			printf("%s million %s hundred and %s %s thousand %s hundred\n",Eng1[p],Eng1[a],Eng2[c-2],Eng1[e],Eng1[g]);
		   }
		   else
		   printf("%s million %s hundred and %s %s thousand\n",Eng1[p],Eng1[a],Eng2[c-2],Eng1[e]);
	   }
	   else
	   printf("%s million %s hundred and %s thousand\n",Eng1[p],Eng1[a],Eng2[c-2]);
	 }
 	  
   else if(p<19&&p>9){//十几
 	    d=b%10000;  
   	if(d>999){
 	  	e=d/1000;
 	  	f=d%1000;
 	  	if(f>99){
 	  		g=f/100;
 	  		h=f%100;
 	  		if(h>19){
 	  			i=h/10;
 	  			j=h%10;
 	  			if(j==0)
 	  			printf("%s million %s hundred and %s thousand %s hundred and %s\n",Eng1[p],Eng1[a],Eng1[p],Eng1[g],Eng1[i-2]);
 	  			else
 	  			printf("%s million %s hundred and %s thousand %s hundred and %s %s\n",Eng1[p],Eng1[a],Eng1[p],Eng1[g],Eng2[i-2],Eng1[j]);
			   }
			else if(h<19&&h>9){
 	  			printf("%s million %s hundred and %s thousand %s hundred and %s\n",Eng1[p],Eng1[a],Eng1[p],Eng1[g],Eng1[h]);
			}
			else
			printf("%s million %s hundred and %s thousand %s hundred and %s\n\n",Eng1[p],Eng1[a],Eng1[p],Eng1[g],Eng2[i-2]);
		   }
		   else
		   printf("%s million %s hundred and %s thousand\n",Eng1[p],Eng1[a],Eng1[p]);
	   }
	   else
	   printf("%s million %s hundred and %s thousand\n",Eng1[p],Eng1[a],Eng1[p]);
	 }
}
	 else
	 printf("%s million %s hundred  thousand\n",Eng1[p],Eng1[a]);
 
 }
} 
