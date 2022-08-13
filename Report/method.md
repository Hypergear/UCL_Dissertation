# Methods

To approach the goal of identifying the vulnerability in the STC
network, the author firstly introduces the key concepts and
terminologies in this study. Secondly, we assess the future risk of
bandwidth shortage due to the increasing bandwidth demand for internet
services. Subsequently, a framework of STC data flow and various
centrality analysis were proposed to identify the potential influential
path/landing station. Finally, an STC improvement scenario in the
southern Pacific Ocean is described.

## Graph theory and Network science

Network science and graph theory are two highly overlapped fields to
model and mathematically describe the relational connection between
multiple objects, even though the two research fields can be used
interchangeably to illustrate a similar idea: the objects (nodes,
vertices) are associated by a logical connection (links,
edges).[@albertlaszlabarabasi_2016_network] But the nuanced differences
between the two statements still exist which can not be interpreted with
one.

-   Graph theory is a branch of discrete mathematics that provides the
    fundamental theorem and essential algorithms for the given
    graph.[@neo4j_2022_graph] The entity of node and edge object could
    be seen as a set of objects with different types of items.

-   In contrast, network science focus on the observation of real-world
    representation of the connection to understand the structure and
    quantify the dynamics of the complex system between the
    objects.[@friedrich_2019_from] For example, society is the linkage
    of individuals with family, friendships, classmates and coworkers.

#### Internet routing in graph theory

![Computer routing in graph
theory[@albertlaszlabarabasi_2016_network]](Img/grouph_img_computerRouting.png){#fig:Computer_routing
width="5.7in"}

The construction of the internet routing network system is valid for an
undirected graph as the internet cables provide synchronous
communication allowing data upload/download happens simultaneously from
both ends.[@gkantsidis_2003_spectral] The system component in such a
graph is often called nodes and each direct interaction between two
nodes is also known as edge.

In a network system, we label a node with $V_i$, where $i$ is the index
of the components in such network system, which is labeled as
$i = 1,2,3...n$.

E is a set of edges between the nodes where each edge association is
denoted as $E_{xy}\rightarrow{((x,y\subseteq V_i) \cap (x\neq y))}$

We denote $K_i$ as the number of edges directly connect to the node
$V_i$ in the network, this number is also known as degree. In an
undirected network system, the total number of edge $L$ can be
calculated by the following equation. $L=\frac{1}{2}\sum_{i = 1}^N K_i$

#### Attributes in the STC graph

To review the global STCs from multiple aspects of dynamic correlations
and bring quantitative constructions needed for the analysis. The
network science and graph theory provide methods to take into
consideration of the quantitative relationship by inserting the
numerical values into the nodes and edges within the STC network. The
network's nodes and edges attribute definition is presented in Table
([\[table:Network_attribute\]](#table:Network_attribute){reference-type="ref"
reference="table:Network_attribute"})

::: tabu
to 1 **Category** & **Attributes** & **Relevance**\
Node & Label & The name of landing city and country\
Node & Position & Lon/Lat of of the given node\
Node & Adjacent & A list of nodes that directly connect by an edge\
Edge & Label & The name of cable\
Edge & Connection & Two nodes that construct this relationship\
Edge & Capacity & The designed maximum data transmission can be carried
of the STC per second\
Edge & Length & The length of the STC between two landing points\
Edge & Cost & The budget cost when the cable was designed\
Other & Other & Undirected graph, each node has the infinite capacity to
route data between two cables
:::

#### Keywords/philosophy in the network science

Under such a quantitative network, a range of network analysis toolboxes
offering the analysis approach to measure the topology and properties of
the network from multi-dimensional groups of content. in
Table([\[table:Network_philosophy\]](#table:Network_philosophy){reference-type="ref"
reference="table:Network_philosophy"})

[@albertlaszlabarabasi_2016_network][@diestel_2017_graph][@hoffman_2021_methods][@muscoloni_2016_richclubness][@najera_2021_measuring][@newman_2017_networks][@saqr_2020_robustness][@xavier_1998_introduction]

