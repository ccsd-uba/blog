+++
title = "Agents, game theory, and quantum computers: the Web3 AI Summit in San Francisco"
description = "Diego Kingston, CCSD's Research Director, took part in the Web3 AI Summit in San Francisco. This edition was dominated by AI agents, agentic payments, game theory applied to models, and the post-quantum transition."
date = 2026-09-11
[taxonomies]
tags = ["artificial intelligence", "cryptography", "zk", "conferences", "research"]
+++

This month, Diego Kingston, Research Director of our center, took part in the Web3 AI Summit in San Francisco, as he had in the three previous editions, to talk with researchers and industry leaders about the latest developments in web3 and its intersection with AI. This edition took a different direction from previous years: whereas the focus used to be on digital identity, privacy technologies, and selective disclosure, this time the agenda was dominated by AI agents and the post-quantum transition. This was to be expected, since AI has changed the way we do many things, including programming and searching for information, and it is only natural for the industry to start exploring what happens when agents begin to transact on their own.

The event ran over two days: the first devoted mostly to AI agents, and the second to zero-knowledge proofs and quantum computing.

## Agentic payments

Several companies are working on agentic payments, since these could enable new consumption habits and offer a better user experience and better prices, with no additional effort from the user. The general picture, well described in DeepMind's paper [Virtual Agent Economies](https://arxiv.org/pdf/2509.10147), is one in which you describe a simple intention (such as planning a trip or buying something) and the agent searches across different providers, pays small amounts to access better options, and comes back with a short list for the user's final approval. One of the points the paper raises is that these kinds of economies should be designed deliberately rather than left to emerge on their own, and that decisions such as how permeable the boundary between the agent economy and the human economy should be will determine whether the outcome is efficient and fair, or extractive.

While crypto and x402 offer a natural alternative for handling agentic payments, traditional payment providers are also taking part in this technology, going as far as issuing credit cards to agents. One of the analyses presented at the summit estimated that the volume of genuine agentic payments on x402 sits between 0.6% and 7.5% of total volume, which at the time of the study was around 52 million dollars. Even taking the upper bound, this shows that the infrastructure is still ahead of demand, although volume has been growing at a steady pace in recent months and agents are indeed already making commercial payments.

For all of this to be viable at scale, an efficient micropayment system is needed, since an agent that pays a fraction of a cent per query to several providers before it can give an answer will end up spending more on fees than the information is worth. That is why most of the teams we spoke with at the summit are building payment channels, which allow several microtransactions to be made off-chain, aggregated, and published as a single settlement on the L2 or L1.

## Game theory when the players are models

Another central topic was game theory applied to AI agents. Several groups showed use cases and simulations using Google DeepMind's [Concordia](https://github.com/google-deepmind/concordia) framework, which allows building simulated worlds populated by LLM-based agents. Recent work on [evaluating the generalization capabilities of LLM-based agents in mixed-motive scenarios](https://arxiv.org/pdf/2512.03318) uses Concordia to place agents in games where cooperation and self-interest are in tension, and finds that agents that behave cooperatively in familiar situations do not always generalize that behavior to new ones. This is more than a curiosity, since the agents being deployed today are starting to negotiate and transact on behalf of users.

There was also a discussion about whether these systems can exhibit chaotic behavior, in line with recent work on [paradoxes of game-theoretic equilibria and the price of anarchy](https://arxiv.org/pdf/2607.11752), which suggests that the equilibrium you design may not be the state the system actually converges to when the participants are learning algorithms. Finally, there were discussions on agentic personhood and which attributes an agent must exhibit to qualify as such, following the paper [A Pragmatic View of AI Personhood](https://arxiv.org/pdf/2510.26396), which frames that personhood not as a metaphysical threshold to be crossed, but as a bundle of rights and responsibilities that can be granted piecemeal, according to what we need agents to be able to do.

## ZK and the quantum timeline

The second day was devoted to cryptography, with a focus on developing and improving ZK proof systems using AI and on the challenges that still remain to be solved. There were also talks on the latest developments in neutral-atom quantum computers, their operating principles, and the improvements in the requirements for achieving a cryptographically relevant quantum computer, which keep coming down with every new estimate. The general feeling is that the deadline is approaching faster than expected, and one of the conclusions (which had also been heard in Rome earlier this year) is that, even if the timeline turns out to be longer, it is best to act as if it were short, given the level of uncertainty.

While some applications will be able to upgrade before these quantum computers become available, there are still important parts of the internet and of hardware that depend on elliptic curve cryptography, and migrating complex systems to new primitives is not something that can be done in a few days. Moreover, the signatures that guarantee multi-year commitments have to survive the "harvest now, decrypt later" window, not just withstand today's attackers.

Fortunately, Ethereum is already moving in this direction and leading the development of an aggregatable post-quantum signature scheme, useful for any blockchain.

## What we take away

Diego, who in addition to leading the center's research area works at Aligned, took the opportunity to talk about some of the ideas and products he has been working on there, with this new landscape in mind: AI agents doing commerce and the quantum threat drawing ever closer. Many of those conversations kept coming back to the same point: the need to verify someone else's computation, cheaply and with security that does not expire. At Aligned, work continues on the development of its zkVM (post-quantum secure by design) and on proof aggregation, as well as collaborating to have efficient protocols ready for this next stage.

For those of us at the center who closely follow the intersection of AI, cryptography, and decentralized systems, the summit leaves a clear picture of where the industry is heading. It was a joy to reconnect with so many colleagues in San Francisco and to see how the ecosystem keeps evolving. Now, back to building.
