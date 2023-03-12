# Linked-list
/******************************************************************************

Welcome to GDB Online.
GDB online is an online compiler and debugger tool for C, C++, Python, Java, PHP, Ruby, Perl,
C#, OCaml, VB, Swift, Pascal, Fortran, Haskell, Objective-C, Assembly, HTML, CSS, JS, SQLite, Prolog.
Code, Compile, Run and Debug online from anywhere in world.

*******************************************************************************/
#include <iostream>

using namespace std;
class Node
{
    public:
    int data;
    Node *next;
};
class LinkedList
{
    Node *head;
    Node *tail;
    //int length;
    public:
    LinkedList()
    {
        head=NULL;
        tail=NULL;
        //length=1;
    }
    void insert(int data)
    {
        Node *newNode=new Node();
        newNode->data=data;
        newNode->next=NULL;
        Node *temp=newNode;
        if(head==NULL)
        {
            head=temp;
            tail=temp;
        }
        else
        {
            tail->next=temp;
            tail=temp;
           
        }
        //length++;
    }
        void prepend(int data)
        {
            Node *newNode=new Node();
            newNode->data=data;
            newNode->next=NULL;
            Node *temp=newNode;
            if(head==NULL)
            {
                head=temp;
                tail=temp;
            }
            temp->next=head;
            head=temp;
        }
    
    void insertAfter(int data,int value)
    {
        Node *newNode=new Node;
        newNode->data=data;
        newNode->next=NULL;
        Node *temp=head;
        while(temp!=NULL)
        {
            if(temp->data==value)
            {
                newNode->next=temp->next;
                temp->next=newNode;
            }
            temp=temp->next;
        }
        
    }
    void print()
    {
        Node *temp=head;
        while(temp!=NULL)
        {
            cout<<temp->data<<endl;
            temp=temp->next;
        }
    }
};
int main()
{
    
LinkedList *ll=new LinkedList;
ll->insert(1);
ll->insert(2);
ll->insert(3);
ll->prepend(4);
ll->insertAfter(5,1);
ll->insertAfter(7,2);
//ll->sort();
ll->print();
//ll->sort();
//ll->print1();
    return 0;
}
