# Crypto-Perpetual-Futures-Arb-Pitch

Attached is a short description of the pitch, for more detailed information please visit the PDF:

In cryptocurrencies, there are contracts called perpetual futures that never expire. Contracts only settle when both parties pay a fee for the contract to settle. In regular futures contracts, the price of the contract converges to spot near expiry, and so the price of the contract does not deviate too far from the underlying. In perpetual contracts, in order for the price of the futures contract to converge with the underlying, the following occurs:

1) If the price of the future is higher than the underlying, the long future positions pay a funding rate to short future positions (peer to peer)

2) If the price of the future is lower than the underlying, the short future positions pay a funding rate to the long future positions

The funding rate is a percentage paid out peer to peer and includes two components: the fixed interest rate (0.01%) and the premium. The premium is a percentage of the price difference between the perpetual contract and mark price. The funding rate is paid every 8 hours, and so theoretically the futures contract should converge to spot pretty frequently.

The arbitrage comes into play because depending on the price difference between the contract and the underlying, we can long / short the future and simultaneously long / short the underlying to receive the funding rate with no exposure to market fluctuations in price. If levels flip, and the price of the future crosses the underlying, then we simply reverse our position and avoid paying out the funding rate. For example, if the price of the future is higher than underlying, we long BTC and short BTC-perp, getting paid the funding rate every 8 hours. If the price of BTC-perp falls below BTC, we simply liquidate our current position and short BTC long BTC-perp. It is worth noting, however, that in the majority of cases the funding rate is positive.
