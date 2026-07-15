# Game Theory and Texas Hold'em

An analytical study of Texas Hold'em poker through the lens of game theory and mathematical optimization. This project explores hand probabilities, the mechanics of counting "outs," and mixed-strategy Nash equilibria to understand what constitutes optimal decision-making under uncertainty.

---

## 📖 Introduction
Texas Hold'em is widely considered the most popular variant of poker. While its historical origins remain somewhat ambiguous—officially recognized by the Texas State Legislature as Robstown, Texas—the game has evolved into a deep, strategically rich environment. 

The objective of Texas Hold'em is to win chips either by having the best five-card hand at showdown or by forcing all other opponents to fold before the showdown. This dual objective creates a highly dynamic balance between mathematical probability and psychological deception (bluffing).

---

## 🧮 Theoretical Framework

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

## 📊 Combinatorics & Hand Probabilities

Using the binomial coefficient formula to find the total number of unique 5-card hands from a standard 52-card deck:

$$\binom{52}{5} = 2,598,960\text{ combinations}$$

The hierarchy of hands, ranked from the most mathematically improbable to the most common, is shown below:

| Rank | Hand | Distinct Combinations | Probability |
| :---: | :--- | :---: | :---: |
| 1 | **Royal Flush** | $4$ | $0.00015\%$ |
| 2 |
