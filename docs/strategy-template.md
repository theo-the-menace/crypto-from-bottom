# Strategy specification template

Copy this file for each hypothesis. Complete it before tuning parameters.

## Identity

- Name and version:
- Author/date:
- Market and contract:
- Intended holding period:

## Hypothesis

What behavior should persist, and why might it exist after fees and competition?

## Rules

- Universe and exclusions:
- Data frequency and timezone:
- Entry conditions:
- Stop/invalidation:
- Profit-taking and trailing rules:
- Time stop:
- Position sizing formula:
- Maximum leverage and portfolio exposure:

## Test design

- Historical period:
- Training/validation/test split:
- Benchmark:
- Fees, spread, slippage, funding and latency assumptions:
- Look-ahead, survivorship and selection-bias checks:

## Results

- Number of trades and exposure:
- Expectancy and profit factor:
- Annualized return and volatility:
- Maximum drawdown and recovery time:
- Worst loss streak:
- Sensitivity to parameters and costs:

## Operations

- Paper-trading start/stop criteria:
- Kill switch:
- Monitoring and reconciliation:
- Conditions that invalidate or retire the strategy:
