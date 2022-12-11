# print_reverse_LL
print_reverse_LL
#include<iostream>
using namespace std;
class Node
{
    public:
    int data;
    Node* next;
    Node(int data)
    {
        this->data=data;
        next=NULL;
    }
};
Node* input()
{
    int data;
    cin>>data;
    Node* head=NULL;
    Node* tail=NULL;
    while(data!=-1)
    {
        Node* newNode=new Node(data);
        if(head==NULL)
        {
            head=newNode;
            tail=newNode;
        }
        else
        {
            tail->next=newNode;
            tail=tail->next;
        }
        cin>>data;
    }
    return head;
}
void print(Node* head)
{
    Node* temp=head;
    while(temp!=NULL)
    {
        cout<<temp->data<<" ";
        temp=temp->next;
    }
}
void print_reverse(Node* head)
{

    if(head==NULL)
    {
    
        return ;
    }
    else
    {
        print_reverse(head->next);
        cout<<head->data<<" ";
    }
        

}
int main()
{
    Node* head=input();
    print_reverse(head);
}
