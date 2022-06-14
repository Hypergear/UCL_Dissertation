## Method
To approach the goal of identify the vulnerability in the STC network, author firstly introduce the key concepts and terminologies in this study. Secondary, we assess the risk of bandwidth shortage due to the increasing bandwidth demand on internet services. Subsequently, a framework of STC data flow and various of centrality analysis were proposed to identify the potential influential path/landing station. Finally, a STC improvement scenario in southern pacific ocean is described.

### Method selection and key concepts
Graph_intro.md

### Bandwidth shortage
There is one issue needs to be deled with before processing any proper analysis, some of the bandwidth information in the raw dataset are not publicly released. To overcome the problem of missing data on bandwidth, author decided to employ Butter's law of bandwidth to estimate the potential bandwidth capacity that can be carried by STC. In the context of STC, optical fiber is the most fundamental and essential material in photonic data communication. Similar to the Moore's law, Butter's law based the historical observation that the amount of information can be transmitted through the optical fiber has been doubling every 9 months thanks to the development of new technologies such as wavelength-division multiplexing.(@hadaway_2016_16)(@buttle_2014_internet)

$ n_i = n_0\times2^{(y_i-y_0)/T} $

Where $n_0$ is the initial bandwidth throughput in the year $ y_0$, T is a constant reference to the number of years needed to double the bandwidth throughput. The value of $n_i$ is the resultant bandwidth in the year $y_i$, thus its logarithmic value shows a linear dependency on $n_0$. 

### Policy-Based Routing

The path between the origin and destination in a network could either be statically predefined, or adaptively changed based on the algorithm. The routing decisions change dynamically based on the instantaneous status within the network, such as current network topology, traffic load, latency. (@medhi_2017_network) The first priority for all the routing algorithm is to prevent the deadlock, thus the optimal routing strategy aims to achieve maximum efficiency by minimizing the routing cost.(@duato_2003_chapter) Considering an undirected graph(G) with N nodes and M edges, where each edge is assigned to a weight to represent a physical property of 'distance'. The target is to find a route between two nodes alone a set of edges, therefore the sum of weights under this route is minimum upon all the route choices. The routing algorithm mathematically discover the best route is called shortest-path algorithm. There are four types of weight property applied to the edges into their investigations, they are: Simple, Spatial length, Budget cost, Bandwidth capacity. The detailed summary of description can be found in Table %^%^%+1

| Property | Symbol | Explain | Application |
|---|---|---|---|
| Simple | $C^S$ | Each edge weight is assigned to value of 1 | The path where data flows through with minimum number of edges along the way. |
| Spatial length | $C^L$ | The edge weight is the actual length of STC between the landing stations | As the distance is directly proportional to the time, the route with shortest length in STC gives the minimum time taken for data to travel between landing stations. |
| Budget cost | $C^C$ | The edge weight is average cost of deployment based on the length | STC owner recovers the cost of deployment by charging the money from the local internet services providers(ISP). A STC may be preferred by ISP due to its low charging price. |
| Bandwidth capacity | $C^B$ | The edge weight is the maximum data throughout capacity | Each STC is labeled to a design bandwidth capacity, it is the theoretical limit of data carriage ability. It is useful while users are sending large size files via STC. |

###### Table. %^%^%N. Edge properties

### Network Analysis
To analysis such complex network consists large number of nodes and edges, the research boundary is not only the physical connection of STC also an abstract quantitative network to deal with the communication between the nodes and edges. 

As the weakness may either occur on the under water STC or the cable landing stations, the locations in the global STC network with the high value of centrality gain more interest than others. The node with high centrality referred to the importance of an actor plays in a topological network structure.(@hoffman_2021_methods) There are two centrality measurements are employed in this investigation: degree centrality, betweenness centrality - The detailed strength and weakness can be found in Table %^%^%+1.

| Concept | Definition | Explain | Application |
|---|---|---|---|
| Degree centrality | The count number for edge directly connect to the node(@sharma_2013_degree) | A node with higher degree of edge acts the more central role of a network | Degree centrality shows how many nodes can be directly reached by such node, even though this node might be far off on the boundary of this network |
| Betweenness centrality | $\delta_s(E)=\sum_{(x,y)\in E} \frac{\sigma_{xy}(E)}{\sigma_{xy}} $(@hansen_2019_analyzing) | The node plays as a hot spot role in many shortest paths | If all the information must pass through a node before reaching the destination, this node is the most important as the efficiency of the communication is depend on it. But betweenness centrality is compute intensive large scale network |
###### Table. %^%^%N. Network analysis compare

### Network optimization

To overcome the problem of STC incidents, reroute the data flow to an alternative or secondary infrastructure would in worst performance but functional internet services. If the country/region only consists one STC connection, it is considered to be high risk country to STC failure due to its low redundancy. South pacific ocean has been know by its isolation to the majority of the world, the deployment of STC is not as well-developed as the rest of the world. This makes the countries(such as Tonga) extremely vulnerable and dependent to its only STC to communicate with rest of the world, but this risk could be mitigated by laying additional STC cables to increase its network redundancy. (@laporte_2015_chapter) Inspect a similar issue from Chinese postman problem(CPP) and provides an idea from another perspective. 

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

CPP indicates additional edge needed to form a Euler circuit graph, a walk can visits every edge exactly once by starting from any given node.(@tan_2005_chinese) Thus the each node must a positive number pairs of edges to provide the route for incoming and outgoing path. This provides a baseline of one STC redundancy for each landing station.

Meanwhile, over-redundancy is the by-product of the CPP which produced unnecessary edge to satisfy the CPP algorithm. Eventhough redundant edges give more robust network topology, it also brings extra cost for construction. Here author presents rich-club coefficient which describes the connectivity between the node with high degree centrality, by setting the assumption that higher centrality nodes are gaining bigger geographical advantages in the network. (@ma_2015_richcores)
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