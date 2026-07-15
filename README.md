# Game Theory and Texas Hold'em

An analytical study of Texas Hold'em poker through the lens of game theory and mathematical optimization. This project explores hand probabilities, the mechanics of counting "outs," and mixed-strategy Nash equilibria to understand what constitutes optimal decision-making under uncertainty.

---

## Introduction
Texas Hold'em is widely considered the most popular variant of poker. While its historical origins remain somewhat ambiguous—officially recognized by the Texas State Legislature as Robstown, Texas—the game has evolved into a deep, strategically rich environment. 

The objective of Texas Hold'em is to win chips either by having the best five-card hand at showdown or by forcing all other opponents to fold before the showdown. This dual objective creates a highly dynamic balance between mathematical probability and psychological deception (bluffing).

---

## Theoretical Framework

### 1. Game Theory Optimal (GTO)
Game Theory Optimal (GTO) is a defensive strategy aimed at maximizing long-term expected profit while minimizing the possibility of being exploited by opponents. It relies heavily on the concept of a **Nash Equilibrium**—a state in which no player can improve their expected outcome by unilaterally changing their strategy.

Texas Hold'em is modeled as an **extensive form game** because players make decisions sequentially over multiple stages (Preflop, Flop, Turn, River) with incomplete information.

### 2. Mixed-Strategy Nash Equilibrium Model
We analyze a simplified two-player (heads-up) model of Texas Hold'em where:
* **Player 1 (Bettor)** can either hold a strong hand ($S$) or bluff ($B$).
* **Player 2 (Caller)** can either call ($C$) or fold ($F$).

#### Payoff Matrix
The interaction is represented by the following normal-form matrix:

| Player 1 \ Player 2 | Call ($C$) | Fold ($F$) |
| :--- | :---: | :---: |
| **Strong ($S$)** | $(150, -150)$ | $(100, -100)$ |
| **Bluff ($B$)** | $(-50, 50)$ | $(100, -100)$ |

#### Derivation Summary
Let $p$ be the probability that Player 1 bluffs, and $q$ be the probability that Player 2 calls. By setting the expected values of each choice to be equal to find indifference, we derive:

$$EV_2(C) = EV_2(F) \implies 200p - 150 = -100 \implies p = 0.25$$

$$EV_1(B) = EV_1(S) \implies 100 - 150q = 100 + 50q \implies q = 0.25$$

The mixed-strategy Nash equilibrium occurs at:
$$\mathbf{[p = 0.25, q = 0.25]}$$

> **Key Takeaway:** Optimal play requires strict balance. Under this specific model, Player 1 must bluff exactly 25% of the time to remain completely unexploitable.

---

## Combinatorics & Hand Probabilities

Using the binomial coefficient formula to find the total number of unique 5-card hands from a standard 52-card deck:

$$\binom{52}{5} = 2,598,960\text{ combinations}$$

The hierarchy of hands, ranked from the most mathematically improbable to the most common, is shown below:

| Rank | Hand | Distinct Combinations | Probability |
| :---: | :--- | :---: | :---: |
| 1 | **Royal Flush** | $4$ | $0.00015\%$ |
| 2 | **Straight Flush** | $36$ | $0.0014\%$ |
| 3 | **Four of a Kind** | $624$ | $0.024\%$ |
| 4 | **Full House** | $3,744$ | $0.1441\%$ |
| 5 | **Flush** | $5,108$ | $0.197\%$ |
| 6 | **Straight** | $10,200$ | $0.393\%$ |
| 7 | **Three of a Kind** | $54,912$ | $2.11\%$ |
| 8 | **Two Pair** | $123,552$ | $4.75\%$ |
| 9 | **Pair** | $1,098,240$ | $42.26\%$ |
| 10 | **High Card** | $1,302,540$ | $50.12\%$ |

---

##  Expected Value & The 4-2 Rule

To make mathematically sound decisions during live gameplay, players calculate their **Expected Value (EV)**:

$$EV = (W\% \times \$W) - (L\% \times \$L)$$

Where:
* $W\%$ is the probability of winning (equity).
* $L\%$ is the probability of losing ($1 - W\%$).
* $\$W$ is the total pot size you stand to win.
* $\$L$ is the amount you must risk (the bet size).

During the hand, players use the **4-2 Rule** to approximate their winning percentage based on their "outs" (unseen cards that improve their hand):
* **On the Flop (with 2 cards left to come):** $W\% \approx 4 \times \text{Outs}$
* **On the Turn (with 1 card left to come):** $W\% \approx 2 \times \text{Outs}$

---

## Authors
* **Adam Barsotti**
* **Alexander Santos**
* **Cristian Cordova**

---

##  References
1. BetMGM. *The Rule of 4 and 2 in Poker*. (2023).
2. Bos, Tom. *What Is Expected Value in Poker?* GTO Wizard. (2022).
3. Feterik, Fiori, and Adam Biro. *Poker Outs Explained: Master Odds & Boost Your Edge*. (2026).
4. Wikipedia. *Poker Probability*. (2026).
5. PokerOrg. *Understanding Poker Equity*. (2024).
