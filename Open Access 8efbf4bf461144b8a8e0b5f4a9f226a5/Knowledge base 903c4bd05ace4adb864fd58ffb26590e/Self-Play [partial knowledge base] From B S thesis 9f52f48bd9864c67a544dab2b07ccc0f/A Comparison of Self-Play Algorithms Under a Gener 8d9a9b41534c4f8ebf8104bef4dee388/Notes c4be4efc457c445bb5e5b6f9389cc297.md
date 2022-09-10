# Notes

Extracted Annotations (1/14/2022, 12:21:43 AM)

"We present a formalized framework, with clearly defined assumptions, which encapsulates the meaning of self-play as abstracted from various existing self-play algorithms." (Hernandez et al 2021:1)

"This framework is framed as an approximation to a theoretical solution concept for multiagent training." (Hernandez et al 2021:1)

"However, it is not clear how to define a pragmatic solution concept when training a single policy in a multi-agent system, for an agent's optimal strategy is dependent on behaviours of the other agents that inhabit the environment." (Hernandez et al 2021:1)

"An initial solution is to compute the expected reward obtained by a given policy defined over the entire set of all possible other policies in the environment, which is intractable in all but toy scenarios." (Hernandez et al 2021:1)

"To approximate this solution, traditional multi-agent RL (MARL) methods would train and benchmark a policy against a set of preexisting fixed agents, using as a success metric the relative performance against these agents." (Hernandez et al 2021:1)

"These methods rest on two assumptions. Firstly, the availability of benchmarking policies at training and testing time. Secondly, these existing policies dominate, in a game theoretical sense, most of the policy space." (Hernandez et al 2021:1)

"However, this approach features many flaws. if this benchmarking set of is too small, the trained policy may overfit to the" (Hernandez et al 2021:1)

"What about the cases in which we don't have access to these learning resources? Such as when developing a new game for which no prior expert information is known, and for which any hand-crafted evaluation functions yields a fruitless policy." (Hernandez et al 2021:1)

"Authors such as [3] began experimenting on self-play (SP). SP is an open-ended learning training scheme which arises in the context of multi-agent training. A SP training scheme trains a learning agent purely by simulating plays with itself, or with policies which have been generated during training" (Hernandez et al 2021:1)

"it is of paramount importance to define meaningful metrics to inform this open-ended learning process." (Hernandez et al 2021:1)

"Historically, SP lacks a formal definition, and notation is often not shared among researchers. This has led to isolated, and sometimes conflicting, conceptions of what constitutes SP as a training scheme in MARL" (Hernandez et al 2021:1)

"The notion of SP has been present in the game playing AI community for over half a century." (Hernandez et al 2021:2)

"which derived a backgammon playing policy by performing supervised learning on expert datasets" (Hernandez et al 2021:2)

"More recently, AlphaGo [8] used a combination of supervised learning on expert moves and SP to beat the world champion Go player." (Hernandez et al 2021:2)

"It is often assumed that a training scheme can be defined as SP if, and only if, all agents in an environment follow the same policy, corresponding to the latest version of the policy being trained." (Hernandez et al 2021:2)

"naive SP" (Hernandez et al 2021:2)

"The authors claim that such version of SP aims at training a policy which is able to defeat random older versions of itself, ensuring continual learning." (Hernandez et al 2021:2)

"Which agents will be added into this "historical" set of policies and (2) which of these agents will populate the environment. Different takes on (1) and (2) spawn different SP algorithms." (Hernandez et al 2021:2)

"This is because by leaving a single agent learning in a stationary environment, the fixed agents' influence on the environment is stationary [12]." (Hernandez et al 2021:2)

"This is of genuine importance, given that most RL algorithms' convergence properties heavily rely on the assumption of a stationary environment [13]. SP algorithms can leverage the assumption that they are using SP, so they can provide the learning agent with a label denoting which combination of agent behaviours inhabits the environment," (Hernandez et al 2021:2)

"A normal form game is a tuple ( Π , U , n) where n is the number of players, Π = (Π 1 , . . . , Π n ) is the set of joint policies, one for each player. U : Π → n is a payoff table mapping each joint policy to a scalar utility for each player." (Hernandez et al 2021:2)

"A game is symmetric if all players feature the same policy set ( Π 1 = . . . = Π n ) and the payoff associated to each joint policy depends only on the policies and not on the identity of the players." (Hernandez et al 2021:3)

"2 player normal form games (n = 2 ) are typically defined by a tuple ( , B )" (Hernandez et al 2021:3)

"If = T the game is symmetric. Most importantly for us, if = − the game is zero-sum." (Hernandez et al 2021:3)

"W π ∈ n × n denote an empirical winrate matrix also known as a meta-game ." (Hernandez et al 2021:3)

