# Complexity

## Task

What is the complexity of the following functions (assuming they are implemented efficiently):

- max(double[] values)
- sort(double[] values)
- avg(double[] values)
- median(double[] values)
- stdev(double[] values)
- uniqueValuesCount(byte[] values)

## Result

- max(double[] values) -> O(N)
- sort(double[] values) -> O(Nlog(N))
- avg(double[] values) -> O(N)
- median(double[] values) -> O(Nlog(N))
- stdev(double[] values) -> O(N)
- uniqueValuesCount(byte[] values) -> O(N)

# Achiver

## Task

Is it possible to develop an archiver that would compress every possible file bigger than 1GB by at least one byte? Provide your reasoning.

## Result
* Quick answer -> no

* General idea. If we would have already some data, that is compressed to 1 GB size, then it wouldn't be possible to do it in reccuresion. 
* In theory we can't say *every* file, many -- yes, but every -- impossible.
* Compreesion is already operation, that decreases amount of information, so if we have more possible files than unique compressed representations, then more than two different files must be compresses to equal representation. 