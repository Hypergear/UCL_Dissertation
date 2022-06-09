## Method
To approach the goal of identify the vulnerability of the STC network, author firstly introduce the key concepts and terminology in this study. Secondary, we assess the shortage of bandwidth due to the nature growth of internet services demand. Subsequently, a framework of STC data flow and various of centrality analysis were proposed to identify the potential influential path/landing station. Finally, a STC improvement scenario in southern pacific ocean is described.

### Method selection and key concepts
Graph_intro.md

### Bandwidth shortage
Before processing any proper analysis, some of the bandwidth information in the raw dataset are not publicly released. To assign the bandwidth attribution into each edge, the value of bandwidth in needed. To overcome the problem of missing data in bandwidth, author decided to employ Butter's law of bandwidth to predict the transmission capacity that can be carried within STC. Since in the context of STC, optical fiber is the most fundamental and essential material to communicate photonic information. Similar to the Moore's law, Butter's law is the observation that the amount of information can be transmitted through the optical fiber has been doubling every 9 months thanks to the development of new technologies such as wavelength-division multiplexing.(@hadaway_2016_16)(@buttle_2014_internet)

$ n_i = n_0\times2^{(y_i-y_0)/T} $

Where $n_0$ is the initial bandwidth throughput in the year $ y_0$, T is a constant reference to the number of years needed to double the bandwidth throughput. The value of $n_i$ is the resultant bandwidth in the year $y_i$, thus its logarithmic value shows a linear dependency on $n_0$. 

### Policy-Based Routing

The path between the origin and destination in a network could either be manually selected to a static node, or adaptively changed based on the algorithm. The routing decisions changes dynamically based on the current information within the network, such as current network topology, traffic load, latency. (@medhi_2017_network) The first priority for all the routing algorithm is to prevent the deadlock, thus the optimal routing strategy aims to achieve maximum efficiency by minimizing the routing cost.(@duato_2003_chapter) Considering an undirected graph(G) with N nodes and M edges, where each edge is assigned to a weight to represent a physical property of 'distance'. The target is to find a route between two nodes alone a set of edges, therefore the sum of weights under this route is minimum upon all the route choices. The routing algorithm to mathematically discover the best route is called shortest-path algorithm. There are four types of weight property applied to the edges into their investigation, they are: Simple, Spatial length, Budget cost, Bandwidth capacity. The detailed summary of description can be found in Table %^%^%+1

| Property | Symbol | Explain | Application |
|---|---|---|---|
| Simple | $C^S$ | Each edge weight is assigned to value of 1 | The path where data flows through with minimum number of edges along the way. |
| Spatial length | $C^L$ | The edge weight is the actual length of STC between the landing stations | As the distance is directly proportional to the time, the route with shortest length in STC gives the minimum time taken for data to travel between landing stations. |
| Budget cost | $C^C$ | The edge weight is average cost of deployment based on the length | STC owner recovers the cost of deployment by charging the money from the local internet services providers(ISP). A STC may be preferred by ISP due to its low charging price. |
| Bandwidth capacity | $C^B$ | The edge weight is the maximum data throughout capacity | Each STC is labeled to a design bandwidth capacity, it is the theoretical ability of data carriage. It is useful while users are sending large size file via STC. |

###### Table. %^%^%N. Edge properties

### Network Analysis
To analysis such complex network of the combination between large number of nodes and edges, the analysis boundary is not only the physical connection of STC also an abstract quantitative network to deal with the communication between the landing stations(node) via the STCs(edge). 

As the weakness may either occur on the under water STC or the cable landing stations, those locations in the global STC network with the high value of centrality are gains more interest than others. The node with high centrality referred to the how the importance of an actor plays in a topological network structure.(@hoffman_2021_methods) There are two centrality measurments are employed in this investgation: Degree centrality, betweenness centrality - The detailed strength and weakness can be found in Table %^%^%+1.

| Concept | Definition | Explain | Application |
|---|---|---|---|
| Degree centrality | The count number for edge directly connect to the node(Sharma and Surolia, 2013) | A node with higher degree of edge acts as the more central node of a network | Degree centrality shows how many nodes can be directly reached by such node, even though this node might be far off on the boundary of this network |
| Betweenness centrality | $\delta_s(E)=\sum_{(x,y)\in E} \frac{\sigma_{xy}(E)}{\sigma_{xy}} $(Hansen, Shneiderman and Himelboim, 2019) | The node plays as a hot spot role in many shortest paths | If all the information must pass through a node before reaching the destination, this node is the most important as the success of the communication is depend on it. But betweenness centrality is compute intensive large scale network |
###### Table. %^%^%N. Network analysis compare

### Network optimization

To overcome the problem of STC incidents, reroute the data flow to an alternative or secondary infrastructure would provide less performed but functional internet services. If the country/region only consists one STC connection, such countries are considered to belong to high vulnerable to STC failure due to its low redundancy. South pacific ocean has been know by its isolation to the majority of the world, the deployment of STC is not as well-developed as the rest of the world. This makes the countries(such as Tonga) extremely vulnerable and dependent to its only STC to communicate with rest of the world, but this could be mitigated by laying additional STC cables to increase its network redundancy. (@laporte_2015_chapter) inspect a similar issue from Chinese postman problem(CPP) and provides an idea from another perspective. 

```
BEGIN
1. Check for Solvability
2. Find imbalanced nodes
3. Find additional paths
4. Insert additional paths
5. Specifying the Euler Tour
END
```
###### Pseudocode of Chinese postman problem(Source: @tum_2015_the)

CPP indicates additional edge needed to form a Euler circuit graph, which can a walk can visits every edge exactly once by starting from any given node.(@tan_2005_chinese) Thus the each node must a positive number of pairs of edges to provide the route for incoming and outgoing path. This provides a baseline of one STC redundancy for each landing station.

Meanwhile, over-redundant is the by-product of the CPP which produced unnecessary edge to satisfy the CPP algorithm. Eventhough redundant path gives more robust network topology, it also brings extra cost for construction. Here author presents rich-club coefficient which describes the connectivity between the node with high degree centrality and author assumed that the connectivity of a higher degree node is naturally in a geographical advantage. (@ma_2015_richcores)
\[\phi(k) = \frac{2 E_k}{N_k (N_k - 1)}\]










missing data prediction 
    Butter's law to estimate the bandwidth capacity of the submarine cable. 
    Assess the risk of the demand-supply gap in the global internet bandwidth under Edholm's law of bandwidth

Route options -> Shortest path
    node
        最少的交换点
    length
        最快的距离
    cost
        ISP最少的费用
    bandwidth
        大文件传输速度


Centrality
    Degree centrality
    Betweenness

Additional new route
    Chinese postman
    rich club