# Quicksort Pivots

in the lectures I only briefly mentioned strategies for determining a good pivot
for quicksort. The implementation on the slides simply picks the leftmost
element in the part of the array that we consider as a pivot. I also mentioned a
few other ways of picking a good pivot, e.g. randomly.

Median-of-three is also a good way of picking a pivot -- inspect the first,
middle, and last elements of the part of the array under consideration and
choose the median value. Using the probabilities for picking a pivot in a
particular part of the array (in the same way as we did on slide 34), argue
whether this method is more or less (or equally) likely to pick a good pivot
compared to simply choosing the first element. Assume that all permutations are
equally likely, i.e. the input array is ordered randomly.

Your answer must derive probabilities for choosing a good pivot and
quantitatively reason with them.

The intuitive answer I immediately came to is that yes, median of three is more likely to produce a good pivot than selecting the first element with no further information. It is pretty easy to understand this on a base level, as worst case scenario for quicksort is when the selected pivot is the highest or lowest available element. By starting off with two comparisons you guarantee that there is at least one element higher than your pivot and at least one element lower than your pivot, which eliminates both worst case scenarios. 

Diving Deeper (With help from Daniel Collins and trusty Slide 34):

First we will define the three types of numbers that can be chose for our median of 3.  
Numbers too large: L (1/4 chance)  
Numbers too small: S (1/4 chance)  
And numbers that would be 'good' pivots (1/2 chance)

Since we are picking 3 seperate numbers, each number can be any of the above types of numbers, meanign we have 3<sup>3</sup> or 27 unique combinations of numbers

combinations of numbers that are permutations of each other are all equally likely so we will group them and multiply the probability by the amount of permutations

to find the probability of each of these we will multiple out the odds of each of the individual elements of the combination (lowest common denominator will be 64 so I will convert all probabilities preemtively)

SSS (1/4)<sup>3</sup> = 1/64  
* MMM (1/2)<sup>3</sup> = 8/64  
LLL (1/4)<sup>3</sup> = 1/64  
SSM+ (1/4)<sup>2</sup> * (1/2) * 3 = 6/64  
SSL+ (1/4)<sup>3</sup> * 3 = 3/64  
* MMS+ (1/2)<sup>2</sup> * (1/4) * 3 = 12/64  
* MML+ (1/2)<sup>2</sup> * (1/4) * 3 = 12/64  
LLS+ (1/4)<sup>3</sup> * 3 = 3/64  
LLM+ (1/4)<sup>2</sup> * (1/2) * 3 = 6/64  
* SML+ (1/4)<sup>2</sup> * (1/2) * 6 = 12/64  

Combination sets where a good pivot would be chosen as the median are starred

adding up these probabilities gives us the odds of choosing a good pivot using median of 3

8/64 + 12/64 + 12/64 + 12/64 = 44/64 = 68.75%

Had help from Daniel Collins to stear me in the right direction (using combinations and probabilities of each element)

I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.
