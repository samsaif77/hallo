#include <iostream>
using namespace std;

struct node
{
    int value;
    node *next;
};
node *head = NULL;
// insert function **********
void insertNode(int data)
{
    node *newnode;
    node *last;

    newnode = new node; //  انشاء عقده جديده
    newnode->value = data;
    newnode->next = NULL;
    if (head == NULL)
    {
        head = newnode;
    }
    else
    {
        last = head;
        while (last->next != NULL)
        {
            last = last->next;
        }
        last->next = newnode;
        newnode->next = NULL;
    }
}
void display()
{
    node *lamp;
    if (head == NULL)
    {
        cout << "linked list is empty";
    }
    else
    {
        lamp = head;
        while (lamp ->next != NULL)
        {
            cout << lamp->value << endl;
           lamp= lamp->next;
        }
      //  cout << lamp->value << endl;
    }
}
int main()
{
    insertNode(20);
    insertNode(5);
    insertNode(15);
    insertNode(3);
    display();
    cout << "linked list \n";

    return 0;
}
