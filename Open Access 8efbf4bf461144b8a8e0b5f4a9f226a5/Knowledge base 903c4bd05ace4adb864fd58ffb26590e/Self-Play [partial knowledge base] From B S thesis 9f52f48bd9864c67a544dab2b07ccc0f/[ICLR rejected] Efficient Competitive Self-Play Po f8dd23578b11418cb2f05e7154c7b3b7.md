# [ICLR rejected] Efficient Competitive Self-Play Policy Optimization

*Evaluation of performance: They are using Elo score, and they showed the mean/average reward (Win-rate) (Did not understand this part correcty). 

They are making evaluation between models from different algorithms (Pairwise competition) among all the checkpoints. Each competition/evaluation round between two opponents has multiple of matches
*Opponent selection + Training: At the begining we have a population of e.g. 8 members, they run evaluation against all these 8 members, then they select the best opponent in terms of this evaluation and train against it

The problem that it is time consuming I believe with more populations not enough generalization, might not be good for hard tasks (continous action space, NvM, complicated tasks) (as they did not try with hard tasks only robot sumo)
Conference: ICLR
Importance: 8
Intervention: Some theoretical proof and some results for their new algorithm
Link: https://openreview.net/forum?id=99M-4QlinPr
Notes: It was submitted to ICLR 2021 but was rejected
Some theoretical proof and some results for their new algorithm
Status: Done
Type: Code, Preprint
Year: 2021

[new.pdf](%5BICLR%20rejected%5D%20Efficient%20Competitive%20Self-Play%20Po%20f8dd23578b11418cb2f05e7154c7b3b7/new.pdf)