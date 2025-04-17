# Pricing Reinsurance Deals under an Uncertain Mortality Rate Model

This project aims to explore different pricing methods for reinsurance deals in the context of an Uncertain Mortality Rate.

A **reinsurance deal** is a financial contract in which the insurer commits to delivering a predefined payoff to the policyholder based on the value of an underlying asset — either upon death (if it occurs before maturity) with a specific strike, or at maturity (if the policyholder is still alive) with another.  

In exchange, the buyer of the option pays a regular fee until death or contract maturity. The goal is to evaluate the fair price of such contracts under various mortality rate assumptions.

These financial products are most often purchased by insurance companies from financial institutions in order to hedge life insurance contracts they issue to their clients, who also pay them a regular fee.

To simplify the setting, we focus on a single source of default risk: the **risk of death**.

We begin by studying the pricing of such contracts under a **deterministic mortality rate**, using two Monte Carlo methods — one that simulates the time of death directly, and one that avoids doing so.

We then extend the model by assuming that the mortality rate is no longer constant, but instead varies within a known bounded corridor. In this more complex setting, we apply and compare two pricing approaches:

- 1-BSDE Approach  
- Adapted Longstaff-Schwartz Algorithm (based on the work of Julien Guyon)

These methods are compared in terms of the **variance of the pricing estimates**, and are also used to determine the value of the monthly fee that makes the contract **costless at inception**.

In the special case where the strike associated with the death payoff is set to zero, the contract becomes equivalent to a **put option** with monthly premium payments.

It has been observed that **policyholders often do not act optimally**, i.e., they fail to exit the contract when the continuation value becomes negative.  
This behavioral inconsistency is one of the key motivations behind the introduction of **Uncertain Mortality Rate Models**.

However, under the assumption that $K_D = 0$ and that the policyholder behaves optimally, the contract can be priced as an **American Put option**.  
We then compare the pricing obtained from the Uncertain Mortality Rate Model-specific Longstaff-Schwartz algorithm with the price of a standard American Put, computed using the classical Longstaff-Schwartz method.

This comparison helps assess the relevance and effectiveness of refined mortality modeling when pricing contracts subject to complex policyholder behavior.