::: tabu
to 1 **Concept** & **Explanation** & **Application**\
Degree & Number of edges connecting to a node & To gain observation of
the distribution of connection in a network\
Path & A set of edges that connects from $V_i$ to $V_j$ & A allocate the
spatial movement from the origin to destination for a given condition\
Neighbors & The node($V_i$) is neighbor to a node($V_j$) such that the
edge $E_{V_i,V_j}$ exists. & The diversity of the choice when routing
from one node to another\
Connectivity & The measure of the connection between the nodes, there
are two or more isolated sub-graphs if no path exists between any given
two nodes & If the global internet can be accessed between two
countries, either they are connected by STC or the combination of STCs
and TTCs\
Flow & The non-negative capacity associated with each edge & The
capability of the data movement that no edge can exceed this limitation\
Centrality & A measure to the importance of the node in a network & To
classify the STC landing points based on their cohesiveness. This allows
centrality to be considered as a coefficient to describe node
importance\
Betweenness & Betweenness centrality measures the number of times a node
lies on the shortest path between other nodes. & Provides another view
of network elasticity by considering the most influential routing nodes
in a network. For example, the transit stop in a connecting flight has
higher betweenness in the flight network\
Rich club coefficient & A measure to identify the presence of the
connection between well-connected(a large number of degree) nodes & The
rich club coefficient assesses the group robustness and the ability to
remain functional when the key group member quit from the collaboration
:::

## Bandwidth shortage

There is one issue that needs to be dealt with before processing any
proper analysis, some of the bandwidth information in the raw dataset is
not publicly released. To overcome the problem of missing data on
bandwidth, the author decided to employ Butter's law of bandwidth to
estimate the potential bandwidth capacity that can be carried by STC. In
the context of STC, optical fiber is the most fundamental and essential
material in photonic data communication. Similar to Moore's law,
Butter's law is based on the historical observation that the amount of
information that can be transmitted through the optical fiber has been
doubling every 9 months thanks to the development of new technologies
such as wavelength-division
multiplexing.[@hadaway_2016_16][@buttle_2014_internet]

