# 🧪 Lottery Lab — Agent Handoff

## Project
Thai Lottery Statistical Analysis & Prediction App
- **Repo**: https://github.com/dmz2001TH/lottery-lab
- **Tech**: Pure HTML/CSS/JS — single `index.html` file
- **Owner**: dmz2001TH

## What's Done

### 1. Auto-Fetch API (v2.0)
- Source: `https://lotto.api.rayriffy.com` (scrapes sanook.com)
- Endpoints: `/latest`, `/list/[page]` (20/page), `/lotto/[id]`
- Coverage: ~480 draws (2010–2026)
- UI: Dropdown to select 20/50/100/200/all draws
- Function: `fetchLotteryData()` — paginated batch fetch with progress

### 2. Professional Prediction Engine
- `buildFreqData()` — builds exponential decay freq, position freq, markov transitions, gap analysis, position co-occurrence
- `scoreNumber(numStr, fd, method)` — scores any number across 4 signal types
- `generatePrediction(method, data, selected)` — scores ALL numbers, returns top-ranked
- `getPredictionAnalysis()` — detailed breakdown for UI display

**Methods available:**
| Method | Algorithm |
|--------|-----------|
| Ensemble | Weighted 30% + Markov 30% + Entropy 20% + Gap 20% |
| Weighted | Exponential decay frequency (λ=0.03) |
| Markov | Digit-level transition matrix + position interdependence |
| Entropy | Distribution balance + sum reversion |
| Gap | Overdue detection (√dampened) + repeat penalty |
| Hot/Cold | 60/40 split (legacy) |
| Position | Position-specific frequency only |
| Random | Control group |

### 3. Smart Backtest Engine (`LotteryBrain` class)
- Walk-forward validation: train on first 5, predict rest one-by-one
- Tracks: top-N hit rate, rank distribution, rolling accuracy
- Auto-predicts next draw using full brain

### 4. Other Features
- Chi-Square test for randomness validation
- Pattern detection: consecutive, repeating, bigram, odd/even ratio
- Accuracy scoreboard with cumulative tracking
- Export/Import JSON + PNG report
- Claude API integration (optional AI analysis)
- Dark/Light mode, mobile-first responsive

## Architecture

```
index.html (2000+ lines)
├── CSS: 230 lines — custom properties, dark theme
├── HTML: Tab-based panels (data/stats/pattern/predict/track/backtest/export)
├── JS Core:
│   ├── Data: getData/setData/saveData/fetchLotteryData
│   ├── Stats: frequency, position freq, streak, chi-square, patterns
│   ├── Predict: buildFreqData, scoreNumber, generatePrediction, getPredictionAnalysis
│   ├── Backtest: LotteryBrain class, runSmartBacktest
│   ├── Track: accuracy scoreboard, verify, cumulative chart
│   └── Export: JSON, PNG, API key management
└── External: Chart.js 4.4.7, html2canvas, Claude API (optional)
```

## Git Workflow

**⚠️ Push requires auth. To push from agent:**

```bash
cd /root/.openclaw/workspace/lottery-lab
# Token must be provided via environment — NEVER hardcode or commit
git remote set-url origin "https://USERNAME:${GITHUB_TOKEN}@github.com/dmz2001TH/lottery-lab.git"
git add -A && git commit -m "your message" && git push
# Clean up after push:
git remote set-url origin "https://github.com/dmz2001TH/lottery-lab.git"
```

Set token via: `export GITHUB_TOKEN=<token>` (session only, never in files)

## Possible Next Steps
- [ ] Add more prediction methods (neural net, LSTM simulation)
- [ ] Real-time update when new draw is published
- [ ] Compare prediction accuracy across methods visually
- [ ] Add confidence intervals / probability estimates
- [ ] Mobile PWA packaging
- [ ] i18n support

## ⚠️ Security Notes
- NEVER put GitHub tokens in files, commits, or chat
- Token was previously exposed — owner should revoke & regenerate
- All data stored in browser localStorage (client-side only)
- Claude API key stored in localStorage (user-managed)

---
*Handoff created: 2026-04-16*
