# Vigilant Asset Allocation G4 Strategy Backtesting

<img src ="https://user-images.githubusercontent.com/53241405/224523507-5cc11cfe-d519-45da-a468-9065ca811b5c.png">

Vigilant Asset Allocation G4 (VAA G4) is a dual-momentum based investment strategy that aggressively monitors the market and reallocates portfolio funds based on the relative momentums of risk assets and safety assets.  It was created by Wouter Keller and JW Keuning, based on their paper <a href = "https://papers.ssrn.com/sol3/papers.cfm?abstract_id=3002624">"Breadth Momentum and Vigilant Asset Allocation."</a>  In contrast to traditional dual momentum strategies, VAA G4 monitors the market itself through the two asset types.  When all risk assets have positive momentum, the portfolio is allocated entirely into the risk asset with the strongest momentum  At any other time, the portfolio is allocated entirely into the safety asset with the strongest momentum. The combination of breadth momentum with a very defensive reallocation trigger results in a strategy which captures alpha consistently.  <a href="https://allocatesmartly.com/vigilant-asset-allocation-dr-wouter-keller-jw-keuning/">A more in-depth review is available here.</a>

# The Strategy Rules:

1. Calculate momentum scores for each asset on each monthly close.

momentumScore = (12*(currentMonthlyClose/lastMonthlyClose)) + (4*(currentMonthlyClose/thirdLastMonthlyClose)) + (2*(currentMonthlyClose/sixthLastMonthlyClose))+(currentMonthlyClose/twelvethLastMonthlyClose)-19

2. If all risk asset momentums are positive, allocate entire portfolio to the strongest momentum risk asset.

3. If any risk asset momentum is negative, allocate entire portfolio to the strongest momentum safety asset.

4. Reevaluate at the end of each month.

# Note
Backtesting is helpful for validating strategies against historical data, but may not accurately reflect fills, fees, slippage, or other faults of live market behavior.  As such, results should be taken as guidance towards, not guarantee of, success.  Results and code are provided for educational purposes only.

Special thanks to <a href="https://twitter.com/VolatilitySwan">@VolSwan</a> for the idea!

Special thanks to <a href="https://twitter.com/RobAgrees">@RobAgrees</a> for inital strategy code

Special thinks to <a href="https://twitter.com/jamiedubauskas">@jamiedubauskas</a> for the final polish and adding backtesting metrics
