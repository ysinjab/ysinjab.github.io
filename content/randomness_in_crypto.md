+++
title = 'Randomness in cryptography'
date = 2024-11-09T20:28:26+03:00
publishResources = true
+++

“There isn’t enoguh entropy in this secret word!” A sentence had me wondered what does entropy means? and what does it have to do with cryptography. In this post I will share with you reading notes I collected to understand how randomness is important in cryptography world.

Firstly, there are many cryoptographic algorithms out there that requires randomness at some point wether it is secret keys, IV, or noces etc. But what is the source of this randomness? Usually cryptographic applications extract randomness from observing hard-to-predict physical phenomena.

Some of entropy sources are keystrokes, mouse movements, or hard disk seek time and so on. But the problem with those are they are predectible at boot time. Other sources are called True random number generators such as those that comes from thermal noise. Read more here [Random number generation](https://en.wikipedia.org/wiki/Random_number_generation).

What is one issue with randomness from a noise? slowness. You can’t get unpredectible randomness from a noise if there is not enough entropy in it. What is entropy? It is a term used to tell how much an output is predectible such as: this sentence has high entropy means it is less predectible and vice versa.

So how operating systems generate randomness in case of low noise from entropy source. Answer is: pseudorandom number generators or [PRNGs](https://en.wikipedia.org/wiki/Pseudorandom_number_generator). Two of PRNG properties are determinism and indistinguishable from random.

In general: OSs get randomness for its cryptographically secure random number from noise sources, or from mixing and cleaning those sources if there are not enough entropy in it, or finally by using PRNG which is faster in comparison to the first two.
