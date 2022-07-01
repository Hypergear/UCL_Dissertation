## Data

### Dataset gathering
There are three comprehensive open datasets of the global STC were utilized in this research. All three datasets provide the some information of cable name, cable length, ready to services date and cable owner, they differ in extra information(eg number of fiber pair) and number of cable documented

#### Submarine cable dataset
DS1: The _Submarine Cable Map(SCM)_ is a online web map services powered by TeleGeography, which gives the world STC GPS location and the its landing points. The TeleGeography has the 15 years of experience in telecommunications market research and consulting, its research results sponse to the companies such as Amazon AWS, CISCO and Google cloud. (Source: www.submarinecablemap.com/api/v3)

DS2: For detailed STC properties, the _Submarine Cable Almanac(SCA)_ offers information including planed budget cost, number of fiber twisted pairs. This report updates quarterly with most recent data and technical breakthrough in the submarine telecommunication industry. (Source: https://subtelforum.com)

DS3: The _Infrastructure Map_ provides detailed STC designed capacity and annual lit capacity of the global STC network. The data in Infrastructure Map is directly collected from the official website for each STC and peer viewed by group of expert from telegeography and community. (Source: https://www.infrapedia.com/app/subsea-cable)

#### Global bandwidth dataset
DS4: Recall that more than 98% of global internet transmission is handled by the STCs(@winseck_2017_the), the annual survey from ITU documents the "total international bandwidth usage per second" and "individual bandwidth usage for each internet user per second" across 237 countries from 2007 to 2020. ITU collected and harmonized the information from the state telecommunication/ICT ministries or national statistical offices(Source: https://www.itu.int/en/ITU-D/Statistics/Pages/about.aspx).

### Dataset pre-process

For some reasons, the cable property data in few cables are not the publicly released. In very rare cases, the property data on an STC shows a conflict of information between datasets or significantly outlies than the rest values under that data property. To overcome this, author uses Interactive Transmission Network Maps(@bdt_2022_infrastructure) as the additional validation dataset and adopting majority rule strategy from the voting system(@kuncheva_2003_limits) to decide the most reliable information within. Worth to mention that the data from SCA holds two votes as the data properties are reviewed more frequently(4 times every year) than other datasets. All the datasets mentioned above remains in the public domain for any non-commercial usage.

### Dataset Storage
All the raw data and processed clean data are stored by a SQLite database and kept by a secure storage(eg Github repository) to ensure its confidentiality, availability and durability.



### Data category
Since the scope of this research focus on the submarine telecommunication cable, following types of fibre optic cables are not included in this research. Firstly, the fibre cables lays after the STC landing point which also known as the terrestrial telecommunication cable(TTC), these cables provides the domestic internet connection or play as the highway to connect the data traffic between STC landing points from one end of the country to another. TTCs are usually constructed and controlled by the local internet services providers, they are much longer and harder to trace the location. For example, the Zayo group built at least 170222km of TTC in contiguous US where most of the connection between east coast and west coast are relayed on this.(@infrapedia_2022_zayo) Secondary, the cable used for the military or national security purposes are excluded, because their existence are extremely confidential and they are using private networking which is not open to the civilian broadband.(@ruffin_2000_a) The third exclusion consists of private cables and dark fibres, these cables are either used to transmit private information between servers with high standard on performance and security or the constructed cable but currently not on services. Because their special usage, the network topologies are usually point-point, star or ring which do not contribute to the majority of the people.(@sima_2007_deliverable) Lastly, the STCs which only designed to serve particular sea operation station are also excluded. The typical example is oil drilling platforms where the single channel communication is directly connecting to the TTC and transmission is used purely for commercial reasons. For example _Abu Dhabi_ is the cable with the length of 420km which connects UAE and Abu Dhabi National Oil Company's offshore production facilities.(@nielsen_2017_submarine)(@jandenul_2021_jan)


#### High level data description
The High level data description aggregates the data into based their belonging countries which gives an abstract view of the STC connection. 

#### Low level data description
Low level data helps to explain the STC connection in a more concreat information such as STC landing cities and services status. A coastal country may consists one or many landing cities, which dramatically increased the number of nodes and edges to be considered. This level also gives most detailed entries of their construction in the network of connection, as each edge is label to a unique color to identify their route path under the sea.


--- 
# Byproduct, Ignore 

### Gathering, pre-process, storage

The data

|Dataset|Notation|Access by|Format|
|---|---|---|---|

### Ethical consideration







keywords

Lit Capacity
    genuine traffic-carrying capability at a moment in time
    https://blog.telegeography.com/whats-the-difference-between-lit-capacity-and-potential-capacity
    https://irfansalam.wordpress.com/2012/12/02/submarine-cable-systems-what-is-lit-capacity/