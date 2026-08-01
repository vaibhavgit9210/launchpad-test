# andaza

Order of magnitude estimation dojo. Ten Fermi questions per round; you answer with mantissa × 10^exponent, get scored in orders of magnitude, and every reveal shows the decomposition so you learn to derive, not memorise. Tracks your calibration bias (do you systematically over- or under-estimate?) across rounds in localStorage.

Single file, no dependencies, works offline.

- Live: https://vaibhavkumar.is-a.dev/launchpad-test/
- Screenshot hooks (rAF-free, deterministic): `#shot=home`, `#shot=quiz`, `#shot=reveal`, `#shot=summary`
- Headless Chrome needs `--timeout=20000` alongside `--virtual-time-budget` here: the analytics beacon's `setInterval` keeps virtual time alive and the run hangs without it.

Scoring: signed error s = log10(guess) − log10(truth); points = 100 × (1 − |s|/3), floored at 0. Bullseye ≤ 0.33 orders, ballpark ≤ 1, off-by-an-order ≤ 2, recalibrate beyond that.
