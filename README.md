🤖 Adaptive Warehouse Coordination System
A C++ simulation system designed to schedule, assign, and route autonomous robots across a warehouse network using graph algorithms, priority task queues, and dynamic obstacle handling.
📌 Features
Dynamic Task Scheduling:Manages normal tasks via standard queues ($FIFO$) and urgent tasks via a custom priority queue based on task priority.
Shortest Path & Path Finding:Employs Dijkstra's Algorithm to calculate optimal paths and distance between warehouse nodes.
Supports Breadth-First Search (BFS) for graph exploration starting from any node.
Robot Selection & Dispatch:Evaluates available robots based on proximity to pickup location, battery capacity ($>15\%$), and current operational status.
Dynamic Network & Obstacle Management:Dynamically block or unblock pathways (simulating obstacles or structural maintenance).Handles basic path occupancy to avoid collisions and tracks failed/charging robot states.
System Diagnostics & Metrics:Displays real-time task status tracking, robot workloads, and basic performance summaries.
🏗️ Graph Topology & Warehouse NodesThe warehouse graph is configured with the following default nodes and bidirectional pathways:
Node IDLocation Name
0Storage
1Packing
2Loading
3Charging
4Receiving
5Dispatch
🛠️ Data Structures & Algorithms UsedGraphs (Adjacency List): Represents warehouse locations and pathways weighted by distance.
Dijkstra's Algorithm: Calculates shortest path distances between locations while ignoring blocked nodes.
Priority Queue (std::priority_queue): Manages urgent task queues using a custom comparator.
Queue (std::queue): Manages standard priority tasks.
Sets (std::set): Stores active task IDs, blocked pathways, and occupied movement paths for $O(\log N)$ lookup efficiency.
Maps (std::map): Maps task IDs to their current workflow statuses (Pending, Assigned, In Progress, Completed).
🚀 Getting StartedPrerequisitesC++ Compiler: g++ (GCC 4.8.1 or higher) supporting C++11 standard or later.
Make tool or standard CMake setup (optional).
CompilationCompile main.cpp using your preferred C++ compiler:g++ -std=c++11 main.cpp -o warehouse_system
ExecutionRun the compiled executable:./warehouse_system
💻 Usage & CLI InterfaceUpon execution, an interactive console menu provides the following options:
================================
 ADAPTIVE WAREHOUSE COORDINATION
================================
1. Display Warehouse Locations
2. Display Robot Details
3. Add Normal Task
4. Add Urgent Task
5. Process Next Task
6. Find Shortest Route
7. BFS Traversal
8. Block Pathway
9. Unblock Pathway
10. Mark Robot as Failed
11. Recharge Robot
12. Display Task Status
13. Performance Report
0. Exit
🤝 ContributingContributions are welcome! Feel free to open an issue or submit a pull request for new features such as multi-robot collision avoidance algorithms (A* or CBS), GUI integrations, or persistence logging.📄 LicenseThis project is open-source and available under the MIT License.
