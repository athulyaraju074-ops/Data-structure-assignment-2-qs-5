#include <stdio.h>
#include <stdlib.h>
#include <string.h>

#define MAX_CHILDREN 3
#define MAX_QUEUE 20

typedef struct Node {
    char name[30];
    int childCount;
    struct Node *child[MAX_CHILDREN];
} Node;

Node *createNode(const char *name) {
    Node *newNode = (Node *)malloc(sizeof(Node));
    strcpy(newNode->name, name);
    newNode->childCount = 0;
    for (int i = 0; i < MAX_CHILDREN; i++)
        newNode->child[i] = NULL;
    return newNode;
}

void addChild(Node *parent, Node *child) {
    if (parent->childCount < MAX_CHILDREN)
        parent->child[parent->childCount++] = child;
}

void levelOrder(Node *root) {
    Node *queue[MAX_QUEUE];
    int front = 0, rear = 0;
    queue[rear++] = root;

    printf("Level-order traversal:\n");
    while (front < rear) {
        Node *current = queue[front++];
        printf("%s ", current->name);
        for (int i = 0; i < current->childCount; i++)
            queue[rear++] = current->child[i];
    }
    printf("\n");
}

int main() {
    Node *CEO = createNode("CEO");
    Node *HR = createNode("HR");
    Node *Finance = createNode("Finance");
    Node *IT = createNode("IT");
    Node *Development = createNode("Development");
    Node *Testing = createNode("Testing");
    Node *Frontend = createNode("Frontend");
    Node *Backend = createNode("Backend");

    addChild(CEO, HR);
    addChild(CEO, Finance);
    addChild(CEO, IT);
    addChild(IT, Development);
    addChild(IT, Testing);
    addChild(Development, Frontend);
    addChild(Development, Backend);

    levelOrder(CEO);
    return 0;
}
