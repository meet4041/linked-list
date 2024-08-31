I had upload all the program related to Doubly linked list.

1. **Insert Into Empty Node** 

#include <stdio.h>
#include <stdlib.h>

struct node
{

	struct node *prev;
	int data;
	struct node *next;
};

struct node *insert_data(struct node *head, int data)
{

	if (head == NULL)
	{
		struct node *temp = malloc(sizeof(struct node));
		temp->prev = NULL;
		temp->data = data;
		temp->next = NULL;
		head = temp;
	}
	else
		printf("List is full\n");
	return head;
}

int main()
{

	struct node *head = NULL;
	int data = 45;
	head = insert_data(head, data);
	printf("%d ", head->data);
}

2. **Insert the node at Beginning**.

struct node *insert_at_begin(struct node *head, int data)
{

	struct node *temp = malloc(sizeof(struct node));
	temp->prev = NULL;
	temp->data = data;
	temp->next = head;
	head->prev = temp;
	head = temp;
	return head;
}

3. **Insert the node at End**.

void insert_at_end(struct node *head, int data)
{

	struct node *ptr = head;
	while (ptr->next != NULL)
		ptr = ptr->next;
	struct node *temp = malloc(sizeof(struct node));
	temp->prev = ptr;
	temp->data = data;
	temp->next = NULL
	ptr->next = temp;
}

4. **Insert the node in Middle**.

void insert_in_middle(struct node *head, int data, int pos)
{

	struct node *ptr = head;
	struct node *ptr1;
	struct node *temp = malloc(sizeof(struct node));
	temp->prev = NULL;
	temp->data = data;
	temp->next = NULL;
	pos--;
	while (pos != 1)
	{
		ptr = ptr->next;
		pos--;
	}
	ptr1=ptr->next;
	temp->prev = ptr;
	ptr->next = temp;
	temp->next = ptr1;
	ptr1->prev = temp;
}

5. **Delete the node at Beginning**.

struct node *delete_begin(struct node *head)
{

	struct node *temp = head;
	head = temp->next;
	head->prev=NULL;
	free(temp);
	temp = NULL;
	return head;
}

6. **Delete the node at End**.

void insert_at_end(struct node *head, int data)
{

	struct node *ptr = head;
	while (ptr->next != NULL)
		ptr = ptr->next;
	struct node *temp = malloc(sizeof(struct node));
	temp->prev = ptr;
	temp->data = data;
	temp->next = NULL;
	ptr->next = temp;
}


7. **Delete the node at Specific Location**.

struct node *delete_middle(struct node *head, int pos)
{

	struct node *ptr = head;
	struct node *temp;
	pos--;
	while (pos != 1)
	{
		pos--;
		ptr = ptr->next;
	}
	temp = ptr->next;
	ptr->next = temp->next;
	free(temp);
	temp = NULL;
	return head;
}

8. **Reverse the list**.

struct node * reverse(struct node *head)
{

	struct node *ptr1 = head;
	struct node *ptr2 = ptr1->next;
	ptr1->next = NULL;
	ptr1->prev = ptr2;
	while (ptr2 != NULL)
	{
		ptr2->prev = ptr2->next;
		ptr2->next = ptr1;
		ptr1 = ptr2;
		ptr2 = ptr2->prev;
	}
	head = ptr1;
	return head;
}