$$n_i = n_0\times2^{(y_i-y_0)/T}
\label{Butter's Law of bandwidth}$$

Where $n_0$ is the initial bandwidth throughput in the year $y_0$, T is
a constant reference to the number of years required to double the
bandwidth throughput. The value of $n_i$ is the resultant bandwidth in
the year $y_i$, thus its logarithmic value shows a linear dependency on
$n_0$.

## Policy-Based Routing

The path between the origin and destination in a network could either be
statically predefined or adaptively changed based on the algorithm. In
many real world router setups, the routing decisions change dynamically
based on the instantaneous status within the network, the factors
leading to the new route could be: current network topology, traffic
load and latency. [@medhi_2017_network] The first priority for all the
routing algorithms is to prevent the deadlock, thus the optimal routing
strategy aims to achieve maximum efficiency by minimizing the routing
cost.[@duato_2003_chapter] Considering an undirected graph(G) with N
nodes and M edges, where each edge is assigned a weight to represent a
physical property of 'distance'. The target is to find a route between
two nodes along a set of edges, therefore the sum of weights under this
route is minimum upon all the route choices. The routing algorithm
mathematically discovers the best route is called shortest-path
algorithm. There are four types of weight properties applied to the
edges in their investigations, they are Simple, Spatial length, Budget
cost, Bandwidth capacity. The detailed summary description can be found
in Table
([\[table:Edge_properties\]](#table:Edge_properties){reference-type="ref"
reference="table:Edge_properties"})

::: tabu
to 1 **Property** & **Symbol** & **Explain**& **Application**\
Simple & $C^S$ & Each edge weight is assigned to value of 1 & The path
where data flows through with the minimum number of edges along the
way.\
Spatial length & $C^L$ & The edge weight is the actual length of STC
between the landing stations & When the data transmission speed is
constant, time is directly proportional to distance. The route with the
shortest length in STC gives the minimum time taken for data to travel
between landing stations.\
Budget cost & $C^C$ & The edge weight is the average cost of deployment
based on the length & STC owner recovers the cost of deployment by
charging the money from the local ISP. An STC may be preferred by ISPs
due to its low charging price.\
Bandwidth capacity & $C^B$ & The edge weight is the maximum data
throughput capacity that can be carried in that cable & Each STC is
labeled to a design bandwidth capacity, it is the theoretical limit of
data carriage ability. It is useful when users are sending large size
files via STC.
:::

### Network Analysis

To analyze such complex network with a large number of nodes and edges,
the research boundary is not only the physical connection of STC, also
an abstract quantitative network to deal with the communication between
the nodes and edges.

As the weakness may either occur on the underwater STC or the cable
landing stations, the locations in the global STC network with the high
value of centrality gain more interest than others. The node with high
centrality referred to the importance of an actor in a topological
network structure.[@hoffman_2021_methods] There are two centrality
measurements employed in this investigation: degree centrality,
betweenness centrality - The detailed strength and weakness can be found
in Table
([\[table:Network_analysis_compare\]](#table:Network_analysis_compare){reference-type="ref"
reference="table:Network_analysis_compare"})

::: tabu
to 1 **Concept** & **Definition** & **Explain**& **Application**\
Degree centrality & The count number for edge directly connect to the
node[@sharma_2013_degree] & A node with a higher degree of edge acts the
more central role of a network & Degree centrality shows how many nodes
can be directly reached by such node, even though this node might be far
off on the boundary of this network\
Betweenness centrality & $s(E) = {E(x,y)}$[@hansen_2019_analyzing] & The
node plays a hot spot role in many shortest paths & If all the
information must pass through a node before reaching the destination,
this node is the most important as the efficiency of the communication
is dependent on it. But betweenness centrality compute intensive in
large scale network
:::

### Network optimization

To overcome the problem of STC incidents, rerouting the data flow to an
alternative or secondary infrastructure would in worst performance but
functional internet services. If the country/region only consists one
STC connection, it is considered to be high risk country for STC failure
due to its low redundancy. South pacific ocean has been known for its
isolation from the majority of the world, and the deployment of STC is
not as well-developed as the rest of the world. This makes the
country(such as Tonga) extremely vulnerable and dependent on its only
STC to communicate with the rest of the world, but this risk could be
mitigated by laying additional STC cables to increase its network
redundancy. [@laporte_2015_chapter] Inspect a similar issue from Chinese
postman problem(CPP) and provides an idea from another perspective.

::: algorithm
input: Grouph $G_{i}$ output: Grouph $G_{o}$ Begin odd_list = \[\] if G
== EulerianCircuit return G while x in G.node if x.degree % 2 == 1
odd_list.add(x) while odd_list != empty distance = MAX node = i, j for x
in odd_list for y in odd_list if 0 \< path(x,y) \< distance i = x j = y
connect_nodes(G, i, j) remove_node(odd_list, i, j) if G !=
EulerianCircuit start again else return G End
:::

CPP indicates additional edge(s) needed to form an Euler circuit graph,
a walk can visits every edge exactly once by starting from any given
node.[@tan_2005_chinese] Thus each node must have a positive number of
pairs of edges to provide the route for the incoming and outgoing paths.
This provides a baseline of one STC redundancy for each landing station.

Meanwhile, over-redundancy is the by-product of the CPP which produced
unnecessary edges to satisfy the CPP algorithm. Even though redundant
edges give a more robust network topology, it also brings extra costs
for construction. Here the author presents rich-club coefficient which
describes the connectivity between the node with a high degree
centrality, by setting the assumption that higher centrality nodes are
gaining bigger geographical advantages in the network.
[@ma_2015_richcores] $$\phi(k) = \frac{2 E_k}{N_k (N_k - 1)}$$
