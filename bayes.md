**Bayes' Theorem**

I would like to highlight Bayes' Theorem, an method of calculating the probability of an event occurring, given that another event has occurred. The notation is quite simple, below is a the notation for the probability of $A$ occurring given that $B$ has occurred:

$$P(H|E)=\frac{P(E|H)*P(H)}{P(H)*P(E|H)+P(\neg H)*P(E|\neg H)}$$

* H, the hypothesis
* E, Evidences or observation.  
* P(E|H), the probability of seeing the evidence if the hypothesis is true. 
* P(E|\neg H), the probability of seeing the evidence if the hypothesis is false.

What makes Bayes useful is that it can be used to calculate the probability of event with only a limited amount of information, and continually update the probability was new information arrives. We can use idea for multiple things. I have used Bayes in a case, where I need to identify the authorship of articles. There were a single suspect in question, but no concrete evidence that allowing us to link the authorship to the suspect. Using word usage analysis on the documents we knew was written by the suspect and comparing it against the articles in question is was possible to calculate the probability that they was written by the suspect.

The reason I find this to be an important theorem investigator should be aware of, as privacy concerns starts to become more prominent in the public eye, the amount of data that can be acquired is starting to become limited. Making us work more in uncertainty, Bayes allowing you to work in the realm of probability. I recommend reading the books *Bayesian Statistics the Fun Way* and  _The theorem that would not die_ too get an better understanding of what Bayes´ can be applied to.
