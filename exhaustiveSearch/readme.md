
# Exhaustive Search - 穷竭搜索

常用的求解工具：递归、栈、队列
常用的求解办法:DFS(回溯法)、BFS

## DFS
DFS从某个**状态**开始，根据特定的规则**转移状态**，直至无法转移(节点为空)，然后回退到之前一步状态，继续按照指定规则转移状态，直至遍历完所有状态。
以深度优先方式搜索解空间，并在搜索过程中用**剪枝函数**避免无效搜索。

**回溯法**包含了多类问题，模板类似。
**排列组合模板->搜索问题**

## BFS 

BFS 从某个状态开始，搜索所有可以到达的状态，转移顺序为:初始状态->只需一次转移就可到达的所有状态->只需两次转移就可到达的所有状态->...，所以对于同一个状态，BFS 只搜索一次，故**时间复杂度**为 $ O(states \times transfer\_methods)$. BFS 通常**配合队列**一起使用，搜索时先将状态加入到队列中，然后从队列顶端不断取出状态，再把从该状态可转移到的状态中尚未访问过的部分加入队列，直到队列为空或已找到解。因此 BFS 适合用于『由近及远』的搜索，比较适合用于**求解最短路径、最少操作**之类的问题

