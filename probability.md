## Probability (19 questions)


#### 1. Bobo the amoeba has a 25%, 25%, and 50% chance of producing 0, 1, or 2 offspring, respectively. Each of Bobo’s descendants also have the same probabilities. What is the probability that Bobo’s lineage dies out?
  - p=1/4+1/4*p+1/2*p^2 => p=1/2
#### 2. In any 15-minute interval, there is a 20% probability that you will see at least one shooting star. What is the proba- bility that you see at least one shooting star in the period of an hour?
  - 1-(0.8)^4. Or, we can use Poisson processes
#### 3. How can you generate a random number between 1 - 7 with only a die?
  - If generate a random number means a uniformly distributed random number, we need to roll the die twice, keep track of the first (r1) and second (r2) roll, there are 36 outcomes: (1,1), (1,2), ..., (6,6). If get (6,6), just re-roll the die twice again untill get a non-(6,6). So there are 35 equally probable results, and use the formula (r1 * 6 + r2) % 7 + 1 to generate a random number between 1 - 7.
  - If not uniform (not entirely fair), just roll the dice twice, get the value of first roll, and if the second roll is odd, add 1, else add 0.
#### 4. How can you get a fair coin toss if someone hands you a coin that is weighted to come up heads more often than tails?
  - Flip twice and if HT then H, TH then T.
#### 5. You have an 50-50 mixture of two normal distributions with the same standard deviation. How far apart do the means need to be in order for this distribution to be bimodal?
  - more than two standard deviations
#### 6. Given draws from a normal distribution with known parameters, how can you simulate draws from a uniform distribution?
  - plug in the value to the CDF of the same random variable (Probability Integral Transform)
#### 7. A certain couple tells you that they have two children, at least one of which is a girl. What is the probability that they have two girls?
  - 1/3 (conditional probability)
#### 8. You have a group of couples that decide to have children until they have their first girl, after which they stop having children. What is the expected gender ratio of the children that are born? What is the expected number of children each couple will have?
  - gender ratio is 1:1. Expected number of children is 2. let X be the number of children until getting a female (happens with prob 1/2). this follows a geometric distribution with probability 1/2
#### 9. How many ways can you split 12 people into 3 teams of 4?
  - the outcome follows a multinomial distribution with n=12 and k=3. but the classes are indistinguishable
  - the outcome is C(12,4)* C(8,4) / 3! = 12! / ((4!)^3 * 3!) = 5775
#### 10. Your hash function assigns each object to a number between 1:10, each with equal probability. With 10 objects, what is the probability of a hash collision? What is the expected number of hash collisions? What is the expected number of hashes that are unused.
  - the probability of a hash collision: 1-(10!/10^10)
  - the expected number of hash collisions: 1-10*(9/10)^10
  - the expected number of hashes that are unused: 10*(9/10)^10
#### 11. You call 2 UberX’s and 3 Lyfts. If the time that each takes to reach you is IID, what is the probability that all the Lyfts arrive first? What is the probability that all the UberX’s arrive first?
  - Lyfts arrive first: 2!*3!/5!
  - Ubers arrive first: same
#### 12. I write a program should print out all the numbers from 1 to 300, but prints out Fizz instead if the number is divisible by 3, Buzz instead if the number is divisible by 5, and FizzBuzz if the number is divisible by 3 and 5. What is the total number of numbers that is either Fizzed, Buzzed, or FizzBuzzed?
  - 100+60-20=140
#### 13. On a dating site, users can select 5 out of 24 adjectives to describe themselves. A match is declared between two users if they match on at least 4 adjectives. If Alice and Bob randomly pick adjectives, what is the probability that they form a match?
  - 24C5 * (5C4 * 19C1 + 5C5) / (24C5 * 24C5) = 4/1771 ≈ 0.2%
#### 14. A lazy high school senior types up application and envelopes to n different colleges, but puts the applications randomly into the envelopes. What is the expected number of applications that went to the right college?
  - Let Xi be the ith application, Xi = 1 if the application goes to the rigth college, and Xi = 0 otherwise. So that P(Xi=1) = 1/n, and E(Xi) = 1/n for all i = 1,2,...,n. Let Y = ∑Xi, then E(Y) = E(∑Xi) = ∑E(Xi) = n * 1/n = 1
#### 15. Let’s say you have a very tall father. On average, what would you expect the height of his son to be? Taller, equal, or shorter? What if you had a very short father?
  - Shorter. Regression to the mean
  - We would expect the son to be closer to the average height, thus, sons of very tall fathers will be on average shorter than their fathers, and sons of very short fathers will be on average higher than their fathers.
#### 16. What’s the expected number of coin flips until you get two heads in a row? What’s the expected number of coin flips until you get two tails in a row?
  - Let x be the expected number of coin flips required until get two heads in a row, if the first flip is tail, then need x more flips since the events are independent, and the probability is 1/2; if the first flip is head and second is tail, then still need x more flips, and the probability is 1/4; if the first is head and second is head, then the number is 2 and the probability is 1/4. 
  - Thus, we get x = 1/2*(1+x) + 1/4*(2+x) + 1/4 * 2 and x = 6.
#### 17. Let’s say we play a game where I keep flipping a coin until I get heads. If the first time I get heads is on the nth coin, then I pay you 2n-1 dollars. How much would you pay me to play this game?
  - less than $3
#### 18. You have two coins, one of which is fair and comes up heads with a probability 1/2, and the other which is biased and comes up heads with probability 3/4. You randomly pick coin and flip it twice, and get heads both times. What is the probability that you picked the fair coin?
  - P(HH|fair) = 1/4, P(HH|biased) = 9/16, and P(fair) = P(biased) = 1/2
  - Bayes' Rule, P(fair|HH) = P(HH|fair) * P(fair) / (P(HH|fair) * P(fair) + P(HH|biased) * P(biased)) = 4/13
#### 19. You have a 0.1% chance of picking up a coin with both heads, and a 99.9% chance that you pick up a fair coin. You flip your coin and it comes up heads 10 times. What’s the chance that you picked up the fair coin, given the information that you observed?
  - P(H|fair) = (1/2)^10, P(H|biased) = 1, P(fair) = 0.999, and P(biased) = 0.001
  - Bayes' Rule, P(fair|H) = P(H|fair) * P(fair) / (P(H|fair) * P(fair) + P(H|biased) * P(biased)) ≈ 0.4938
#### 20. What is a P-Value ?
  - P value is the probability, computed assuming that null hypothesis is true, that the test statistic would take a value as extreme or more extreme, in the direction of alternative hypothesis, than that actually observed.
  - https://en.wikipedia.org/wiki/P-value
