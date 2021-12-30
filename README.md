## Network data analysis using networkx
Network science or network analytics, involve the analysis of network data and statistics to identify trends and patterns. It is part of graph theory, where a network can be defined as a graph in which nodes and/or edges/links have attributes. 
Here, we use python package networkX. NetworkX includes many graph generator functions and facilities to read and write graphs in many formats.


|   | script                        | description                    |
|---|-------------------------------|--------------------------------|
| 1 | airline_network_data_analysis | analysing airline network data |
| 2 | epidemic_spreading_analysis   | predict the spread of a pandemic |
| 3 | marketing_social_media        | information spreading          |
| 4 | community_detection           | clustering behaviour           |

## 1. Airline network
Airport networks are crucial for understanding the spread of world-wide pandemics. Air-travel is one of the quickest ways that diseases can spread across the globe. For the airport network, an 'attack' is effectively the closure of an airport. Here, the aim is to know if it is possible to break the network apart, and stop the disease spread, by only attacking a few nodes (closing a few airports).

From the experiments, closing a few airports (with the most connectivity) would result in increase in diameter (i.e. shortest distance between two airports) and average path length (i.e. longest number of flights to reach anywhere in the world) within the airline network. These results are not surprising, as closing of a few airports would mean having to perform more transits (somewhere else). 

## 1. Disease network
Networks (and network simulation), are a key tool in trying to predict the spread of worldwide pandemics. Many governments use modelling and simulation software (such as Gleamviz) to help them make decisions during an epidemic outbreak. Here, the aim is to build a simple model of disease spread on different artificial networks and investigate different vaccination strategies to try and prevent/ slow down the spread of the pandemic.

The network built here is based on the stocastic SIR (Susceptible, Infected, Removed) model, where $\alpha$ and $\beta$ describe the rate of removal (fraction of people moving from Infected to Removed) and the rate of infection (fraction of people moving from Susceptible to Infected) respectively. There is a level of known and unknown parameters, which is somewhat realistic, since governments may only have **some** information and data for different aspects of the pandemic. 

Having **any** vaccination strategy delays the average peak time and decreases the average total infected, compared to not having any vaccination strategy. Vaccinating the node (person) with the highest degree will be more effective against the disease, since the person will have the most personal interactions with other people. In reality, it is hard to implement, because should we vaccinate people based on the number of 'friends' in facebook/ instagram? 
