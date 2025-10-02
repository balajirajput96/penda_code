# Penda Health Clinical Analysis

This repository contains code for analyzing clinical data and AI-assisted clinical decision-making at Penda Health clinics.

## Overview

This project analyzes clinical documentation, AI recommendations, and patient outcomes from a clinical study conducted across multiple Penda Health clinic locations. The analysis includes:

- Clinical decision rule evaluation
- AI response analysis with severity classifications (Green, Yellow, Red)
- Clinical documentation processing (history, investigations, diagnosis, treatment)
- Statistical analysis of clinical outcomes

## Repository Structure

- `types_os.py`: Core data models and type definitions using Pydantic
  - `Color`: Severity levels (Green=1, Yellow=2, Red=3)
  - `ClinicalDecisionRule`: Types of clinical decisions
  - `AIResponse`: AI recommendation responses
  - `AICall`: Individual AI interaction records
  - `AICalls`: Collection of AI calls with analysis methods
  - `ClinicalDocumentation`: Patient clinical records

- `analysis_os.ipynb`: Jupyter notebook containing data analysis and visualization
  - Data loading and preprocessing
  - Statistical analysis (Mann-Whitney U tests, Fisher's exact tests, etc.)
  - Visualization of clinical outcomes
  - Comparison between AI-assisted and non-AI visits

## Installation

### Prerequisites

- Python 3.8 or higher
- pip package manager

### Setup

1. Clone the repository:
```bash
git clone https://github.com/balajirajput96/penda_code.git
cd penda_code
```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

## Usage

### Running the Analysis

1. Open the Jupyter notebook:
```bash
jupyter notebook analysis_os.ipynb
```

2. Run the cells sequentially to perform the analysis.

### Using the Type Definitions

```python
from types_os import (
    Color,
    ClinicalDecisionRule,
    AIResponse,
    AICall,
    ClinicalDocumentation
)

# Example: Validate clinical documentation
doc = ClinicalDocumentation(
    Gender="Female",
    Age="25y 3m",
    Allergies="None",
    # ... other fields
)

# Access formatted sections
print(doc.history)
print(doc.diagnosis)
```

## Data Models

### Color Severity Levels
- **Green (1)**: Normal/no concerns
- **Yellow (2)**: Warning/requires attention
- **Red (3)**: Critical/immediate action required

### Clinical Decision Rules
- Treatment Recommendation
- Diagnosis Evaluation
- Clinical Notes
- Vitals & Chief Complaint Evaluation
- Investigation Recommendations

## Analysis Features

The notebook performs:
- Data merging and preprocessing
- Clinical documentation validation
- AI call analysis by rule type
- Statistical comparisons between AI and non-AI visits
- Outcome tracking and visualization
- Location-based analysis across clinic regions

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Copyright

Copyright (c) 2025 Penda Health and OpenAI

## Contributing

This is a research repository. For questions or collaboration inquiries, please contact the repository maintainers.

## Acknowledgments

This work was conducted in collaboration between Penda Health and OpenAI to evaluate AI-assisted clinical decision-making in resource-limited healthcare settings.
