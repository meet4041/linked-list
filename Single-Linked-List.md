I had upload all the program related to single linked list.

1. **Node creation** 

#include <stdio.h>
#include <stdlib.h>

struct node
{

	int data;
	struct node *link;
};

int main()
{

	struct node *head = NULL;
	
	head = malloc(sizeof(struct node));
	head->data = 5;
	head->link = NULL;
	
	struct node *current = malloc(sizeof(struct node));
	current->data = 6;
	current->link = NULL;
	head->link = current;
	
	current = malloc(sizeof(struct node));
	current->data = 45;
	current->link = NULL;
	head->link->link = current;
	
	printf("%d \n", head->data);
	printf("%d \n", head->link->data);
	printf("%d \n", current->data);
	return 0;
}

2. **Count of Node**

void count_of_nodes(struct node *head)
{

	int count = 0;
	if (head == NULL)
		printf("Empty list\n");
	struct node *ptr = head;
	while (ptr != NULL){
		count++;
		ptr = ptr->link;
	}
	printf("Node : %d\n", count);
}

3. **List Printing**

void print_data(struct node *head)
{

	int count = 0;
	if (head == NULL)
		printf("Empty list\n");
	struct node *ptr = head;
	int i = 1;
	while (ptr != NULL)
	{
		printf("Node %d : %d\n", i, ptr->data);
		ptr = ptr->link;
		i++;
	}
}

4. **Insert the node at Beginning**.

struct node *addBegin(struct node *head, int data)
{

	struct node *ptr = malloc(sizeof(struct node));
	ptr->data = data;
	ptr->link = head;
	head = ptr;
	return head;
}

5. **Insert the node at End**.

struct node *addEnd(struct node *head, int data)
{

	struct node *temp, *ptr;
	ptr = head;
	temp = (struct node *)malloc(sizeof(struct node));
	temp->data = data;
	temp->link = NULL;
	while (ptr->link != NULL)
		ptr = ptr->link;
	ptr->link = temp;
	return head;		
}

6. **Insert the node in Middle**.

void *addMiddle*(struct node *head, int data, int pos)
{

	struct node *ptr = head;
	struct node *ptr2 = malloc(sizeof(struct node));
	ptr2->data = data;
	ptr2->link = NULL;
	pos--;
	while (pos != 1)
	{
		ptr = ptr->link;
		pos--;
	}
	ptr2->link = ptr->link;
	ptr->link = ptr2;
}

7. **Delete the node at Beginning**.

struct node *deleteBegin(struct node *head)
{

	if (head == NULL;
		printf("List is empty\n");
	else
	{
		struct node *temp = head;
		head = head->link;
		free(temp);
		temp = NULL;
	}
	return head;
}

8. **Delete the node at End**.

struct node *deleteLast(struct node *head)
{

	if (head == NULL)
		printf("List is empty\n");
	else if (head->link == NULL)
	{
		free(head);
		head = NULL;
	}
	else
	{
		struct node *temp = head;
		struct node *temp2 = head;
		while (temp->link != NULL)
		{
			temp2 = temp;
			temp = temp->link;
		}
		temp2->link = NULL;
		free(temp);
		temp = NULL;
	}
	return head;
}


9. **Delete the node at Specific Location**.

void *deleteMiddle*(struct node **head, int pos)
{

	struct node *current = *head;
	struct node *previous = *head;
	if (*head == NULL)
		printf("List is empty\n");
	else if (pos == 1)
	{
		*head = current->link;
		free(current);
		current = NULL;
	}
	else
	{
		while (pos != 1)
		{
			previous = current;
			current = current->link;
			pos--;
		}
		previous->link = current->link;
		free(current);
		current = NULL;
	}
}

10. **Delete the entire**.

struct node *listDelete(struct node *head)
{

	struct node *temp = head;
	while (temp != NULL)
	{
		temp = temp->link;
		free(head);
		head = temp;
	}
	return head;
}

11. **Reverse the list**.

struct node *reverse_list(struct node *head)
{

	struct node *next = NULL;
	struct node *prev = NULL;
	while (head != NULL)
	{
		next = head->link;
		head->link = prev;
		prev = head;
		head = next;
	}
	head = prev;
	return head;
}





