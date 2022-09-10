# Brown's original fictitious play

Importance: 4
Notes: About Fictitious play with some interesting details but nothing useful for my current knowledge
Status: Done, Read it again!
Tags/Keywords: Game theory
Type: Paper

[https://towardsdatascience.com/introduction-to-fictitious-play-12a8bc4ed1bb](https://towardsdatascience.com/introduction-to-fictitious-play-12a8bc4ed1bb)

Fictitious play is a game theory concept. It consists of analyzing the game to figure out what is the best strategy to adopt when facing an opponent in a zero sum game.

Fictitious play is a method defined by George W. Brown in 1951, it consists of zero sum game and each player plays the best response to his opponent strategy. The aim of the method is to find the Game Value in an iterative way.

**As usual iterative methods are easier to compute than analytical methods when the problem gets complicated.**

Fictitious method is proven to converge to the theoretical game value (V). It is also proven that the **Fictitious Play converges to Nash equilibrium in two-player zero-sum game**.

## **Game Value**

The Game Value (V) is the number of points, money, credits, etc… that a player can expect to win (or lose) on the average, after playing a sufficiently large number of times. If V is positive we consider it in favor of the player I (so player II must pay), if V is negative we consider it favor of Payer II (so player I must pay).

## **Nash Equilibrium**

Nash equilibrium is a state where no player has any interest in changing his strategy because any change will be countered by others. Nash Equilibrium does not mean optimal equilibrium, there could be a strategy for one or more players that is more favorable to them, but the reason they can’t adopt it is because that theopponents (assumed smart enough) will counter them and the end result will become unfavorable. You can think of it as a deadlock, but it also can be beneficial for all.

A simple example is to imagine 2 robbers splitting their robbery in half. If one of them denounce the other to the police he can get the full spoils, but he has no interest in doing so because the other one will denounce him as well and they will end up both in jail. So splitting in half is the best solution for both of them.

## **Why would we seek Nash Equilibrium in AI ?**

Theoretically, Nash Equilibrium will guarantee, on average, no loss.

Meaning over a considerable number of games, on average the AI will draw or will win.
However, in practice, this is more optimistic. When playing against humans there is a high probability that the human player will make an error at one point, which the AI will exploit to win.

Another important question is why the AI instead of seeking Nash Equilibrium does not study the human strategy and exploit it to win.

The risk of this approach is that humans can learn to trick the AI, by giving it the impression that they are using some strategy, then switch to another.

For example suppose that in the game Rock Scissor Paper, the human gives 3 Scissor in a row, which leads the AI to assume that this is the strategy of the human. In the next move, AI will counter by a Rock, but the human (who laid the trap) will use Paper.

So the best strategy in this game is to stick to the Nash Equilibrium and use stochastic strategy (randomly choosing the item)