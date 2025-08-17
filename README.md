# Greenwashing-Risk-Assessment-Tool
Greenwashing Risk Assessment Tool (GRAT) from my master's thesis (TU Delft &amp; Leiden). Developed for European electric utilities by combining environmental performance metrics with NLP-based sustainability report analysis. Adaptable to other sectors.

## Overview

The Greenwashing Risk Assessment Tool (GRAT) is a systematic framework for detecting greenwashing risk among electric utility companies through integrated environmental performance measurement and multi-dimensional communication analysis. Originally developed for European electric utilities, GRAT can be adapted for other sectors by modifying metrics, terminology, and sector-specific parameters.

The complete thesis document is included in this repository (in the docs folder) as a PDF. For detailed practical usage guidance, implementation steps, and data requirements, refer to Chapter 5 of the thesis.

## Research Background

This tool addresses three fundamental gaps in existing greenwashing detection literature: the performance-communication disconnect, lack of multi-dimensional communication analysis, and weight uncertainty in composite indicators. GRAT provides a transparent, theory-grounded approach to systematic greenwashing risk assessment suitable for regulatory screening, investment analysis, and academic research.

## Repository Structure

### Data Extraction & Processing (`01_data_extraction/`)
- **CDP climate data filtering**: Extraction and cleaning of emission data, targets, and renewable energy metrics
- **Refinitiv Eikon integration**: Third-party verified performance data processing  
- **Data harmonization**: Currency standardization and intensity metric alignment

### Performance Analysis (`02_performance_analysis/`)
- **Four core components**: Emission intensity, goal achievement, target ambition, and transparency
- **Constrained ensemble methodology**: 2,285 valid weight combinations within theoretical constraints
- **Sector-specific adjustments**: Renewable energy bonuses and target manipulation penalties

### Communication Analysis (`03_communication_analysis/`)
- **Text extraction and cleaning**: PDF processing using SpacyLayout for sustainability reports
- **Five communication dimensions**: 
  - Green communication intensity (sentiment and green term analysis)
  - Substantiation weakness (quantification, evidence, aspirational patterns)
  - Language vagueness (hedge words and unclear terminology)
  - Temporal orientation (future focus vs. timeline specificity)
  - Reporting consistency (year-over-year similarity analysis)
- **Rule-based NLP**: Transparent, interpretable methods using SpaCy and ClimateBERT

### Integration & Scoring (`04_integration_scoring/`)
- **Performance-Communication Gap (PCG)**: Primary greenwashing risk dimension
- **Final risk calculation**: Integration of five dimensions using ensemble methodology
- **59,881 weight combinations**: Systematic enumeration within theoretical constraints

### Validation (`05_validation/`)
- **External validation**: Mann-Whitney U testing against documented greenwashing cases
- **Sensitivity analysis**: Internal Validation testing across 17 weight variation scenarios
- **Statistical limitations**: Small sample size constraints acknowledged

## Key Features

**Constrained Ensemble Methodology**: Handles weight uncertainty by systematically examining all valid combinations within theoretical constraints rather than relying on arbitrary weight selection.

**Multi-Dimensional Detection**: Combines performance-communication gaps with communication quality issues that function as independent greenwashing indicators.

**Transparency and Interpretability**: Rule-based NLP approaches enable understanding of scoring rationale, essential for regulatory and investment applications.

**Sector Adaptability**: Framework structure allows modification for other industries through adjusted performance metrics, terminology, and weight hierarchies.

**Robust Validation**: Internal sensitivity analysis and external validation against real-world documented cases.

## Data Requirements

**Performance Analysis**:
- Scope 1 and 2 emissions data (self-reported and third-party verified)
- Emission intensity metrics with consistent denominators
- Target documentation (reduction percentages and target years)
- Renewable energy intensity (using similar consistent denominators)
- Minimum two consecutive years of data

**Communication Analysis**:
- English-language sustainability reports in digital format
- Aligned reporting periods across analysis years
- PDF documents suitable for text extraction

## Implementation Approach

1. **Performance Scoring**: Four components processed through constrained ensemble (2,285 combinations with current constraints)
2. **Communication Analysis**: Five dimensions calculated using rule-based NLP modules
3. **Integration**: Performance-Communication Gap calculation with communication quality dimensions
4. **Ensemble Scoring**: Final risk scores across 59,881 valid weight combinations (with current constraints)
5. **Validation**: Internal sensitivity analysis and external case validation

## Usage Notes

Execute notebooks sequentially by folder numbering. Each module includes data validation and produces ensemble statistics (mean, median, standard deviation, interquartile range). The methodology emphasizes median scores for final analysis while providing uncertainty ranges for confidence assessment. The code will not run as is because it requires specific data files. These files can be generated after completing the data analysis and by adjusting the code to extract the relevant metrics.

For implementation guidance, data preparation steps, and practical application instructions, see Chapter 5 of the thesis document.
For more detailed information check chapter 3.

**Validation Recommendations**: For new sector applications, conduct sensitivity analysis and validate against documented cases with minimum 30 companies for statistical power.

## Limitations (of my sample testing)

- English-language analysis only
- Sustainability reports as primary communication source
- Small sample validation (14 companies) provides indicative rather than conclusive results
- Emission intensity benchmarks dependent on available third-party data
- Pre-CSRD reporting period analysis with varied report structures

## Commercial Use Restrictions

This work is provided for academic and research purposes only. Commercial use, redistribution, or modification requires explicit written permission from the author. 

For commercial applications or licensing inquiries, contact: [LinkedIn](https://www.linkedin.com/in/aad-baartman-737a9b1a7)

## Citation

If you use this work, please cite:

Baartman, H. A. (2025). "Promises vs. Performance: A Multi-Dimensional Greenwashing Risk Assessment Tool Integrating Environmental Performance Data with NLP Communication Analysis." Master's Thesis, TU Delft & Leiden University.

## Contact

For questions about methodology, implementation, or potential collaborations:
[LinkedIn](https://www.linkedin.com/in/aad-baartman-737a9b1a7)
