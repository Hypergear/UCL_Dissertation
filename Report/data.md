# Data

This section demonstrates and discusses the data was identified to
characterize the essential requirements and to estimate the STC network
system performance, before the highlighting any analysis. The STC data
process can be categorized into 4 sections: dataset gathering, dataset
pre-process, data storage, data category classification.

## Dataset gathering

There are three comprehensive open datasets of the global STC were
utilized in this research. All three datasets provide some information
on cable name, cable length, ready to services date and cable owner,
they differ in extra information(eg number of fiber pairs) and number of
cables documented

-   Submarine cable dataset [DS1](www.submarinecablemap.com/api/v3): The
    *Submarine Cable Map(SCM)* is an online web map service powered by
    TeleGeography, which gives the world STC GPS location and its
    landing points. TeleGeography has 15 years of experience in
    telecommunications market research and consulting, its research
    results sponse to the companies such as Amazon AWS, CISCO and Google
    cloud.

    [DS2](https://subtelforum.com): For detailed STC properties, the
    *Submarine Cable Almanac(SCA)* offers information including planned
    budget cost, number of fiber twisted pairs. This report updates
    quarterly with the most recent data and technical breakthroughs in
    the submarine telecommunication industry.

    [DS3](https://www.infrapedia.com/app/subsea-cable): The
    *Infrastructure Map* provides detailed STC designed capacity and
    annual lit capacity of the global STC network. The data in
    Infrastructure Map is directly collected from the official website
    for each STC and peer viewed by a group of experts from
    TeleGeography and the community.

-   Global bandwidth throughput dataset
    [DS4](https://www.itu.int/en/ITU-D/Statistics/Pages/about.aspx):
    Recall that more than 98% of global internet transmission is handled
    by the STCs[@winseck_2017_the], the annual survey from ITU documents
    the \"total international bandwidth usage per second\" and
    \"individual bandwidth usage for each internet user per second\"
    across 237 countries from 2007 to 2020. ITU collected and harmonized
    the information from the state telecommunication/ICT ministries or
    national statistical offices

## Data pre-process

For various reasons, the cable property data in a few cables are not
publicly released. In very rare cases, the property data on an STC shows
a conflict of information between datasets or significantly outlies the
rest values under that data property. To overcome this, the author uses
Interactive Transmission Network Maps[@bdt_2022_infrastructure] as the
additional validation dataset and adopting the majority rule strategy
from the voting system[@kuncheva_2003_limits] to decide the most
reliable information within. Worth to mention that the data from SCA
holds two votes as the data properties are reviewed more frequently(4
times every year) than other datasets. All the datasets mentioned above
remain in the public domain for any non-commercial usage.

## Dataset Storage

All the raw data and processed clean data are stored in an SQLite
database which kept in secure storage(eg Github repository) to ensure
their confidentiality, availability and durability.

## Data category classification

Since the research scope focuses on the submarine telecommunication
cable, the following types of fibre optic cables are not included in
this research. Firstly, the fibre cables lay after the STC landing point
which is also known as the terrestrial telecommunication cable(TTC),
these cables play as the highway to provide the domestic internet
connection or speed up the data traffic between STC landing stations
from one country to another. TTCs are usually constructed and controlled
by the local ISPs, they are much longer and harder to trace the
locations. For example, the Zayo group built at least 170222km of TTC in
the contiguous US where most of the connections between the east coast
and west coast are relayed on this.[@infrapedia_2022_zayo] Secondary,
the cable used for military or national security purposes are excluded
because their existence is extremely confidential and they are using
private networking which is not open to civilian
broadband.[@ruffin_2000_a] The third exclusion consists of private
cables and dark fibres, these cables are either used to transmit private
information between servers with high standards on performance and
security or the constructed cable but currently not on services. Because
of their special usage, the network topologies are usually
point-to-point, star or ring which do not contribute to the majority of
the people.[@sima_2007_deliverable] Lastly, the STCs which are only
designed to serve particular sea operation stations are also excluded. A
typical example is oil drilling platforms where the single channel
communication is directly connected to the TTC and transmission is used
purely for commercial reasons. For example, *Abu Dhabi* is the cable
with a length of 420km which connects UAE and Abu Dhabi National Oil
Company's offshore production
facilities.[@nielsen_2017_submarine; @jandenul_2021_jan]

-   High level data description The High level data description
    aggregates the data based on their belonging countries which gives
    an abstract view of the STC connection.

-   Low level data description Low level data helps to explain the STC
    connection in more concrete information such as STC landing cities
    and services status. A coastal country may consist one or many
    landing cities, this will dramatically increased the number of nodes
    and edges to be considered. This level also gives the most detailed
    entries of their construction in the network of connections, as each
    edge is labeled to a unique color to identify their route path under
    the sea.
