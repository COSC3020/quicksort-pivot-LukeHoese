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

The intuitive answer I immediately came to is that yes, median of three is more likely to produce a good pivot than selecting the first element with no further information. It is pretty easy to understand this on a base level, as worst case scenario for quicksort is when the selected pivot is the highest or lowest available element. By starting off with two comparisons you guarantee that there is at least one element higher than your pivot and at least one element lower than your pivot, which eliminates both worst case scenarios. It's hard to come to a definitive probability value for the medium of three method, but given that selecting the first element has a 50% chance of falling in the range of "good" pivots, and median of three eliminates the chance of choosing the highest or lowest value, thus eliminating at least one element that can be chose from each partition of "bad" pivots, we can assume that the odds of getting a "good" pivot are greater than 50%. Evaluating this from the point of view however leads us to the same calculations that were seen on the slides. The only guarantee of improved odds is a constant so when looking at larger data sets this is essentially ignored, leaving the number of expected splits to still be Θ(logn) and the number of total comparisons to still be Θ(nlogn), with the slide calculations still holding true.

Add your answer to this markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.
