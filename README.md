# RubySyncNodesRepo
MBC Ruby Test (This is a Testing repo for evaluation process only. it serve no functional purpose other than educational.)

# Consensus Simulation
The following project simulates a distributed system with multiple nodes communicating with each other to achieve consensus on a shared state.
It uses a simplified consensus mechanism (about 10% of the real algorith, it only focus on the functional low level, there is no hierarchy distribution) of algorithms like Raft or Paxos. 
The simulation handles network partitions and node failures gracefully and logs state transitions and messages exchanged between nodes.

Requirements
Ruby (3.0 was used, but should run from 2.5.0)

Installation
Clone the repository:

git clone git@github.com:aetrial/RubySyncNodesRepo.git

cd simulation
Ensure you have Ruby installed:

ruby -v
(Optional) Install Bundler and use it to install dependencies:

gem install bundler
bundler install

Running the Simulation
ruby meeteamTest.rb

Changing the Test Samples
It's possible to change testing logic by modifying test section logic. Please do so with care, declaration and initialization must be performed in order to avoid exceptions. 
you can edit the meeteamTest.rb file in the lowest section marked with comment.

Example changes:

# Adding a new node
node4 = Node.new(4)
node1.add_neighbor(node4)
node2.add_neighbor(node4)
node3.add_neighbor(node4)
node4.add_neighbor(node1)
node4.add_neighbor(node2)
node4.add_neighbor(node3)

# Proposing new states
node1.propose_state(10)
node2.propose_state(20)
node3.propose_state(5)
node4.propose_state(15)

# Simulating network partitions and recoveries
node3.simulate_partition([node1, node4])
node4.simulate_recovery([node1])
