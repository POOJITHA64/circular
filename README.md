# circular
#include<stdio.h>
#include<stdlib.h>
struct node
{
    int data;
    struct node*next;
}*newnode,*temp;
struct node*head=NULL;
struct node*tail=NULL;
void create()
{
    int value;
    int ch;
    do{
        newnode=(struct node*)malloc(sizeof(struct node));
        printf("enter the value\n");
        scanf("%d",&value);
        newnode->data=value;
        newnode->next=NULL;
        if(head==NULL)
        {
            head=newnode;
            tail=newnode;
            newnode->next=head;
        }
        else
        {
            tail->next=newnode;
            tail=newnode;
            tail->next=head;
        }
        printf("press 1 to continue,0 to exit\n");
        fflush(stdin);
        scanf("%d",&ch);
    }
    while(ch==1);
}
void display()
{
    printf("the created circular linked list\n");
    temp=head;
    while(temp->next!=head)
    {
        printf("%d",temp->data);
        temp=temp->next;
    }
}
void insert_beg()
{
    int value;
    newnode=(struct node*)malloc(sizeof(struct node));
    printf("enter the value\n");
    scanf("%d",&value);
    newnode->data=value;
    newnode->next=head;
    tail->next=newnode;
    head=newnode;
}
void insert_end()
{
    int value;
    newnode=(struct node*)malloc(sizeof(struct node));
    printf("enter the value\n");
    scanf("%d",&value);
    newnode->data=value;
    newnode->next=head;
    tail->next=newnode;
    tail=newnode;
}
void insert_pos()
{
    int value,i,pos;
    temp=head;
    newnode=(struct node*)malloc(sizeof(struct node));
    printf("enter the value\n");
    scanf("%d",&value);
    printf("enter the position\n");
    scanf("%d",&pos);
    for(i=0;i<pos-1;i++)
    {
        newnode->data=value;
        newnode->next=temp->next;
        temp->next=newnode;
    }
    void delete_beg()
    {
        temp=head;
        while(temp->next!=tail)
        {
            temp=temp->next;
        }
        temp->next=head;
        tail=temp;
    }
    void delete_end()
    {
        temp=head;
        while(temp->next!=tail)
        {
            temp=temp->next;
        }
        temp->next=head;
        tail=temp;
    }
    void delete_pos()
    {
        int i,pos;
        temp=head;
        printf("enter the position\n");
        scanf("%d",&pos);
        for(i=0;i<pos-1;i++)
        {
            temp=temp->next;
        }
        temp->next=temp->next->next;
    }
    void main()
    {
        int count=0,choice;
        while(choice<9)
        printf("operation on circular linked list\n");
        printf("1-create the circular list\n");
        printf("2-display\n,3-insert_beg()\n");
        printf("4-insert_end()\n,5-insert_pos()\n");
        printf("6-delete_beg()\n,7-delete_end()\n");
        printf("8-delete_pos\n");
        printf("%d",&choice);
        switch(choice)
        {
            case 1:
            create();
            break;
            case 2:
            display();
            break;
            case 3:
            insert_beg();
            break;
            case 4:
            insert_end();
            break;
            case 5:
            insert_pos();
            break;
            case 6:
            delete_beg();
            break;
            case 7:
            delete_end();
            break;
            case 8:
            delete_pos();
            break;
            default:
            printf("enter wrong");
            break;
        }
    }
}
