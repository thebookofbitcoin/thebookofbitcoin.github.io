# Brainwallet

It's possible to consider ownership of Bitcoin simply knowledge of a random number, the private key that can control its transfer by signing a transaction that can be published to the Blockchain. With this in mind, a **brainwallet** is a concept to create a user friendly version of this private key that can be memorized, in the interests of security, or entertainment. In the early days of Bitcoin, this concept was entertained as a promising feature of the system, however consensus grew that instead of brainwallets being a useful tool the use of brainwallets was very likely to lead to loss of funds and that the practice should be strongly discouraged.

## Brain Wallet Strategies

One particularly bad, but simple and popular way of crafting a brain wallet is to simply take a random word or phrase and run it through a hashing algorithm to convert it into hashed number, or private key. Unfortunately this security model is very insecure: a brain wallet is not like a website password where there is a limiting factor on the attempts that can be made to guess it. A brain wallet attacker can guess unlimited times, and even come up with guesses ahead of time by building up a big dictionary of possible brain wallets. It's technically possible to make a brain wallet that would defeat guessing, but in practice people are very bad at accomplishing that task and there is no way to give feedback to let them know if they have accomplished it.

Given that the hurdle of creating an unguessable brain wallet is already very difficult for people, it is suggested that people simply allow a computer program to craft one instead. It's quite easy to come up with a secure storage key using a program: simply start any HD wallet and memorize the backup seed. 

This however moves the problem of a brain wallet to the next area of failure: human memory. Unfortunately, human memory is also a frequent source of failure, even a strongly entropic and unguessable brain wallet is still not recommended due to the possibility of mental error, unless the brain wallet is simply a complement to more reliable measures such as redundant securely stored paper copies.

