
# OrderLineDecorator Indicator for NinjaTrader 8

The **OrderLineDecorator** is a custom indicator designed for NinjaTrader 8 that enhances the visual display of active stop and target orders in the Chart Trader panel. By overlaying informative labels directly next to your order lines on the chart, it provides at-a-glance insights into the potential risk and reward of your trades. This forked and updated version (originally based on Gemify's OrderLineDecorator) introduces normalization features, making it particularly useful for traders managing multi-contract positions. It helps streamline decision-making by automating calculations that would otherwise require manual effort, reducing cognitive load during live trading.

**Especially useful and convenient for prop traders migrating off of ProjectX to Tradovate which does not have this feature natively**
This was forked from Gemify. This used to be on the ninja trader ecosystem but it was pulled. I treid reaching out to this Gemify but he's unreachable. My specific contribution is the normalization features. 
## To install properly, download the current version from releases page, not the source code. It should have a sha256 hash.
<img width="760" height="540" alt="image" src="https://github.com/user-attachments/assets/0c4aa783-dc8d-4e86-b67e-d585c3cf3de8" />


Follow me on these
- https://x.com/imRobbieRobski
- https://www.youtube.com/@CoastToCoastTradersPodcast
- https://www.youtube.com/@RobbieRobski
---
## How It Works

- Decoration Labels: For each qualifying order (stops or targets), it generates a customizable label box positioned just to the left of NinjaTrader's built-in order UI element. The label includes details like order type (STOP or TARGET), quantity, and user-selected metrics.
- Supported Order Types:
    - Stops: StopMarket, StopLimit, MIT (Market If Touched).
    - Targets: Limit orders.
- Visibility Requirement: The Chart Trader must be enabled and visible for the decorations to appear. If hidden, the indicator automatically disables rendering to avoid unnecessary processing.
- Updates Dynamically: Labels refresh on price changes, order updates (e.g., fills, modifications), or account item changes (e.g., unrealized P&L), ensuring accuracy without manual intervention.
- Display what's IMPORTANT TO YOU!
    - Ticks
    - Points
    - Currency
    - Percentage
- Normalization feature allows you view each value as if it were a single position.

	Examples. Suppose you have a long position on MNQ of 3 contracts where you want to risk 10 points, take profit on 2 for 20 points, and hold a 3rd for 40 points)
		
- And assuming you are displaying, Tics, Currency, and Points, the labels would appear like this:
	- STOP (3): -120T : -30p : ($60)
	- TARGET (2): 160T: 40P: $80
	- TARGET(1):160T: 40P: $80
- If you were to use Normalize, they would appear like this instead:
	- STOP (3): -40T : -10p : ($20)
	- TARGET (2): 80T: 20P: $40
	- TARGET(1):160T: 40P: $80
![RobbieRobskiOrderLineDecorator-example](https://github.com/user-attachments/assets/8d74b87f-cb2d-4ba0-b237-b21daa624bb8)

NOTE: The value in () represents the number of orders in that order/group, not for example first scale target, second scale target, etc. 

---
Key Features and Benefits
##This indicator transforms basic order lines into powerful analytical tools, offering several benefits for day traders, scalpers, and position traders:

1. Multi-Metric Display for Quick Risk/Reward Assessment:
    
    - Ticks (T): Shows the distance from entry price in ticks (e.g., +10 T or -5 T). Benefit: Ideal for precise, short-term trading where tick-level granularity matters, helping you evaluate stop distances or targets instantly.
    - Points (P): Displays the point value difference (e.g., +2.5 P). Benefit: Useful for instruments like futures where points represent larger price moves, allowing easy comparison to your strategy's parameters.
    - Currency Value ($): Calculates the dollar impact based on point value and quantity (e.g., $150.00). Benefit: Quantifies real monetary risk or reward, promoting better money management and preventing overexposure.
    - Percent of Account (%): Expresses the currency value as a percentage of your account's cash value (e.g., 1.25%). Benefit: Encourages risk-aware trading by highlighting how much of your capital is at stake, aligning with rules like the 1-2% risk per trade guideline.
    
**No more mental math**

![RobbieRobskiOrderLineDecorator-Settings](https://github.com/user-attachments/assets/d92d9c59-ad28-4fab-945e-74c11e265e6a)


