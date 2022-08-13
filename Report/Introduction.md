# Introduction

Motivated by the progress of information technology on mobile devices
combined with the rise of the 5G technology and cloud computing
services, the demand for higher stand internet services can be foreseen.
The world needs a medium to transmit a large amount of data
inexpensively more than ever. As the *highway* of data communication,
the optic fibre is the most common tool for wired long-distance data
communication.[@kangovi_2017_3] There are two types of state level fiber
optic cables: fibre optic terrestrial telecommunication cable(TTC) and
fibre optic submarine telecommunication cable(STC). In terms of
useability, the latter gains a bigger market share.
[@marra_2018_ultrastable] Nowadays, STC is responsible for more than 98%
of global internet transmission [@winseck_2017_the]. By estimate, more
than 1.2 million KM of STC were constructed. [@wang_2019_costeffective].
In some terms, any internet service depends on STC's functional working
in fields such as academia, education, entertainment, finance, health
care, and the military.

Considering the irreplaceability of STC in all aspects of people's daily
life, the failure could cause a significant negative impact on the
social and economic disruptions in a community or society. The failure
of an STC might not disrupt access to the worldwide internet, as the
nature of the internet routing topology, [@calvert_1997_modeling]
suggested that the connection can still be obtained by a longer and less
stable connection. [@turner_2010_california]. However, this is not true
for all the countries. In 2008 a dragging ship anchor damaged either one
of STCs in Mediterranean: SEA-ME-WE 4 or FLAG, the data was
automatically rerouted data to SEA-ME-WE 3 and overwhelmed its design
capacity, which subsequently caused more than 50% of internet services
interruption in middle-east area. [@zetter_2008_undersea] More recently,
in 2022 the volcano eruption in Tonga caused the failure of Tonga's only
STC, which subsequently led to the internet blackout with the rest of
the world for nearly five weeks. [@bateman_2022_cut] Due to the
commercial interest and limited internet usage, usually less developed
countries and remote islands such as Chile or the Marshall island do not
have an alternative STC for redundancy. [@domineyhowes_2022_when]
Obviously these countries are more dependent and suffer more losses if
the STC breaks down.

Even though STC is a world spread infrastructure, there are still four
billion people who do not have access to the internet. However,
satellite internet can be an alternative technology to replace the STC
by using non-synchronous orbit satellites. [@graydon_2019_connecting]
These satellites rotate around the earth obit, providing wireless
internet connection to the customer near the earth's surface. If the
satellite is located in geostationary earth orbit, the user will suffer
from high latency and limited bandwidth. Low Earth orbit (LEO)
satellites can significantly mitigate these issues. Still, LEO acquires
hundreds of thousands of satellites to provide worldwide coverage which
gives higher standards on the internet services provider(ISP).
[@deutschmann_2021_broadband] Regardless, satellite internet services
always have higher requirements on the user budget than STC, as the
professional technical devices and expensive data packages need to be
pre-purchased before usage. [@starlink_2022_starlink]

The rest of paper is organized as follows. Firstly, in Section 2, the
vulnerability, legal protections and consequences of STC breakdown are
introduced in details. Then, the related datasets and data pre-process
are provided in Section 3. After that, the analysis procedures including
a local STC optimization approach are given in Section 4 and 5. Finally,
Section 6 and 7 give the discussion and conclusions.
