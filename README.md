# RandomDotOrgAPI
Access the API (signed or basic) at Random.org See the API features here: https://api.random.org/features

Use various functions from https://random.org (q.v.).

# Currently available
- <b>getUsage()</b>: obtain current bit quota for your IP.
- <b>checkUsage()</b>: check if quota is non-zero.
- <b>getResult()</b>: get a stored signed result from RDO (stored >= 24 hours)
- <b>verifySignature()</b>: obtain signature verification for a previously signed result from RDO
- <b>generateIntegers()</b>: obtain integers.
- <b>generateIntegerSequences()</b>: obtain randomized sequences of integers 1..N
- <b>generateStrings()</b>: obtain random strings of characters (upper/lower case letters, digits)
- <b>generateGaussians()</b>: obtain random Gaussian numbers
- <b>generateDecimalFractions()</b>: obtain random numbers on the interval (0,1)
- <b>generateUUIDs()</b>: obtain random bytes in various formats
