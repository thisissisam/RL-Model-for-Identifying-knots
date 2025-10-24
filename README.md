# RL-Model-for-Identifying-knots
Reinforcement Learning Model for simplifying knots through braid operations and identifying them

## How it works
Every knot can be uniquely represented as a braid (an element of the braid group). When the braid's ends are connected (also called clousere of the braid) it becomes a knot (or a link). when braid relations and markov moves act on braids, they dont change the underlying knot. Using these operations one can simplify a knot (usually decreasing the crossing numbers). Once the braid has been simplifyed, it then searches if the braid exists in the braid-knot database, if not then it tries to further simplify and repeats this process.
