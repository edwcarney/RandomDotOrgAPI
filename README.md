# RandomDotOrgAPI
Access the API (signed or basic) at Random.org See the API features here: https://api.random.org/features

Use various functions from https://random.org (q.v.).

# Current functions
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

Simply include the file with <b>include("RandomDotOrg.jl")</b>. You may also place the module in a folder entitled <i>RandomDotOrg/src</i> and add the folder to your Julia LOAD_PATH. See <a href="https://en.wikibooks.org/wiki/Introducing_Julia/Modules_and_packages#How_does_Julia_find_a_module?">here</a> for information on custom modules.

Values are returned in vector arrays of integers or strings.

The use of secure HTTP by RANDOM.ORG prevents interception while the numbers are in transit. However, is probably best not to use the Random.org site for any purpose that might have a direct impact on security. The FAQ (Q2.4) on the website says the following: "We should probably note that while fetching the numbers via secure HTTP would protect them from being observed while in transit, anyone genuinely concerned with security should not trust anyone else (including RANDOM.ORG) to generate their cryptographic keys."

using HTTP, Printf
