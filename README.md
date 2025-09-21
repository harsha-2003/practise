# Project 2 – Gossip Protocal
**COP5615 - Distributed Operating Systems Principles**

---
## Group Info
* 1511-8670 Jonnala Harshavardhan Reddy
* 4453-0897 Chittela venkata sai Tarun Reddy

---
## Explanation

# Gossip Algorithm

The Gossip protocol is used for information propagation in distributed systems. It works by randomly spreading a rumor (message) among nodes until convergence is achieved.

Starting: One actor is initially given the rumor.

Step: Each actor randomly selects a neighbor and forwards the rumor.

Termination: An actor stops transmitting once it has heard the rumor a fixed number of times (e.g., 10).
This algorithm simulates how information spreads quickly in large networks, similar to how gossip spreads in real life.

# Push-Sum Algorithm

The Push-Sum protocol is designed for aggregate computation (e.g., computing averages).

State: Each actor maintains (s, w) values, where s is initialized with the actor’s ID and w = 1.

Send/Receive: Each actor sends half of (s, w) to a random neighbor while keeping the other half. When receiving, it adds the incoming values to its own.

Estimate: The ratio s/w represents the current estimate of the average.

Termination: When the ratio stabilizes (no significant change for several rounds), the actor stops.
This ensures all actors converge to the same global average without requiring central coordination.

# Topologies

The choice of network topology defines how actors communicate and strongly affects convergence speed.

Full Network: Every actor can communicate with all others. Fastest convergence, but least realistic.

3D Grid: Actors are placed in a 3D grid, with communication limited to direct grid neighbors. More realistic but slower convergence.

Line: Actors are arranged in a line, each communicating only with its immediate neighbors. Slowest convergence due to limited connectivity.

Imperfect 3D Grid: Similar to the 3D Grid, but each actor has one additional random neighbor. This improves performance by introducing randomness into the network.

# Bonus 

The project can be extended by simulating failure models, where nodes or connections may fail temporarily or permanently.

Node Failure: A node stops participating in communication.

Connection Failure: A link between two nodes becomes unavailable.
These scenarios test the robustness of Gossip and Push-Sum under realistic conditions. By experimenting with different failure rates, one can analyze how fault tolerance and convergence time are affected.
## What is working?  

* Implemented both Gossip and Push-Sum protocols using the actor model in Gleam.

* Supported network topologies: full, line, 3D grid, and imperfect 3D grid.

* Gossip protocol: Rumor spreads correctly, and convergence is detected once all nodes have received it the required number of times.

* Push-Sum protocol: Each actor maintains (s, w) values, exchanges them with neighbors, and converges once the ratio s/w stabilizes within a threshold.

* Convergence time is measured and reported accurately at the end of each simulation.

* The program scales to large numbers of nodes (tested successfully up to [insert your maximum tested nodes]) while maintaining correctness.

* Observed expected performance trends:

* Full topology converges fastest.

* Line topology converges slowest.

* 3D grid shows moderate convergence.

* Imperfect 3D grid improves upon regular 3D due to added random links.

* Bonus feature: Implemented a failure model (node and/or connection failures) controlled by a parameter, demonstrating resilience in full and imperfect 3D topologies.

## Instructions

* chmod +x ./run_simulation.sh
  * ./run_simulation.sh 5 line push-sum
  * ./run_simulation.sh 50 imp3D gossip
  * ./run_simulation.sh 100 full push-sum
  * ./run_simulation.sh 3000 3D gossip
    
## Output
# gossip full
![WhatsApp Image 2025-09-21 at 16 58 54_82a131d5](https://github.com/user-attachments/assets/8551ec69-982b-4023-bbc3-2c72cf897d10)

# gossip line

# gossip 3d
# gossip imp 3d

