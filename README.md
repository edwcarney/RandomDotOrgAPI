# RandomDotOrgAPI.jl
Access the API at Random.org. Either <b>signed</b> or <b>basic</b> API will work with a parameter, <b>apiType</b>. If the apiType is set to "signed", the functions will generate requests with <i>Signed</i> after the word <i>generate</i> for the method. For example, a signed API request for UUIDs will be sent with method <i>generateSignedUUIDs</i>.

For information on each API:
  <p><b>signed</b> [https://api.random.org/json-rpc/2/signed] (requires registration with RANDOM.ORG)
  <p><b>basic</b> [https://api.random.org/json-rpc/2/basic])

For information about signatures, see this page: https://api.random.org/signatures

See the overview of API features here: https://api.random.org/features

From the RANDOM.ORG <a href="https://www.random.org/faq">FAQ (Q4.1)</a>:
<blockquote>The RANDOM.ORG setup uses an array of radios that pick up atmospheric noise. Each radio generates approximately 12,000 bits per second. The random bits produced by the radios are used as the raw material for all the different generators you see on RANDOM.ORG. Each time you use one of the generators, you spend some bits. By enforcing a limit on the number of bits you can use per day, the quota system prevents any one person from hogging all the numbers. (Believe us, this was a big problem before we implemented the quota system.)</blockquote>

## Current functions
- <b>getUsage()</b>: obtain current bit quota for your IP.
- <b>checkUsage()</b>: check if quota is non-zero.
- <b>getResult()</b>: get a stored signed result from RDO (stored >= 24 hours) <i>(signed API)</i>
- <b>verifySignature()</b>: obtain signature verification for a previously signed result from RDO  <i>(signed API)</i>
- <b>generateIntegers()</b>: obtain integers.
- <b>generateIntegerSequences()</b>: obtain randomized sequences of integers 1..N
- <b>generateStrings()</b>: obtain random strings of characters (upper/lower case letters, digits)
- <b>generateGaussians()</b>: obtain random Gaussian numbers
- <b>generateDecimalFractions()</b>: obtain random numbers on the interval (0,1)
- <b>generateUUIDs()</b>: obtain random bytes in various formats
- <b>generateBlobs()</b>: generate bit blobs of sizes in multiples of 8 in base64 or hex

Simply include the file with <b>include("RandomDotOrgAPI.jl")</b>. You may also place the module in a folder entitled <i>RandomDotOrgAPI/src</i> and add the folder to your Julia LOAD_PATH.

See https://en.wikibooks.org/wiki/Introducing_Julia/Modules_and_packages#How_does_Julia_find_a_module? for information on custom modules.

Random values are returned in JSON schemas in various formats (strings, integers, floats, etc.)

The use of secure HTTP by RANDOM.ORG prevents interception while the numbers are in transit. However, it is probably best not to use the Random.org site for any purpose that might have a direct impact on security. The FAQ (Q2.4) on the website says the following: "We should probably note that while fetching the numbers via secure HTTP would protect them from being observed while in transit, anyone genuinely concerned with security should not trust anyone else (including RANDOM.ORG) to generate their cryptographic keys."

Dependencies: HTTP, JSON
