# Project 2 – Gossip Protocal
**COP5615 - Distributed Operating Systems Principles**

---
## Group Info
1511-8670 Jonnala Harshavardhan Reddy
4453-0897 Chittela venkata sai Tarun Reddy

---
## Explanation

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

chmod +x ./run_simulation.sh

./run_simulation.sh 5 line push-sum
./run_simulation.sh 50 imp3D gossip
./run_simulation.sh 100 full push-sum
./run_simulation.sh 3000 3D gossip



