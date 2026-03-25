# bracketdist

Simulate bracket distributions with custom probability models

The goal of `bracketdist` is simple: assign the distribution of probability mass across the possible set of tournament bracket configurations.

P(b|data)

Essentially, we're interested in a Bayesian posterior of bracket probabilities so we can answer questions like:

1. What bracket is most likely (given our data/information entered into the model)?
2. What is the _effective_ number of bracket combinations?
  + For example, the NCAA tournament has 2^63 = 9 quintillion possible combinations. But if we had the (accurately estimated) posterior probability of each of those brackets, the hypothesis is that only a very small fraction of those make up almost all of the probability mass, making the effective number of brackets much smaller--which you might conclude that creating the perfect bracket is, while still very unlikely, not impossible.

This package provides the engine for estimating the bracket posterior distribution through simulation. The unit of analysis here is a _bracket_, not a game. But the game level is where all the customization occurs. Therefore, the main user interface is for being able to specify/customize the matchup model(s) to your own liking, then use the simulation engine to see how that plays out at the bracket level.

Focus is initially on the NCAA Men's Basketball Tournament, but could extend this to any bracket tournamnet structure (in theory)
