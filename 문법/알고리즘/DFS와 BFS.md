## 📍 DFS와 BFS의 차이점 ❕

* DFS(Depth-First-Search)로 '깊이 우선 탐색'
* BFS(Breadth-First-Search)로 '너비 우선 탐색' <br>
❤ PPT로 DFS/BFS 그래프 예시 만들어서 올리기 !

### 코드 구현
```c
#include <stdio.h>
#include <stdlib.h>

#define MAX_SIZE 100

// 그래프 정점 구조체
typedef struct Node {
    int vertex;
    struct Node* next;
} Node;

// 그래프 구조체
typedef struct Graph {
    int numVertices;
    Node** adjLists;
    int* visited;
} Graph;

// 그래프 초기화
Graph* createGraph(int numVertices) {
    Graph* graph = (Graph*)malloc(sizeof(Graph));
    graph->numVertices = numVertices;
    graph->adjLists = (Node**)malloc(numVertices * sizeof(Node*));
    graph->visited = (int*)malloc(numVertices * sizeof(int));

    for (int i = 0; i < numVertices; ++i) {
        graph->adjLists[i] = NULL;
        graph->visited[i] = 0;
    }

    return graph;
}

// 정점에 연결된 간선 추가
void addEdge(Graph* graph, int src, int dest) {
    // 정점 dest를 정점 src에 연결
    Node* newNode = (Node*)malloc(sizeof(Node));
    newNode->vertex = dest;
    newNode->next = graph->adjLists[src];
    graph->adjLists[src] = newNode;

    // 정점 src를 정점 dest에 연결
    newNode = (Node*)malloc(sizeof(Node));
    newNode->vertex = src;
    newNode->next = graph->adjLists[dest];
    graph->adjLists[dest] = newNode;
}

// DFS 구현
void dfs(Graph* graph, int vertex) {
    Node* adjList = graph->adjLists[vertex];
    Node* temp = adjList;

    graph->visited[vertex] = 1;
    printf("Visited %d \n", vertex);

    while (temp != NULL) {
        int connectedVertex = temp->vertex;
        if (graph->visited[connectedVertex] == 0) {
            dfs(graph, connectedVertex);
        }
        temp = temp->next;
    }
}

// BFS 구현
void bfs(Graph* graph, int startVertex) {
    int queue[MAX_SIZE];
    int front = -1, rear = -1;

    // 시작 정점을 큐에 삽입
    queue[++rear] = startVertex;
    graph->visited[startVertex] = 1;

    while (front != rear) {
        // 큐에서 정점을 추출하여 방문
        int currentVertex = queue[++front];
        printf("Visited %d \n", currentVertex);

        Node* temp = graph->adjLists[currentVertex];
        while (temp) {
            int connectedVertex = temp->vertex;
            if (graph->visited[connectedVertex] == 0) {
                // 방문하지 않은 정점을 큐에 삽입
                queue[++rear] = connectedVertex;
                graph->visited[connectedVertex] = 1;
            }
            temp = temp->next;
        }
    }
}

int main() {
    Graph* graph = createGraph(6);

    // 그래프 정점과 간선 추가
    addEdge(graph, 0, 1);
    addEdge(graph, 0, 2);
    addEdge(graph, 1, 3);
    addEdge(graph, 2, 4);
    addEdge(graph, 2, 5);

    printf("DFS starting from vertex 0:\n");
    dfs(graph, 0);

    // visited 배열 초기화
    for (int i = 0; i < graph->numVertices; ++i) {
        graph->visited[i] = 0;
    }

    printf("\nBFS starting from vertex 0:\n");
    bfs(graph, 0);

    return 0;
}

```
