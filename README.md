# SMAC
This repository contains Python and jupyter notebook files that teammate Amir Hossein Birzhandi and I coded for my internship and his Bachelor's thesis.
This project adds a new entity to the Starcraft multi-agent challenge([SMAC](https://github.com/oxwhirl/smac)) called Captain. The challenge is to win fights in an empty arena of the Starcraft game. There are many maps in the challenge; Our choice is the 5 marines vs 5 marines scenario.  Our team of agents is controlled by a centralized MARL algorithm called [QMIX](https://arxiv.org/pdf/1803.11485.pdf). This algorithm is specifically tested on SMAC in its paper and showed fascinating results compared to other algorithms([Demos on YouTube](https://www.youtube.com/watch?v=VZ7zmQ_obZ0). The agents in previous works had a fixed sight range of 9. However, we wanted to see whether we could reduce this range and still get the same results. That's how we started making a new agent called Captain. It receives the observation of all agents in each step and then decides whether to increase the sight from a range of 6 to 12. We have implemented 3 different captains. 

**QMIX Captain** the same configuration as the agents' Network
**QL Captain** Centralized DQN that gets all obs and gives all sights in one network
**IQL shared parameter Captain** Decentralized DQN for each agent, with periodic parameter sharing
**PPO Captain**  Centralized PPO network that gets all obs and gives all sights in one network continuously

The results have shown that all captains managed to successfully decrease sight range without much difference in the win rate. Meaning that the captain is giving sight to agents efficiently. The results of this work can be used in areas where there might be excessive data from sensors. These data are expensive to process and the concept of captain can be utilized to reduce the need for redundant sensors, thus reducing costs
