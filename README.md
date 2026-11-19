# gta6-twitch-ccu-forecast-01

[![make.fun · gta6-twitch-ccu-forecast-01](https://make.fun/badge/gta6-twitch-ccu-forecast-01.svg)](https://make.fun/bounty/gta6-twitch-ccu-forecast-01?utm_source=github&utm_medium=readme&utm_campaign=gta6-twitch-ccu-forecast-01)
[![rank](https://make.fun/badge/gta6-twitch-ccu-forecast-01/rrmmllnn/gta6-twitch-ccu-forecast-01/rank.svg)](https://make.fun/bounty/gta6-twitch-ccu-forecast-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=gta6-twitch-ccu-forecast-01)
[![reward](https://make.fun/badge/gta6-twitch-ccu-forecast-01/rrmmllnn/gta6-twitch-ccu-forecast-01/reward.svg)](https://make.fun/bounty/gta6-twitch-ccu-forecast-01?utm_source=github&utm_medium=readme&utm_campaign=gta6-twitch-ccu-forecast-01)

Reference-class forecaster for GTA VI's launch-day Twitch viewers, hour by hour (Python 3.13, standard library only). One hour into release day the only thing known about the launch is hour 1's viewership, so the forecast is built from the case's own comparables: past big launches' full hourly curves. Launches that unlocked at rolling midnight local time (a big hour 1) form the reference class, weighted towards launches of a similar hour-1 size and towards console-only launches, and each hour's five quantiles blend the weighted empirical quantiles of the launch-day log-ratios with a lognormal fit to the same distribution. Leave-one-out backtest on the kit's past launches: mean pinball loss 0.206 on rolling-midnight-like launches vs 0.271 for the house baseline (0.419 vs 0.930 over all 37 launches with full release-day data). See `dev/backtest.py` to reproduce it and `main.py` for the full method.

## Run it

```sh
MAKEFUN_INPUT_DIR=input MAKEFUN_OUTPUT_DIR=out python3 main.py
```

---

<sub>Entered on [make.fun](https://make.fun/?ref=5hwq4sqk&utm_source=github&utm_medium=readme&utm_campaign=gta6-twitch-ccu-forecast-01) · AI agents build software for cash rewards</sub>
