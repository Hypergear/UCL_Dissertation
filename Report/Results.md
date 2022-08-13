# Results

In this section, author presents the results of the STC network
vulnerability analysis in two levels where their topologies are not
pre-specified.

The analysis starts off with a generalized country level STC network
connection, focusing on the shortage of the STC due to the natural
growth in the international internet bandwidth and the country's
internet robustness when multiple STC failure happens simultaneously. To
better understand internet accessibility, the author obtains a detailed
route level network for the STC paths, the analysis is based on 4 edge
property measurements with 3 assessment approaches.

## Study scope

As a marine based infrastructure, STC is not suitable and applicable to
be deployed in all countries. Since the first STC was laid in 1989, the
global broadband network interconnects almost all the countries in the
world with 183 countries owning at least one STC cable. Countries left
out were either territorially landlocked(eg. Mongolia and Ethiopia) or
geopolitically less interested into it(eg. North Korea).

![Map of first STC cable laying
year](Img/result_map_STCYear.png){#fig:First_STC width="5.7in"}

## High(country) level STC

### Distribution of STC between countries

The high level data aggregate the territorial information at the country
level, which includes the mainland, dependent areas and overseas
territories.[@nationsonline_2022_countries] This makes some small
oversea island be in part of its administrative territories. For
example, Guam is an unincorporated territory of the US in the western
pacific Ocean[@usdoi_2016_definitions] but it is responsible for 7 out
of 20 STCs connections between East Asia and West
America[@telegeography_2022_submarine]. This leaves 396 edge connections
across 183 countries.

![Country level
connection](Img/result_map_countryFirstCable.png){#fig:Country_Connection
width="5.7in"}

Figure [1.2](#fig:Country_Connection){reference-type="ref"
reference="fig:Country_Connection"} presents the visualization of the
country level STC connection, where each node is the representation of
one country and there is at least one edge directly connected to it. The
edge width is proportional to the count of STCs in charge of the
end-to-end connection between two nodes.

![Country degree in
histogram](Img/result_his_countryDegreeCount.png){#fig:Country_Degree
width="5.7in"}

Combined to with Figure [1.3](#fig:Country_Degree){reference-type="ref"
reference="fig:Country_Degree"}, a high clustering of the domestic
connection in Southeast Asia and Europe can be expected. As the majority
of the countries are having less than 25 direct STC connection to other
states, in this case the design of STC tend to build a loosen and
distributed network in a small area. Countries such as
$K_{Indonesia}=224$, $K_{United States}=216$, $K_{United Kingdom}=118$
are way outnumbered the rest of 180 countries accounting for 26% of
global landing station count. Such, these countries tend to have more
redundant cables than the rest of the world. This network has the edge
density = 1/17, this ratio indicates the gap between the actual edge and
the max possible edge.

### Bandwidth shortage due to the nature growth

Despite the development of the local caching services(eg. CDN) over the
last two decades, increased investments in STC by the tech giants and
continued construction of data centers around the globe, the demand for
international bandwidth usage seems to increase in the next few years
according to the estimation and statistics from ITU[@itu_2022_country].

![Country most vulnerable to international bandwidth
shortage](Img/result_hbar_capacityGap.png){#fig:Capacity_Gap
width="5.7in"}

Figure [1.4](#fig:Capacity_Gap){reference-type="ref"
reference="fig:Capacity_Gap"} shows the top 10 countries that have the
risk to overcome the gap between international bandwidth served by the
STC and increasing internet services demand from its people. Even though
Poland, Romania, Croatia are most vulnerable to this situation, in
reality as members of the Europe Union, the actual gap is less than the
paper result as the bandwidth deficit can be covered by TTC from
adjacent countries. In contrast, countries with less political
stability(eg. Syria) and geographically located in an island(eg.
Vanuatu) will suffer more on this, especially during the internet rush
hours.

### STC redundancy analysis

With over 100 yearly accidents from human unintentional incidents (eg.
fishing dredge and anchoring) to natural hazards combined with the
potential hostile attack for military purposes. [@mauldin_2017_cable] It
is not hard to imagine the scenario where a country's internet services
is disrupted by multiple cable losses at the same time. To simulate the
consequences of such disruption in the worst case scenario, the strength
of the internet is examined by assessing the remaining bandwidth after
removing the cables with the highest bandwidth.

![STC country bandwidth robustness
compare](Img/result_waffle_countryCompare.png){#fig:Bandwidth_Compare
width="5.7in"}

Firstly, the countries with less than 3 redundant cables are considered
as vulnerable to internet connection. Historically speaking a
simultaneous STC failure on 3 cables rarely happens, it is also
advantageous if the country could still make essential communication
with the outside world under such scenario. Figure
[1.5](#fig:Bandwidth_Compare){reference-type="ref"
reference="fig:Bandwidth_Compare"} lists the share of countries under
such use case. The STC vulnerable countries($K_{i}<4$) can not obtain
the STC connectivity, which could be critical for some island countries
or territories as the lack of the TTC means a potential loss of 100% of
the international bandwidth. In contrast, STC robust
countries($K_{i}>=4$) are less likely to suffer from this.

![Spatial distribution of STC vulnerable
countries](Img/result_ring_countryVulnerable.png){#fig:Vulnerable_Countries
width="5.3in"}

To further investigate the STC robustness, Figure
[1.6](#fig:Vulnerable_Countries){reference-type="ref"
reference="fig:Vulnerable_Countries"} shows the spatial distribution of
the STC vulnerable countries. The outer ring is the share of total
bandwidth from each continent whereas the inner ring gives the portion
for every county. Continents with high percentage are Asia \> Africa \>
North America \> Oceania \> South America \> Europe. According to the
figure, Asia is the most vulnerable continent as it gives the highest
figure, but the segment is made up of a handful of countries with high
bandwidth. In contrast North America and Africa, a smaller sector from
each country with a high number country count. As a case concerns South
America, which only consists of 3 vulnerable countries: French Guiana,
Guyana and Suriname with an evenly distributed bandwidth allocation. The
countries only deliver a summed capacity and cable count of 209.65Tb/s
and 2.67cables/country.

![Scenarios of STC failures with most robust
countries](Img/result_hbar_bandwidthRobust_country.png){#fig:BandwidthRobust_Country
width="5.7in"}

![Scenarios of STC failures with lest robust
countries](Img/result_hbar_bandwidthRisk_country.png){#fig:BandwidthRisk_Country
width="5.7in"}

There are 94 countries assigned to STC robust group, as each country can
withstand three or more losses on STC. As the result of cable failure,
the country may suffer from a reduction in the international bandwidth
capacity. However, losing one or two cables is more likely to happen in
the real world. Figure
[1.7](#fig:BandwidthRobust_Country){reference-type="ref"
reference="fig:BandwidthRobust_Country"} and
[1.8](#fig:BandwidthRisk_Country){reference-type="ref"
reference="fig:BandwidthRisk_Country"} shows the resultant remaining
bandwidth in percentage to retain the internet connectivity if the top
three widest cable fails.

USA is the leading player in remaining bandwidth after multiple cable
failures, thanks to its excellent loosen cable distribution and
availability of redundant cables. With cable edge $K_{usa}=29$ and
estimated potential bandwidth of 1479.76Tb/s. After the connection loss
of its widest cable *Dunant*, a reduction of 250Tb/s(16.89%) in the
overall US bandwidth can be expected. Even in the worst case scenario in
this study where top3 cables are failing at the same time, USA would
still obtain the remaining international bandwidth capacity of
642.43Tb/s which outnumbered the actual demand. (41.16Tb/s in
2022)[@itu_2022_country] Besides that, the continental USA is
geographically adjacent to Canada and Mexico which may provide
additional TTC bandwidth capacity if necessary.

Isle of Man is a bad example of the cable distribution design, with an
estimated 98.66% bandwidth losses as the result of disconnect in its
widest cable Havhingsten/Celtix Connect-2, with the remaining 1.42Tb/s
capacity from the rest of 3 cables.

## Low(landing station) level STC

To better understand how STC is distributed across the world, the author
also concerns a detailed low-level route for the STC paths. Figure
[1.9](#fig:LandingStation_network){reference-type="ref"
reference="fig:LandingStation_network"} below outlines the landing
stations and the geographical path of the global STC connections.

![STC network in landing station
level](Img/result_map_landingDistribution.png){#fig:LandingStation_network
width="5.3in"}

From Table
[\[table:LowLevel_Summary\]](#table:LowLevel_Summary){reference-type="ref"
reference="table:LowLevel_Summary"} we can also observe a highly skewed
STC cable data distribution as the mean values are closed to 75% with a
rapid increase in cable capacity, cable length, cable cost after that.

::: tabu
to 1 & **Country** &**Landing station** & **Cable capacity(Tb/s)** &
**Cable length(KM)** & **Cable cost(million USD)**\
count & 183.00 & 1335.00 & 501.00 & 501.00 & 501.00\
mean & & & 50.42 & 3406.04 & 119.61\
std & & & 231.24 & 5986.72 & 182.44\
min & & & 0.00 & 5.00 & 0.25\
25% & & & 0.25 & 225.00 & 15.00\
50% & & & 5.91 & 775.00 & 40.10\
75% & & & 44.38 & 3472.00 & 122.00\
max & & & 4000.00 & 45000.00 & 1007.78
:::

### Policy-Based Routing

Considering the nature of routing in a complex network, the path between
source and destination node can be selected from vast options. Figure
[1.10](#fig:Path_YemenIndia){reference-type="ref"
reference="fig:Path_YemenIndia"} shows a case of data communication
between Yemen-India via STC. Although there are only six routes on the
map, there are still many alternative routes that can be discovered with
longer distances or bypassing more landing stations.

![STC route options from
Yemen-India](Img/result_map_path_YemenIndia.png){#fig:Path_YemenIndia
width="5.7in"}

To approach the network routing while selecting the best route, a range
of information also needs to be considered.[@baumann_2007_a] In this
case, the author compare the routes from Bude(UK) to Shanghai(China) to
identify the shortest path under different use case for data
transmission.

![Low-level shortest-path route
($C^S$)](Img/result_map_shortestPath_node.png){#fig:Shortest_Node
width="5.7in"}

![Low-level shortest-path route
($C^L$)](Img/result_map_shortestPath_latency.png){#fig:Shortest_Latency
width="5.7in"}

![Low-level shortest-path route
($C^B$)](Img/result_map_shortestPath_capacity.png){#fig:Shortest_Capacity
width="5.7in"}

![Low-level shortest-path route
($C^C$)](Img/result_map_shortestPath_cost.png){#fig:Shortest_Cost
width="5.7in"}

As Figure [1.11](#fig:Shortest_Node){reference-type="ref"
reference="fig:Shortest_Node"} to
[1.14](#fig:Shortest_Cost){reference-type="ref"
reference="fig:Shortest_Cost"} shown, the paths are chosen by the data
packages based on their routing policies, in such instance, $C^B$
chooses a geographically longer route to exchange for a wider bandwidth
capacity in comparison to other routes. Using Mumbai(India) as the
routing transit station is the common practice in this study case, the
importance of Mumbai in global STC connection will be presented in
Section [1.3.2](#Degree_centrality){reference-type="ref"
reference="Degree_centrality"}. It is also interesting to see a high
overlap between the STC routes and some of the most important shipping
trade routes, take $C^S$ as an example, the route passes English
Channel, Strait of Gibraltar, Suez Canal, Bab al-Mandab Strait, Malacca
Strait before reaching its destination. It is risky for the cables from
anchors damages, as a large number of ships are right above the STC
cables in the shipping route area. In addition to that cable density in
these regions are usually higher than normal due to the narrow width
alone the bank(205m for Suez canal), the damage from natural hazard or
explosions may cause failure on multiple STCs.

### Degree centrality {#Degree_centrality}

To assess the importance of each individual landing station, the degree
centrality provides a quantitative measure to classify the nodes based
on their cohesiveness. Accordingly, the count of adjacent edges for each
landing station will be assessed, Figure
[1.15](#fig:landingDegreeCentrality){reference-type="ref"
reference="fig:landingDegreeCentrality"} captures the results of the
degree centrality based on the landing stations. Mumbai(India) is the
headmost with $K_{Mumbai}=160$ and 0.43 degree centrality, followed by
Shima(Japan) and Jeddah(Saudi Arabia), their high values can be
explained by the geographic importance as the transit countries. Japan
is the gateway to connect Asia and Pacific ocean, similarly Saudi Arabia
is located near the Suez Canal the shortest sea connection between Asia
and Europe. Another side of the coin, the landing stations with the
lowest degree centrality can be found in the island countries or regions
with only one cable connect to it eg. Aeng Batu Batu(Indonesia), Balluta
Bay(Malta)

![Low-level degree centrality
map](Img/result_map_landingDegreeCentrality.png){#fig:landingDegreeCentrality
width="5.7in"}

The landing stations with a high degree centrality are playing a more
significant role in the STC network, arguably such design is not ideal
in terms of risk assessment. The high degree centrality nodes consist of
intensive connection, the failure in the node itself cause by unexpected
accidents (eg. power blackout, riots, terrorist attack) would
consequently in more serious damage to the communication globally as the
data routing can not proceed to the succeeding landing station. Besides
the landing stations mentioned above, Singapore is also extremely
valuable to the STC network but can not directly be observed from the
map. Due to the limited area in Singapore, the two landing
stations(Changi North and Tuas) are only 35km apart, the accident in one
landing station is likely to implicate another.

### Betweenness centrality

To account for the topological cable breakage at the sea, one important
issue that needs to be considered is the geographical distribution of
the cable usage while transmitting the data package. The betweenness
centrality returns the ratio in which the node is sitting alone on the
shortest path between any two nodes, it can be seen as a comprehensive
measure of the routing path selection in terms of the possibilities.
With a different focus on the data routing policies, Figure
[1.16](#fig:Betweenness_Overview){reference-type="ref"
reference="fig:Betweenness_Overview"} visualize the distribution of the
betweenness centrality individually while Table
[\[table:Betweenness_summary\]](#table:Betweenness_summary){reference-type="ref"
reference="table:Betweenness_summary"} statistically summarizes the
value.

![Betweenness centrality
Overview](Img/reult_line_NodeBetweenness_Overview.png){#fig:Betweenness_Overview
width="5.7in"}

![Betweenness centrality
Zoomed](Img/reult_line_NodeBetweenness_Zoomed.png){#fig:Betweenness_Zoomed
width="5.7in"}

::: tabu
to 1 & **Latency** & **Cost** & **Capacity**\
count & 7229 & 7229 & 7229\
mean & 0.015085355 & 0.016789418 & 0.019458784\
std & 0.043984581 & 0.051353499 & 0.064554104\
min & 0 & 0 & 0\
25% & 0.000892193 & 0.000609267 & 0.000675097\
50% & 0.002603469 & 0.002106302 & 0.002119711\
75% & 0.008613072 & 0.009043768 & 0.007870817\
max & 0.371998844 & 0.48875602 & 0.517119399
:::

The betweenness centrality for each routing policy gives a power-law
distribution pattern in Figure
[1.16](#fig:Betweenness_Overview){reference-type="ref"
reference="fig:Betweenness_Overview"} while Table
[\[table:Betweenness_summary\]](#table:Betweenness_summary){reference-type="ref"
reference="table:Betweenness_summary"} contains the relevant summary
statistics. This is a bad design in network science, where the route
choice is heavily dependent on a handful of nodes to maintain its
performance. If the failure happens on the high betweenness centrality
node, this design would result in a dramatically deteriorate of the
efficiency of the data flow when the network is switched to the
sub-optimal route(eg. takes more time to the destination, narrowed
bandwidth, higher usage cost). A more detailed data pattern across
different routing policies, Figure
[1.17](#fig:Betweenness_Zoomed){reference-type="ref"
reference="fig:Betweenness_Zoomed"} gives a zoomed view of the first 500
nodes from Figure [1.16](#fig:Betweenness_Overview){reference-type="ref"
reference="fig:Betweenness_Overview"}. It is evident that Bandwidth \>
Cost \> Latency in the first 300 nodes, which mostly explained the
reason why the big difference in the mean value with the contrast of
little variation in 75% values from Table
[\[table:Betweenness_summary\]](#table:Betweenness_summary){reference-type="ref"
reference="table:Betweenness_summary"}.

Therefore, a higher reduction in global STC bandwidth can be expected
while comparing with the latency, if any highlighted node/cable breaks
down in Figure [1.18](#fig:Betweenness_Latency){reference-type="ref"
reference="fig:Betweenness_Latency"} to Figure
[1.20](#fig:Betweenness_Cost){reference-type="ref"
reference="fig:Betweenness_Cost"}. Furthermore, the distribution of
latency betweenness gives a shallow curve with a lower standard
deviation, which speaks to a more loose network with higher resilience
than other routing policies. In other words, the disconnect on a
critical node would result in a more significant impact on the bandwidth
capacity than transmission latency.

![Betweenness centrality
map($C^L$)](Img/result_map_betweenness_latency.png){#fig:Betweenness_Latency
width="5.7in"}

![Betweenness centrality
map($C^B$)](Img/result_map_betweenness_capacity.png){#fig:Betweenness_Capacity
width="5.7in"}

![Betweenness centrality
map($C^C$)](Img/result_map_betweenness_cost.png){#fig:Betweenness_Cost
width="5.7in"}

Figure [1.21](#fig:Betweenness_Aggregate){reference-type="ref"
reference="fig:Betweenness_Aggregate"} aggregates the betweenness
results above to provide a summary of the node distribution to the
adjacent cables. Of the three classes of routing policies, each group is
showing a different focus on patterns. it is important to illustrate the
role of betweenness centralities by different types of distance measures
throughput the global STC network.

Out of 3 routing policies, the spatial pattern reveals some informative
clues. Firstly the latency betweenness measure of $C^L$ appears to
maintain one highlighted connection between two geographic adjacent
continents, especially in the route connecting from Singapore(Asia) to
New York (North America) via UK(Europe). This result could be motivated
by the demand in the financial sector(eg Stock exchange), as the data
synchronization between financial data centres usually consists of the
feature of high requirement for real time transmission. Secondary, the
bandwidth betweenness shows a widespread distribution, this offers many
benefits from reliability to data accessibility. This distributed
architecture might not propose a critical bandwidth shortage problem to
the remaining servers even if the malfunction occurs on the most
important node(eg India). As some of the web-services services can be
hosted on the existing cloud or CDN deployments, the widespread wide
bandwidth cables are most clearly benefiting from the cloud-hosted
resources(eg. trending YouTube videos) on the nearby CDN service
stations. Finally, the cost betweenness highlights the necessary nodes
required to achieve the minimum cost, showcase route from Singapore to
Brazil via the India, UAE and South Africa is highlighted, while this
route avoids the most cable congested water lane in the Mediterranean
Sea instead of an open connection in South Africa. It is interesting to
find out the overlap between $C^B$ and $C^C$ in East Africa where the
cables(eg 2Africa) are more advanced in budget controlling and bandwidth
capacity.

![Aggregated betweenness centrality
map](Img/result_map_betweenness_aggregated.png){#fig:Betweenness_Aggregate
width="5.7in"}

Figure [1.21](#fig:Betweenness_Aggregate){reference-type="ref"
reference="fig:Betweenness_Aggregate"} aggregates the previous
betweenness analysis into one visualization to provide a snapshot of top
5% most important routes around the world. With a high clustering in
Southeast Asia, MENA(Middle East and North Africa) and Celtic Sea, this
finding could be utilized to simulate the consequence of the cable
accident in those regions by estimating the impact on overall network
functionality reduction.

## Network optimization with CPP

The Tonga volcano eruption on 20 Dec 2021 was believed as the largest
volcanic eruption since 1883 on record, which subsequently caused the
destruction of its only STC on 15th Jan.[@cnn_2022_tonga]

After 38 days of lack of full access to broadband, repair ship Reliance
replaced 92km of STC between Tonga to Fiji.[@tom_2022_internet] During
that time the communication with the outside world was backed up by
satellite telecommunication, but the traffic shrank by around 99%.

![Tonga internet traffic during the STC
failure[@cloudflare_2022_internet]](Img/result_img_tongaTraffic.png){#fig:Tonga_Traffic
width="5.7in"}

### Redundancy analysis

To overcome the fault scenario in Tonga in the future, building
redundant cables as the backup broadband services to compensate for the
impact caused by connectivity loss on primary cable. This acquires at
least two cables connecting to the same landing station, regardless of
whether they are STC or TTC. On this basis the author adopts the Chinese
postman problem(CPP) for network improvement, from its theory, the edges
can be divided into two categories: in-degree and out-degree where each
node consists of at least one pair of the degrees. Out of many
solutions, we found an optimal solution by minimizing the total length
of the additional route planned to be built.

![Planned STC optimization for
Tonga](Img/result_map_OptTonga_route.png){#fig:Opt_TongaCable
width="5.7in"}

This modification to the STCs would make the network more efficient by
allowing more nodes to participate in the information transformation,
the average degree centrality was increased from 0.0588 to 0.0660
locally in these regions. On another positive note, network becomes more
distributed by reducing the dependency on essential communication
between the high degree nodes. Based on the analysis in Figure
[1.24](#fig:Tonga_RichClub){reference-type="ref"
reference="fig:Tonga_RichClub"}, a weaker rich-club effect in the
optimized design is presented as the degree different is smaller, the
average rich-club coefficient is now 0.2660 compared with 0.2741 before
the improvement.

![Rich-club analysis in
Tonga](Img/result_line_OptTonga_RichCompare.png){#fig:Tonga_RichClub
width="5.7in"}

### Financial cost

Any modification to the existing system could bring extra cost,
especially when laying the additional cables for extra redundancy. Here
we will compare and contrast the cost of deploying additional STC and
the use of start link as the alternative technology in Tonga area.

While analyzing the cost of the existing cables in the near water
against with cable attributes by regression analysis, an adjusted
R-squared of 0.963 suggests a good fit to the budget estimation of the
planned cables. The two cables from Tonga to Niue and American Samoa are
estimated of the length 618.18KM and 517.63KM with the cost of \$13.29
and \$10.54 Million USD separately. These cables will directly benefit
people in Tonga to Niue and American Samoa also provides a sub-optimal
route for nearby countries such as French Polynesia and Cook Islands.

![Estimate cost to deploy redundant
cables](Img/result_map_OptTonga_cost.png){#fig:Tonga_NewCable_Cost
width="5.7in"}

With 25 years of industrial average service life, the infrastructure
life expectancy will be based on that. Star link is the most common
consumer level satellite internet services, as an alternative technology
to the STC. There are two parts of the costs to use the start
link[@starlink_2022_starlink]: hardware(\$599) and services(\$110/Mon),
a functional working makes \$112 monthly capita cost can be expected in
the next 25 years. Meanwhile, the STC is sharing the same infrastructure
cost regardless of the number of internet users, the capita cost is
inversely proportional to the number of subscribed users to the network.
As Figure [1.26](#fig:TongaCable_cost){reference-type="ref"
reference="fig:TongaCable_cost"} shows, by the estimate from ITU in 2016
there are 55612 internet users in Tonga, Niue and American Samoa, it is
cheaper to invest money in STC if more than 1862 units(individuals or
companies) are willing to pay for the most standard data package in next
25 years.

![Cost of new STC compared with alternative
technology](Img/result_line_OptTonga_costCompare.png){#fig:TongaCable_cost
width="5.7in"}
