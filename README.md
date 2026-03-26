# A/B Testing Analytics Dashboard

A production-ready, single-file A/B testing analytics platform built with Plotly.js. Designed for data analysts, product managers, and statisticians to analyze randomized controlled experiments with statistical rigor.

## Features

### 🎯 Core Analytics
- **Experiment Selector**: Switch between 4 pre-configured A/B test experiments with different characteristics
- **Key Metrics Cards**: Real-time conversion rates, sample sizes, p-values, confidence intervals, and lift calculations
- **Conversion Rate Over Time**: Interactive line chart with 95% confidence bands showing daily conversion trends
- **Statistical Significance Tracker**: Running p-value visualization with significance threshold markers
- **Distribution Comparison**: Bell curves showing probability distributions of conversion rates for Control vs Variant

### 📊 Advanced Analysis
- **Performance by Segment**: Grouped bar charts breaking down conversion rates by customer segments (device type, geography, user cohort)
- **Bayesian Probability Gauge**: Visual indicator showing "Probability that Variant beats Control" using Beta-Binomial conjugate models
- **Sequential Testing Chart**: Cumulative lift visualization with Pocock decision boundaries for early stopping analysis
- **Detailed Statistical Table**: Comprehensive metrics including p-values, effect sizes, and significance badges

### 🔧 Interactive Tools
- **Sample Size Calculator**: Dynamically calculate required sample sizes based on:
  - Baseline conversion rate
  - Minimum detectable effect (MDE)
  - Statistical power
  - Significance level (α)

## Statistical Methods

### Hypothesis Testing
- **Two-Proportion Z-Test**: Used for comparing conversion rates between Control and Variant
- **P-Value Calculation**: Two-tailed hypothesis testing with standard normal distribution
- **Confidence Intervals**: Wilson score method for accurate binomial proportion intervals at 95% confidence

### Effect Size
- **Cohen's h**: Measures practical significance of differences between proportions
- **Lift Calculation**: Percentage difference relative to baseline conversion rate

### Bayesian Analysis
- **Beta-Binomial Conjugate Model**: Posterior probability computation using observed conversions and trials
- **Monte Carlo Sampling**: 10,000 simulations to estimate probability that Variant outperforms Control

### Power Analysis
- **Sample Size Determination**: Calculates required per-variant sample size using z-test formula with:
  - Type I error rate (α)
  - Type II error rate (β = 1 - power)
  - Effect size derived from baseline rate and MDE

### Sequential Testing
- **Pocock Method**: Decision boundaries for continuous monitoring and early stopping
- **Adaptive Monitoring**: Allows interim analyses while controlling familywise error rate

## Synthetic Data

All demo experiments use seeded pseudo-random number generation for reproducibility:

1. **Checkout Flow Redesign** - 1-page vs 3-page checkout (significant improvement)
2. **Pricing Page CTA** - Color variation test (marginal effect)
3. **Email Subject Line** - Personalization test (highly significant improvement)
4. **Onboarding Funnel** - Interactive vs static content (with segment-level Simpson's paradox)

Each experiment includes realistic daily fluctuations, segment breakdowns, and varying sample sizes.

## Tech Stack

- **Frontend Framework**: Vanilla JavaScript (no dependencies for core logic)
- **Visualization**: Plotly.js v2.x (CDN)
- **Statistical Computing**: Native JavaScript implementation
- **Styling**: CSS3 with dark theme and gradient accents
- **Responsive Design**: Mobile-first, works on all devices

## How to Run

1. **Clone the repository**
   ```bash
   git clone https://github.com/mayankjoshiii/ab-testing-dashboard.git
   cd ab-testing-dashboard
   ```

2. **Open in browser**
   - Simply open `index.html` in any modern web browser
   - No build step, no dependencies, no server required
   - Works completely offline once loaded

3. **Interactive usage**
   - Select different experiments from the dropdown
   - Adjust sample size calculator inputs to see real-time calculations
   - Hover over charts for detailed tooltips
   - All charts are fully interactive (zoom, pan, export)

## Design Highlights

- **Dark Theme**: Professional `#0f172a` background with gradient accents
- **Color Scheme**:
  - Control: Blue (#3b82f6)
  - Variant: Green (#10b981)
  - Accents: Purple, Amber, Red for supplementary data
- **Typography**: System font stack for optimal rendering
- **Responsive Grid**: Auto-adapts from 4 columns desktop → 1 column mobile
- **Glassmorphism**: Subtle backdrop blur and transparency effects
- **Smooth Interactions**: CSS transitions on all hover states

## Key Metrics Explained

### Conversion Rate
The proportion of users who completed the desired action (purchase, signup, etc.)

### Lift
Percentage improvement of Variant over Control: `(Variant - Control) / Control × 100%`

### P-Value
Probability of observing the data (or more extreme) if the null hypothesis (no difference) were true. Values < 0.05 indicate statistical significance.

### Confidence Interval
Range where we're 95% confident the true conversion rate lies, using Wilson score method for accuracy with small samples.

### Effect Size (Cohen's h)
Standardized measure of practical difference between proportions. Interpretation:
- 0.2: Small effect
- 0.5: Medium effect
- 0.8: Large effect

### Power
Probability of correctly rejecting the null hypothesis when a true effect exists. Standard: 80%

## Author

**Mayank Joshi**
MSc Business Analytics, Swansea University
[GitHub](https://github.com/mayankjoshiii) | [LinkedIn](https://linkedin.com/in/mayank-joshi-analytics)

## License

MIT License - See LICENSE file for details

## Browser Support

- Chrome/Edge 90+
- Firefox 88+
- Safari 14+
- Mobile browsers (iOS Safari, Chrome Mobile)

## Future Enhancements

- CSV data import for real experiments
- CUPED (Controlled experiment using Pilot)
- Multi-armed bandit analysis
- Custom experiment builder
- Export reports to PDF
- Dark mode toggle
- Additional segment visualizations
