# Michael Sharp

Analyst, FX and Credit Trading at Crédit Agricole CIB, London.
MEng Chemical Engineering, University of Birmingham.

I work on quantitative problems in dealer markets: how to quote and hedge
client flow, how to execute against an order book, and how far a simulator
can be trusted before a result from it means anything. Python, C++, SQL;
kdb+/q for tick data.

## Research projects

Each repository states the question, the data, the method and one
out-of-sample result, with known-answer tests and CI. Client flow and RFQ
data are not public, so the client layer is a calibrated simulation around
a real reference price, and crypto order books stand in for FX where
order-level data is needed; every README says which parts are real.

**[fx-skew-internalisation](https://github.com/m-ichaels/fx-skew-internalisation)** — FX dealer skew, internalisation, adverse selection and price reading.
C++ event-driven dealer simulator and numerical HJB solver extending
Barzykin–Bergault–Guéant (2023) with tier-specific adverse selection and
skew-reading clients (Barzykin et al., 2025), hedging impact, last look, and
an online mark-out toxicity classifier feeding an internalise-or-externalise
rule. On EURUSD ticks with a calibrated client layer the extended policy
withdraws skew from the skew-reading tier, cuts adverse-selection losses from
−$130k to −$23k per day and raises P&L per unit variance by 28 % over the
2023 model; it survives a mid-day toxicity shock that sends Avellaneda–Stoikov
and GLFT negative. Exact P&L decomposition, 39 known-answer tests.

**[lob-execution-sim](https://github.com/m-ichaels/lob-execution-sim)** — order-book execution simulator and TCA.
One C++20 engine with replay, queue-reactive and zero-intelligence simulator
modes behind a FIX 4.4 gateway; self-recorded Binance, Coinbase and Bitstamp
L2/L3 feeds; kdb+ tick store and Parquet/DuckDB research layer. The ranking
of TWAP / VWAP / Almgren–Chriss / OFI-adaptive schedulers changes with the
simulator mode and with latency, so the first result is that the simulator
is part of the model. What is robust across modes: a passive fill at the
touch is marked out 300–500 ticks against you within 100 ms, being filled is
negatively correlated with the next return (ρ ≈ −0.5), and every L2
queue-position model overstates the queue ahead by ~20 % against 21,687 real
order-by-order fills. 52 known-answer tests.

**Yield-curve market making with RL and event data** — in progress.
SOFR/Treasury curve construction (monotone-convex bootstrap vs kernel-ridge),
PCA factor risk, closed-form multi-tenor quotes (Bergault et al., 2021;
Barzykin–Ciceri, 2026) as the benchmark a distributional-RL quoter with
FOMC/ECB text features has to beat on the risk–return frontier.

## Publication

Sharp, M., Tzouras, A., Liu, Q., Zhang, K., Heidary, H., and Sarruf, B. J. M.
*Long-term stability of Ce-Cu modified Ni-8YSZ electrodes under both fuel
cell and co-electrolysis operation.* International Journal of Hydrogen
Energy, in press, 2026.

[LinkedIn](https://linkedin.com/in/-michael-sharp) · m.chaelsharp@gmail.com
