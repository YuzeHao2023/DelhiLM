# Delphi Pipeline

This repository implements a **Delphi pipeline**, designed to aggregate expert opinions through iterative rounds of elicitation, leveraging large language models (LLMs). This implementation integrates probabilistic reasoning, scenario analysis, and Bayesian updates to support consensus-building for complex decision-making.

## Features

- **LLM-Based Expert Simulation**: Uses GPT-based models to simulate expert predictions.
- **Automated Round Management**: Dynamically manages rounds of expert elicitation and feedback.
- **Probabilistic Aggregation**: Calculates weighted mean probabilities based on expert dispersion.
- **Metaculus Integration**: Fetches resolved binary questions and human predictions for comparative analysis.
- **Interactive Visualizations**: Generates insightful plots to analyze consensus, calibration, and variability.
- **Bayesian Credible Intervals**: Constructs posterior distributions for robust probabilistic inference.

## Use Cases

- **AI Risk Assessment**: Evaluate the likelihood of critical outcomes in AI governance scenarios.
- **Forecasting**: Predict trends and events using structured probabilistic methods.
- **Policy Development**: Aggregate expert input to inform governance and regulatory strategies.
- **Research**: Study the reliability and calibration of expert predictions versus LLM-based forecasting.

## Getting Started

### Prerequisites

The code was developed and tested in a Google Colab environment. The following libraries are required:
- `openai`
- `httpx`
- `requests`
- `numpy`
- `pandas`
- `scipy`
- `seaborn`
- `matplotlib`

### Installation

1. Clone the repository:

```bash
git clone https://github.com/your-username/DelhiLM.git
cd DelhiLM
```

2. Set up environment variables for API keys (e.g., OpenAI, Metaculus):

```bash
export OPENAI_API_KEY="your-api-key"
export METACULUS_API_URL="your-api-url"
```

## Workflow

1. **Scenario Preparation**: Format and extract resolved binary questions from Metaculus.
2. **Delphi Elicitation**:
   - Query LLMs and/or human experts for probability estimates.
   - Aggregate responses and provide anonymized feedback.
   - Repeat until consensus (defined by standard deviation threshold) is achieved.
3. **Analysis**:
   - Compare elicited probabilities with human predictions.
   - Calculate calibration metrics (e.g., Brier scores).
   - Plot variability and Bayesian credible intervals.
4. **Results Visualization**: Visualize key metrics, including Brier scores and the variability of correct vs incorrect predictions.

## Notebook Structure

The notebook, `Delphi_LLMs.ipynb`, includes the following:

- **Data Preparation**: Fetch and process scenarios from Metaculus.
- **Elicitation Logic**: Implements multi-round querying of LLMs with adaptive feedback.
- **Statistical Analysis**: Calculates weighted means, standard deviations, and Bayesian updates.
- **Visualization**: Generates plots for calibration, variability, and scenario distributions.

## Key Functions

- `delphi_process_single_scenario`: Manages the Delphi process for a single scenario, querying experts iteratively until consensus.
- `calculate_weighted_mean`: Computes aggregated probabilities weighted by expert response dispersion.
- `plot_variability_correct_incorrect`: Compares variability in predictions for correct vs incorrect outcomes.
- `construct_bayesian_intervals`: Generates credible intervals using Beta distributions.

## Configuration

Adjust parameters in the notebook or configuration files to customize:
- Number of experts and rounds.
- Consensus standard deviation threshold.
- Bayesian prior parameters.

## Results

The pipeline outputs:
- Aggregated probabilities and their distributions
- Calibration metrics (e.g., Brier scores)
- Comparative analysis of LLM vs human predictions
- Visualizations for decision-making insights.

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository.
2. Create a new branch for your feature or bugfix.
3. Commit your changes with clear descriptions.
4. Submit a pull request.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.
