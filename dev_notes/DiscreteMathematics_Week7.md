

# Week7 图论：图的基本概念

## 59-图的基本概念

 - 简单图simple graph：无环和重边的无向图
    - 以后讨论的基本都是 简单图
 - 完全图complete graph：任何两个不同结点间都有边关联的简单图，记做Kn
    - ![](https://raw.githubusercontent.com/mebusy/notes/master/imgs/DM_graph_complete_graph.png)
 - 赋权图 
    - 赋权图G=<V,E,f,g>
    - **结点权**函数：f:V→W
    - **边权**函数：g:E→W
    - W可以是任何集合，常为实数的子集 
    - ![](https://raw.githubusercontent.com/mebusy/notes/master/imgs/DM_graph_weighted_graph.png)


## 60-度和正则图

 - 端点v的度d(v)定义为关联端点v的边的数目
 - 有向图中，度分为出度(out-degree)和入度 (in-degree)
    - 出度d+(v)
    - 入度d-(v)
    - d(v)=d+(v)+d-(v)
 - ![](https://raw.githubusercontent.com/mebusy/notes/master/imgs/DM_graph_degree.png)
    - d(c) = 5


### 度的性质

 - 所有端点 度的总和为**偶数**，而且是边数目的 **两倍**
 - 有向图中出度的总和等于入度的总和
 - **奇数度** 结点必为 **偶数**个（反证法可证）
 - 自然数序列(a1 ,a2 ,…an)是某个图的度序列 当且仅当序列中所有数的总和为偶数
    - 如果你有一个序列， 它的所有的数的总和是一个偶数的话，那么我们就可以，必然可以依据它这个度序列， 来做出一个图来，可以对应一个图。
    - 反过来也是一样
 - 1 度的顶点称为**悬挂点**(pendant node) 


### 正则图(regular graph)

 - 所有顶点的度均相同的图称为**正则图**，按照 顶点的度数k称作**k-正则图**
 - ![](https://raw.githubusercontent.com/mebusy/notes/master/imgs/DM_graph_regular_graph.png)
    - 1st one is 3-正则图
    - 2nd one is 2-正则图
    - last one is 4-正则图 
 - K<sub>n</sub> 是n-1正则图 
    - last one is complete graph K₅
    - 对于每一个完全图来说，它肯定都是一个正则图

## 61-子图与同构图

### 子图(subgraph)

![](https://raw.githubusercontent.com/mebusy/notes/master/imgs/DM_graph_subgraph.png)

 - G1=<V1 ,E1>, G2=<V2 ,E2> 
    - V1 ⊆ V2 , E1 ⊆ E2，称G1是G2的**子图**
    - 如果G1≠G2，则G1是G2的**真子图**
 - 生成子图spanning subgraph
    - 如果G1是G2的子图，且V1=V2
    - G1 只是少了若干条 边
    - 红图 是 蓝图的spanning subgraph 

### 补图

 - G1 ,G2互为补图：
    - V1=V2 , E1∩E2=∅ ,  <V1 ,E1∪E2>是完全图 

![](https://raw.githubusercontent.com/mebusy/notes/master/imgs/DM_graph_Complement_graph.png)

### 图的同构isomorphic

 - G1=<V1 ,E1>, G2=<V2 ,E2>
    - |V1 |=|V2 |, |E1 |=|E2 | 
        - 顶点的个数和边的条数， 要一致
    - 如果可以将V1中所有的结点一一对应地置 换为V2中的结点名后得到的图等于G2
        - 在存在一个双射函数，它把这个V1映射为V2，同时 把E1变成E2
 - ![](https://raw.githubusercontent.com/mebusy/notes/master/imgs/DM_graph_isomorphic_graph.png)
    - 把这个五角星 的这个顶点啊，最顶上这个顶点 最上面的顶点把它挪，挪到最下方。 然后把这个左边这个顶点，挪，挪到右下方的话，我们就会发现，如果经过这样的一个操作， 移动或者说叫做置换的话，那么它就会变成一个五边形了。 
 - 不同构的图：化学中的同分异构体
    - 分子式相同而结构和性质不同的化合物之间 互称同分异构体

## 62-路径与连通性

### 路径(walk)与通路(path)
 
 - 如果拟路径中的边各不相同，称作**路径**
 - 如果路径中的顶点各不相同，称作**通路**
    - 不能够允许包含相同的顶点
 - v1=vl 的路径称为**闭路径**
 - v1=vl 的通路称作**回路**


### 路径与通路性质

 - **路径和通路定理**
    - 在有n个顶点的图G中，如果有顶点u到v的 拟路径，那么u到v必有**路径**，并且必有长度**不大于n-1的通路**
    - (考虑拟路径中重复顶点的压缩)
 - **闭路径和回路定理**
    - 在有n个顶点的图G中，如果有顶点v到v的 闭路径，那么必定有一条从v到v的长度不大于n的**回路**


## 63-连通性

 - u**可达**v(accessible)
    - u=v，或者存在一条u到v的路径
 - **连通**的**无向图**connected
    - 无向图中**任意**两个顶点都是**可达**的
 - **强连通**的**有向图**
    - 有向图中**任意**两个顶点都是**互相可达**的
    - u可达v , v可达u 
    - ![](https://raw.githubusercontent.com/mebusy/notes/master/imgs/DM_graph_connected_graph.png)
 - **单向连通**的**有向图**
    - **任意**两个顶点，**至少**从一个顶点到另一个是 **可达**的
 - **弱连通**的**有向图**
    - 将有向图**看作无向图**时是连通的 (右下角图)
    - ![](https://raw.githubusercontent.com/mebusy/notes/master/imgs/DM_graph_weak_connected_graph.png)