"An evaluation matrix [4] is a meta-game represented by an antisymmetric matrix . One can turn an empirical winrate matrix W into an antisymmetric matrix by performing the element wise operation a i,j = w i,j − 1 2 , shifting the range of each entry from [0 , 1] to [− 1 2 , 1 2 ] . Symmetrical 2-player zerosum games represented by an antisymmetric matrix feature a unique maxent Nash [4], a fact we will use in Section V." (Hernandez et al 2021:3)

"A Nash equilibrium is then computed ( π , π ) for the zero-sum game defined by π , π . The relative population performance is the value v for the meta-player 1: v = n π · π , π · n T π ." (Hernandez et al 2021:3)

"Finally, the relative population performance [4] is a population-level meassure of performance. Given two populations 1 , 2 , it yields a single scalar value comparing the performance of 1 against 2 . It is computed by generating an evaluation matrix for both populations π , π which is then treated as a 2-player zero-sum game. A Nash equilibrium is then computed ( π , π ) for the zero-sum game defined by π , π . The relative population performance is the value v for the meta-player 1: v = n π · π , π · n T π . A positive v indicates that 1 wins on average against population 2 , with the opposite being true if v is negative, v = 0 indicates both populations are equivalent." (Hernandez et al 2021:3)

"Multiagent Reinforcement Learning" (Hernandez et al 2021:3)

"Self-play training schemes can be conceived as modules which extend the MARL loop by introducing a functionality prior to, and after, every episode." (Hernandez et al 2021:3)

"The policies present in the environment can either be exact copies of the policy being trained, or policies derived indirectly from it, taken from the menagerie." (Hernandez et al 2021:4)

"Self-play can be conceived as a bottom up approach towards computing a set of policies, π o , to be used as a proxy for the entire policy space Π in equation 1." (Hernandez et al 2021:4)

"Naive Self-Play:" (Hernandez et al 2021:4)

"All agents share the same behaviour." (Hernandez et al 2021:4)

"To capture this, the policy sampling distribution Ω puts all probability weight to the latest π ." (Hernandez et al 2021:4)

"The policy sampling distribution chooses opponents from the menagerie which are similar in skill to the currently training agent. Where agent skill is meassured by Elo ratings." (Hernandez et al 2021:5)

"The gating function is analogous to the selection, crossover and mutation phases of an evolutionary algorithm." (Hernandez et al 2021:5)

"M operates on a meta-game generated by doing head-tohead matches between all policies in the menagerie, whereas a policy sampling distribution Ω operates directly on the menagerie." (Hernandez et al 2021:5)

"The extent to which PSRO and our framework overlap is left for future work." (Hernandez et al 2021:5)

"In this section we present a novel policy sampling distribution that alleviates on the shortcomings of the δ -Uniform sampling distribution and a novel qualitative metric for the efficiency of the menagerie when it comes to using it as a proxy to the whole policy space." (Hernandez et al 2021:5)

"In supervised learning approaches, training datasets are fixed before training commences. This yields a stationary distribution from which training examples are drawn. RL suffers from sequential and correlated data collection during training, rendering a nonstationary distribution over training samples." (Hernandez et al 2021:5)

"By sampling uniformly at random from a menagerie, we observe a bias of the policies sampled from Ω towards earlier policies." (Hernandez et al 2021:5)

"Intuitively, earlier policies are sampled more often by virtue of being electable to sampling more times than recently added policies." (Hernandez et al 2021:5)

"However, we worry that by sampling earlier policies too often the learning policy will be biased towards interacting with, often random, initial agents." (Hernandez et al 2021:5)

"This worry is furthered by empirical evidences stating that, in certain board games, the quality of the fixed policies being used during training is directly proportional to potential quality of the policy being trained [26]" (Hernandez et al 2021:5)

"With this in mind, we present a novel policy sampling distribution, named δ-Limit Uniform, that gives increased probability to later policies." (Hernandez et al 2021:6)

"An attempt to amend the δ- Uniform bias." (Hernandez et al 2021:6)

"This visual display comes from a 2D embedding of the state trajectories experienced by an agent during each training episode." (Hernandez et al 2021:6)

"As previously stated, an ideal SP would yield policies that always beat previous ones." (Hernandez et al 2021:8)

"For RirRPS, this implies that the populations generated by all SP as training progresses are of similar quality, furthering the idea that in highly cyclic games individual policy improvement is not meaningful, even when there is potential to exploitation due to repetitions in RirRPS." (Hernandez et al 2021:9)

"However, we are surprised to find naive SP performing better than δ = 0 -Uniform and PSRO, which is not obvious by just looking at the winrate matrices from Figure 3." (Hernandez et al 2021:9)

"Future work will study other possibilities presented within the expressive capabilities of our SP framework. For instance, there is no research exploring which policy sampling distribution works best for different types of environments." (Hernandez et al 2021:10)