# Three popular shortest path algorithms and their applications in real life

This is my experiment with some popular shortest path algorithms, since A star is an improved version of Dijkstra I did not put it in this paper

# Efficiency comparison

| Algorithm      | Efficiency                                                   |
| -------------- | ------------------------------------------------------------ |
| Dijkstra's     | O(E + V) (binary heap) , O(E\*V)(no heap, no priority queue) |
| BellmanFord    | O(E\*V)                                                      |
| Floyd–Warshall | O(V^3)                                                       |

The Big O notation says that Dijkstra's algorithm is the fastest one and Floyd-Warshall is the slowest one but why in reality Floyd-Warshall is still used?

# Applications of three algorithm in real life

There are many application of shortest path algorithms in daily life. The most popular one could be
network routing. To route between network nodes, network has to determines the outgoing route of the
received packet. Figuratively, network is graph of billion of routers and all routers are connected by
communication lines, in graph language, they are edges. In order to select the routing among a pair of
routers, there is the need of finding the shortest path in the diagram. Even though, Dijkstra is the fastest algorithm for calculating the shortest path of a router to other routers, but if the problem states that there is a need of finding shortest path from random node network to other node, Dijkstra is slow since it always has to calculate its distance and predecessor tables. On the other hand, after creating distance and predecessor matrix, Floyd-Warshall has a better performance. That is why in real-life, Floyd-Warshall is picked to solve network routing problem.<br />

Dijkstra still can be shine in another computer networking problem. Modern computer networks usually use
dynamic routing algorithms, namely link state routing algorithm and distance vector routing algorithm. Link state routing protocol collects all kinds of information of the whole network, which constitute a topological database of routers. Open Shortest Path First (OSPF) is a typical protocol which is an internal gateway protocol which used to make routing decision within a single autonomous system. Besides, it is a specific implementation of Dijkstra algorithm. It mainly uses the algorithm to generates a tree without loops. Then starting from a router and passing the information to all the routers in the tree. Thus, all the routers is shared by all the state of the link. Each router is calculated in the local routing and avoids updating the routing table blindly.

The distance vector routing algorithm is that each router maintains a table. The table has the best path and route for each destination through exchanging the information with neighbouring routers to update the table information. RIP protocol is a dynamic routing protocol and uses the Bellman-Ford algorithm. The process of routing announcement is the process of the Bellman-Ford algorithm’s implementation. The routers collect all different paths to the destination and save the number of sites about information of each destination path. Any other information will be discarded, except the best route to the destination. The algorithm is distributed execution. All the routers are in the execution of the algorithm and the results are calculated together by allmachines. In OSPF, the algorithm only executes on one machine which is not distributed.<br />

Collaboration between algorithms can also be an option. For example, using both the Dijkstra algorithm and
the Floyd-warshall algorithm in an application that shows the availability of ambulance and accurate
information about victims and road conditions in an accident to help the first aid process for victims or
patients. This application applies Dijkstra's algorithm to determine the fastest travel time to the nearest hospital. The Floyd-warshall algorithm is implemented to determine the closest distance to the hospital. Data on some nearby hospitals will be collected by the system using Dijkstra's algorithm and then the system will calculate the fastest distance based on the last traffic condition using the Floyd-warshall algorithm to determine the best route to the nearest hospital recommended by the system. This application is built with the aim of providing support for the first handling process to the victim or the emergency patient by giving the ambulance calling report and determining the best route to the nearest hospital.<br />

# Conclusion

The shortest path issue is still one of the hottest topics in the research field. This paper introduces the basic principle of three shortest path algorithms and compares them by analyzing the time and space complexity. Besides, it summaries the application range of different algorithms.<br />
• The Dijkstra algorithm is the fastest algorithm comparison with others, however, it fails when graph
carries negative weight.<br />
• The Bellman-Ford algorithm can be a supplementary for Dijktra when there is a negative loop.
However, it only does negative loop detection.<br />
• The Floyd-Warshall the slowest algorithm among three but it can find shortest path from every node
in the graph.<br />
In many practical applications, these three algorithms are applied combinationally to maximise efficiency.
