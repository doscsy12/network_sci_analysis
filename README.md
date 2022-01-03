## Network data analysis using networkx
Network science or network analytics, involve the analysis of network data and statistics to identify trends and patterns. It is part of graph theory, where a network can be defined as a graph in which nodes and/or edges/links have attributes. 
<br>
<br> Here, we use python package [networkX](https://networkx.org/). NetworkX includes many graph generator functions and facilities to read and write graphs in many formats. They have inbuilt graphs, such as [Petersen graph](https://github.com/doscsy12/network_sci_analysis/blob/main/petersen_graph.png), which is an undirected graph with 10 nodes and 15 edges, and [Tutte graph](https://github.com/doscsy12/network_sci_analysis/blob/main/tutte_graph.png), which has 3-regular polyhedron graphs with 46 nodes and 69 edges. 


|   | script                        | description                    |
|---|-------------------------------|--------------------------------|
| 1 | airline_network_data_analysis | analysing airline network data |
| 2 | epidemic_spreading_analysis   | predict vaccination strategy during pandemic | 
| 3 | viral_marketing_analysis      | analysing information spread thru social media |
| 4 | community_detection           | clustering behaviour           |


## 1. Airline network
Airport networks are crucial for understanding the spread of world-wide pandemics. Air-travel is one of the quickest ways that diseases can spread across the globe. For the airport network, an 'attack' is effectively the closure of an airport. Here, the **aim** is to know if it is possible to break the network apart, and stop the disease spread, by only attacking a few nodes (closing a few airports).

From the experiments, closing a few airports (with the most connectivity) would result in increase in diameter (i.e. shortest distance between two airports) and average path length (i.e. longest number of flights to reach anywhere in the world) within the airline network. These results are not surprising, as closing a few airports would mean having to perform more transits (somewhere else). 

Below is the airline network in Force Atlas 2 layout done in Gephi. The size of the nodes are airports with higher degrees (more connections in/out between other airports). 
<br>
<img src="https://github.com/doscsy12/network_sci_analysis/blob/main/airline_forceatlas2_1.png" alt="Airports in Force Atlas 2 layout" width="600"/>

## 2. Disease network
Networks (and network simulation), are a key tool in trying to predict the spread of worldwide pandemics. Many governments use modelling and simulation software (such as [GLEAMviz](http://www.gleamviz.org/)) to help them make decisions during an epidemic outbreak. Here, the **aim** is to build a simple model of disease spread on different artificial networks and investigate different vaccination strategies to try and prevent/ slow down the spread of the disease.

The network built here is based on the stochastic SIR (Susceptible, Infected, Removed) model, where *alpha* and *beta* describe the rate of removal (fraction of people moving from Infected to Removed) and the rate of infection (fraction of people moving from Susceptible to Infected) respectively. There is a level of known and unknown parameters, which is somewhat realistic, since governments may only have **some** information and data for different aspects of the pandemic. 

Having **any** vaccination strategy delays the average peak time and decreases the average total infected, compared to not having any vaccination strategy. Vaccinating the node (person) with the highest degree will be more effective against the disease, since the person will have the most personal interactions with other people. In reality, it is hard to implement, because should we vaccinate people based on the number of 'friends' in facebook/ instagram? 

## 3. Viral marketing
Social network platforms like Facebook or Twitter are becoming major sources of information channels. In these media platforms, everyone acts as both information generator and consumer. In a sense, the spreading of information, or opinions, shares some resemblance with disease spreading. Instead of the disease infecting one person to the next, information is spread from one person to the next. Hence the term 'viral marketing', which is used to define the information that goes viral in social media. 

The **aim** here is to explore the maximization of viral spreading by selecting the best set of initial seed nodes. In other words, what are the best seed nodes to start tweeting in the initialisation stage, such that the tweet/information can reach the widest population?

Similar to disease spreading, the model construct is based on the stochastic SIR model. From the simulations, bimodal behaviour was seen regardless of how the initial seed nodes were selected (randomly, by degree, by betweenness). This is due to the presence of a 'giant component' within the network. Thus, it was demonstrated that viral spreading can only occur when the information/tweet reaches a certain threshold in spreading strength. Thus, for any given network structure or model construct (SIR, linear threshold model, etc), there is a well-defined threshold before the information (or tweet) can be considered *VIRAL*. 
