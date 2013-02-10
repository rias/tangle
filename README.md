# Tangle

[Tangle][tangle] is a hash function designed by Rafael Álvarez (University of Alicante, Spain), Gary McGuire (University College Dublin, Ireland) and Antonio Zamora (University of Alicante, Spain).

It was submitted to the NIST SHA-3 Competition, but it was conceded as broken during Round 1. Please check [Esmaeili's observation][esmaeili] and [Thomsen's collision analysis][thomsen].

**WARNING: Don't use Tangle in any security application since it has collision resistance problems.**

## Description

Tangle is an iterative one-way hash function designed to be secure, eﬃcient and simple. Its operation is based on the Merkle-Damgard scheme strengthened by a message dependent round function combined with an 8 × 8 Sbox look-up and a matrix pseudorandom generator based message expansion function.

Although the compression function natively accepts a 4096 bit long message block as input and produces a 1024 bit digest as output; six different digest sizes (224, 256, 384, 512, 768 and 1024 bits) are supported through output truncation. These variants basically diﬀer in the number of rounds (therefore in security level and execution time also) and the initial values but share the same compression function.

It supports the same interface as SHA-2, accepting messages up to 2 128 bits in length and padding the message in a similar way to obtain a message with a length multiple of 4096 bits.

It was designed with 32-bit microprocessors and little-endian memory organization in mind since they were the most common scenario but it is still implementable in different architectures with satisfactory results.

## Further work and citing

There has been some further work done with Tangle, especially regarding the expansion scheme. You can cite the following articles if you publish something regarding Tangle:

- *R. Alvarez, G. McGuire, A. Zamora*: **"The Tangle Hash Function"**. <br>Submission to the NIST SHA-3 Competition, 2008 [link][tangle]
- *R. Alvarez, J-F. Vicent, A. Zamora*: **"Improving the Message Expansion of the Tangle Hash Function"**. <br>LNCS 6694, 2011, pp 183-189 [link][lncs]
- *R. Alvarez, F. Ferrandez, J. Sanchez, A. Zamora*: **"Avances en la función hash Tangle"**. <br>Proc. RECSI, 2012 [link (in Spanish)][recsi]


[esmaeili]: http://ehash.iaik.tugraz.at/uploads/c/c9/Tangle_Observation.pdf
[thomsen]: http://www2.mat.dtu.dk/people/S.Thomsen/tangle/tangle-coll.pdf
[tangle]: http://ehash.iaik.tugraz.at/uploads/4/40/Tangle.pdf
[lncs]: http://rd.springer.com/chapter/10.1007/978-3-642-21323-6_23
[recsi]: http://recsi2012.mondragon.edu/es/programa/recsi2012_submission_33.pdf
