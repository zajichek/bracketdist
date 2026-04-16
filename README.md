# bracketdist

The goal of `bracketdist` is simple: distribute probability mass across the possible set of tournament brackets.

P(b|data)

Essentially, we're interested in a Bayesian posterior of bracket probabilities so we can answer questions like:

1. What bracket is most likely (given our data/information entered into the model)?
2. What is the _effective_ number of bracket combinations?
  + For example, the NCAA tournament has 2^63 = 9 quintillion possible combinations. But if we had the (accurately estimated) posterior probability of each of those brackets, the hypothesis is that only a very small fraction of those make up almost all of the probability mass, making the effective number of brackets much smaller--which you might conclude that creating the perfect bracket is, while still very unlikely, not impossible.

This package provides the engine for estimating the bracket posterior distribution through simulation. The unit of analysis here is a _bracket_, not a game. But the game level is where all the customization occurs. Therefore, the main user interface is for being able to specify/customize the matchup model(s) to your own liking, then use the simulation engine to see how that plays out at the bracket level.

The other main subsequent idea this explores is th concept of bracket similarity. Even if we find the single most likely bracket, when theres trillions of possibilities, that doesnt give us much confidence. It may be the case that the most likely bracket has a very particular configuration. But then the next 20% of probability mass is distributed among brackets that have bery similar components/subbrackets (e.g., the same final 4 but slight differences in earlier rounds). Thus the pool of that information would suggest we should accumulate info across those brackets. So we need to introduce a level of bracket similarity and then group things accordingly.

Focus is initially on the NCAA Men's Basketball Tournament, but could extend this to any bracket tournamnet structure (in theory)

Some useful reference work:

* [https://predicting-march-madness.streamlit.app/](https://predicting-march-madness.streamlit.app/)
* [https://github.com/markjrieke/2025-march-madness](https://github.com/markjrieke/2025-march-madness)
