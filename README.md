# COVID Fake Detection Project

This project aims to identify and analyze misinformation in social media posts related to COVID-19. By leveraging advanced natural language processing (NLP) techniques, it classifies posts as either factual or fake, helping to combat the spread of misinformation.

**Check [article](docs\article.md).**

## Features
- **VaccineFakeClassifier**: A model based on RoBERTa for detecting fake news.
- **VaccineFakeClassifierTrainer**: A trainer for fine-tuning the classification model on COVID-19-related datasets.
- **OcclusionAnalyzer**: Analyzes token importance for model predictions.
- **StatisticalAnalyzer**: Evaluates token impacts using masking-based statistical methods.

## Datasets
The project uses the following datasets from [Hugging Face](https://huggingface.co):
1. [nanyy1025/covid_fake_news](https://huggingface.co/datasets/nanyy1025/covid_fake_news?utm_source=chatgpt.com)
2. [justinqbui/covid_fact_checked_google_api](https://huggingface.co/datasets/justinqbui/covid_fact_checked_google_api)
3. [justinqbui/covid_fact_checked_polifact](https://huggingface.co/datasets/justinqbui/covid_fact_checked_polifact)

## Installation

### Prerequisites
1. Python 3.9 or later.
2. `pip` (Python package installer).

### Steps
1. Clone the repository:
   ```bash
   git clone https://github.com/AntonSHBK/covid_fake
   cd covid_fake_project
   ```

2. Set up a virtual environment:
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
## Documentation
Documentation for each module is available in the `docs/` folder.

## Contributing
Contributions are welcome! Feel free to submit issues or pull requests.

## License
This project is licensed under the MIT License.

## Contact
For questions or collaboration, reach out at [anton42@yandex.ru].

