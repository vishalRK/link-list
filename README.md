#include<stdio.h>
#include<conio.h>
struct sll
{
	int data;
	struct sll*next;
	
};
struct sll* create(struct sll *p,int d)
{
	p=(struct sll*)malloc(sizeof(struct sll));
	 p->data=d;
	 p->next=NULL;
	 
		printf("\n\n\n%d -->%d ||",p->data,p);
	return p;
}
struct sll * insertatstart(struct sll*h ,struct sll*p)
{
	if(h==NULL)
	{
	  
	  printf("ll is empty:\t%d",h);
	  h=p;
	  
	}
	else
	{
		
		
		printf("ll is not empty%d",h);
		p->next=h;
		h=p;
		
	}
	return h;
}
struct sll* insertatend(struct sll*h,struct sll*p)
{
	struct sll* temp;
	temp=NULL;
	if(h==NULL)
	{
		h=p;
	}
	else
	{
		temp=h;
		while(temp->next!=NULL)
		{
			temp=temp->next;
		}	
		temp->next=p;
		
	}
	return h;
}
struct sll* insertafter(struct sll *h,struct sll *p)
{
	struct sll *temp;
	temp=NULL;
	int flag=0;
	
	int key;
	printf("\n enter a Key::");
	scanf("%d",&key);
	
	if(h==NULL)
	{
		printf("\nlink list is empty::");
		h=p;
		printf("\n your node is now first node of LL");
		
	}
	else
	{
		printf("\n ll is not empty :");
		temp=h;
		while(temp!=NULL)
		{
			if(temp->data==key)
			{
				p->next=temp->next;
				temp->next=p;
				flag=1;
			}
			temp=temp->next;
			
		}
		
	}
	if(flag==0)
		{
			printf("key not found");
		}
		else
		{
			printf("key is found");
		}
	
	return h;
}
struct sll* deleteAtStart(struct sll*h)
{
	
	struct sll* temp;
	if(h==NULL)
	{
		printf("link list is empty:");
	}
	else
	{
		printf("link list is not empty:");
		
		temp=h;
		
		{
			h=h->next;
		}
		free(temp);
		
		
	}
	return h;
}		
		

struct sll* deleteAtEnd(struct sll *h)
{
	struct sll* dum;
	struct sll* temp;
	
	
	if(h==NULL)
	{
		printf("link list is empty");
		
	}
	else
	{
		printf("link list not empty");
		dum=NULL;
	    temp=h;
	    while((temp->next)->next!=NULL)
	    {
	    	temp=temp->next;
	    	
		}
		dum=temp->next;
		printf("\n\n%d will now be deleted",dum->data);
		free(dum);
		temp->next=NULL;
		return h;
		
	}
}
void displayL(struct sll*h)
{
	struct sll*temp;
	temp=NULL;
	
	
	printf("\n\n\n");
	
	if(h==NULL)
	{
		printf("ll is empty::");
		
		
	}
	
	else
	{
		temp=h;
		while(temp!=NULL)
		{
			printf("%d -->%d ||",temp->data,temp);
			temp=temp->next;
		}
		printf("NULL");
		
		
	}
	
}
int main()
{
	struct sll *p,*h;
	 int d;
	 
	 int cnt;
	 h=NULL;
	 for(cnt=0;cnt<5;cnt++)
	 {
	printf("\n data number :");
	 scanf("%d",&d);
	 p=create(p,d);
	 h=insertatend(h,p);
	 
	 
	
	 
	 }
	 displayL(h);
	 
	 
	h=deleteAtEnd(h);
	h=deleteAtStart(h);
	
	 
	 printf("\ninsertafter section.....");
	 printf("\n enter  number :");
	
	 scanf("%d",&d);
	 p=create(p,d);
	
	  h=insertafter(h,p);
	 displayL(h);
	 return 0;
}
