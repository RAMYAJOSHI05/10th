# 10th
#include <stdio.h>
#include <stdlib.h>
struct BST
{
int data;
struct BST *left;
struct BST *right;
};
typedef struct BST NODE;
NODE* createtree(NODE *root, int data)
{
if (root == NULL)
{
NODE *temp;
temp = (NODE*) malloc (sizeof(NODE));
temp->data = data;
temp->left = temp->right = NULL;
return temp;
}
if (data < (root->data))
root->left = createtree(root->left, data);
else if (data > root->data)
root -> right = createtree(root->right, data);
return root;
}
void inorder(NODE *root)
{
if(root != NULL)
{
inorder(root->left);
printf("%d\t", root->data);
inorder(root->right);
}
}
void preorder(NODE *root)
{
if(root != NULL)
{
printf("%d\t", root->data);
preorder(root->left);
preorder(root->right);
}
}
void postorder(NODE *root)
{
if(root != NULL)
{
postorder(root->left);
postorder(root->right);
printf("%d\t", root->data);
}
}
NODE *search(NODE *root, int data)
{
if(root == NULL)
printf("\nElement not found");
else if(data < root->data)
root->left = search(root->left, data);
else if(data > root->data)
root->right = search(root->right, data);
else
printf("\nElement found is: %d", root->data);
return root;
}
void main()
{
int data, ch, i, n;
NODE *root = NULL;
while (1)
{
printf("\n1.Creation of Binary Search Tree");
printf("\n2.Inorder\n3.Preorder\n4.Postorder\n5.Search\n6.Exit");
printf("\nEnter your choice: ");
scanf("%d", &ch);
switch (ch)
{
case 1: printf("\nEnter N value: " );
scanf("%d", &n);
printf("\nEnter the values to create BST like(6,9,5,2,8,15,24,14,7,8,5,2)\n");
for(i=0; i<n; i++)
{
    scanf("%d", &data);
root = createtree(root, data);
}
break;
case 2: printf("\nInorder Traversal: \n");
inorder(root);
break;
case 3: printf("\nPreorder Traversal: \n");
preorder(root);
break;
case 4: printf("\nPostorder Traversal: \n");
postorder(root);
break;
case 5: printf("\nEnter the element to Search: ");
scanf("%d", &data);
root=search(root, data);
break;
case 6: exit(0);
default: printf("\nWrong Option");
break;
}
}
}



OUTPUT:
1.Creation of Binary Search Tree
2.Inorder
3.Preorder
4.Postorder
5.Search
6.Exit
Enter your choice: 1
Enter N value: 12
Enter the values to create BST like(6,9,5,2,8,15,24,14,7,8,5,2)
6 9 5 2 8 15 24 14 7 8 5 2
1.Creation of Binary Search Tree
2.Inorder
3.Preorder
4.Postorder
5.Search
6.Exit
Enter your choice: 2
Inorder Traversal:
2 5 6 7 8 9 14 15 24
1.Creation of Binary Search Tree
2.Inorder
3.Preorder
4.Postorder
5.Search
6.Exit
Enter your choice: 3
Preorder Traversal:
6 5 2 9 8 7 15 14 24
1.Creation of Binary Search Tree
2.Inorder
3.Preorder
4.Postorder
5.Search
6.Exit
Enter your choice: 4
Postorder Traversal:
2 5 7 8 14 24 15 9 6
1.Creation of Binary Search Tree
2.Inorder
3.Preorder
4.Postorder
5.Search
6.Exit
Enter your choice: 5
Enter the element to Search: 8
Element found is: 8
1.Creation of Binary Search Tree
2.Inorder
3.Preorder
4.Postorder
5.Search
6.Exit
Enter your choice: 5
Enter the element to Search: 10
Element not found
1.Creation of Binary Search Tree
2.Inorder
3.Preorder
4.Postorder
5.Search
6.Exit
Enter your choice: 6
