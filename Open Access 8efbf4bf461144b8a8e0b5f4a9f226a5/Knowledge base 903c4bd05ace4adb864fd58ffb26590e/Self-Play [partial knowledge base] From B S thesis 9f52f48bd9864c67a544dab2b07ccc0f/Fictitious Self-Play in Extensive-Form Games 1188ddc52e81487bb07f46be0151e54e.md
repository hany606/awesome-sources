# Fictitious Self-Play in Extensive-Form Games

Importance: 7
Notes: Some interesting information about fictitious play, game theory and self-play and nash-equilbruim


Status: Done
Tags/Keywords: Game theory, selfplay
Type: Paper

[https://towardsdatascience.com/fictitious-self-play-30b76e30ec6a](https://towardsdatascience.com/fictitious-self-play-30b76e30ec6a)

## **Extensive Form Game**

Normal Form Games are modelled as a table where the actions (called strategies) of each player, are the headers of rows and columns, and the content of each cell is the payoff of the strategy employed by each player.

The problem of this form is that it does not capture the sequence or the time. For this reason, Extensive Form Game uses tree-like representations where each node is the player and each edge is the strategy, and the sequence can be clearly seen as the turn goes from node to node.

![Untitled](Fictitious%20Self-Play%20in%20Extensive-Form%20Games%201188ddc52e81487bb07f46be0151e54e/Untitled.png)

Note that for each Extensive Form Game, we can find a Normal Form Game that yields the same results.

## **Learning**

Learning aims to find what strategies to play to reach Nash Equilibrium so that we won’t lose (on average).Another way to say the same thing, the process of **learning** is to find the probabilities (or probability distribution) to use each strategy (or action) so that we won’t lose on average.

**Extensive-Form Fictitious Play (XFP)**

XFP suffers from the curse of dimensionality. At each iteration, computation needs to be performed at all stages of the game. This will lead to an exponential computation.
For this reason, Reinforcement Learning comes into play to create the Fictitious Self Play.

**Fictitious Self Play (FSP)**

Best response: FSP approximates the best response using the Reinforcement Learning method. As its name implies approximation means that best response is not computed but something close to it, which is the ε-best response.

Strategy update: FSP updates the average strategy as a supervised learning task, where each player learns a transition model of their own behaviour.

- Fictitious Play: is an iterative method that finds Nash Equilibrium in Two Player Zero Sum game. Its problem is that it applies to Normal Form Games which are tabular and do not capture time or sequence. Details can be found in the article “[Introduction to Fictitious Play](https://towardsdatascience.com/introduction-to-fictitious-play-12a8bc4ed1bb)”.
- Fictitious Self Play: is a method that fixes the problem of the Fictitious Play by integrating time/sequence by using Extensive Form Game. It also uses Reinforcement Learning to find an approximation of the best response and Supervised Learning to update the average strategy. It is proven that it can converge to a Nash Equilibrium. More details in the article “[Fictitious Self Play](https://towardsdatascience.com/fictitious-self-play-30b76e30ec6a)”

[https://towardsdatascience.com/neural-fictitious-self-play-800612b4a53f](https://towardsdatascience.com/neural-fictitious-self-play-800612b4a53f)