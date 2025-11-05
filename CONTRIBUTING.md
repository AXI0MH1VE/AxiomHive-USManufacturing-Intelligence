# Contributing to AxiomHive US Manufacturing Intelligence

Thank you for your interest in contributing to the AxiomHive US Manufacturing Intelligence project. This document provides guidelines for contributing to ensure high-integrity, fact-based collaboration and data validation.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Core Principles](#core-principles)
- [How to Contribute](#how-to-contribute)
- [Data Integrity Standards](#data-integrity-standards)
- [Validation Requirements](#validation-requirements)
- [Pull Request Process](#pull-request-process)
- [Issue Reporting](#issue-reporting)
- [Documentation Standards](#documentation-standards)

## Code of Conduct

We are committed to providing a welcoming and professional environment for all contributors. We expect all participants to:

- Be respectful and constructive in all interactions
- Focus on facts and data-driven discussions
- Maintain professional and courteous communication
- Support collaborative problem-solving

## Core Principles

All contributions to this project must adhere to the following core principles:

### 1. **Fact-Based Analysis**
- All data contributions must be verifiable and sourced from reliable sources
- Claims and insights must be supported by documented evidence
- Opinions should be clearly distinguished from factual data
- Cite sources for all external data and information

### 2. **Data Integrity**
- Maintain accuracy and precision in all data handling
- Document data transformations and processing steps
- Preserve data provenance and lineage
- Never modify raw data without clear documentation

### 3. **Transparency**
- Clearly document methodologies and assumptions
- Make analytical processes reproducible
- Disclose limitations and potential biases
- Provide clear reasoning for analytical decisions

### 4. **Quality Over Quantity**
- Prioritize accurate, validated contributions over rapid additions
- Thoroughly test and validate before submitting
- Focus on meaningful improvements to the project

## How to Contribute

### Getting Started

1. **Fork the Repository**: Create your own fork of the project
2. **Clone Your Fork**: Clone the repository to your local machine
3. **Create a Branch**: Create a feature branch for your contribution
   ```bash
   git checkout -b feature/your-feature-name
   ```
4. **Make Changes**: Implement your changes following our standards
5. **Test Thoroughly**: Validate your changes meet all requirements
6. **Submit Pull Request**: Open a PR with clear description

### Types of Contributions

We welcome contributions in the following areas:

- **Data Additions**: New datasets relevant to US manufacturing
- **Analytics**: New analytical methods or insights
- **Documentation**: Improvements to documentation and guides
- **Bug Fixes**: Corrections to errors or issues
- **Visualizations**: New ways to present manufacturing data
- **Tools**: Utilities that enhance project usability

## Data Integrity Standards

### Data Sources

All data must meet the following criteria:

1. **Verifiable Sources**: Use only reliable, verifiable data sources
   - Government agencies (Census Bureau, BLS, BEA, etc.)
   - Established research institutions
   - Peer-reviewed publications
   - Industry associations with transparent methodologies

2. **Documentation**: Include comprehensive source documentation
   - Source URL or citation
   - Date of data collection/publication
   - Data collection methodology (if available)
   - Known limitations or caveats

3. **Version Control**: Track data versions and updates
   - Use clear version numbering
   - Document changes between versions
   - Maintain changelog for datasets

### Data Quality Checks

Before submitting data contributions:

- [ ] Verify data completeness (no unexpected missing values)
- [ ] Check for logical consistency
- [ ] Validate data types and formats
- [ ] Ensure temporal consistency in time-series data
- [ ] Cross-reference with related datasets when possible
- [ ] Document any data cleaning or preprocessing steps

## Validation Requirements

### Code Validation

All code contributions must:

1. **Be Tested**: Include appropriate tests for new functionality
2. **Be Documented**: Include clear inline comments and docstrings
3. **Follow Standards**: Adhere to project coding standards and style guides
4. **Be Reproducible**: Ensure results can be consistently reproduced

### Analytical Validation

Analytical contributions must:

1. **Show Your Work**: Document all steps in the analytical process
2. **Justify Methods**: Explain why analytical methods were chosen
3. **Validate Results**: Cross-check results using alternative methods when possible
4. **Assess Uncertainty**: Quantify and communicate uncertainty in findings
5. **Peer Review**: Have analysis reviewed by at least one other contributor

## Pull Request Process

### Before Submitting

1. **Update Documentation**: Ensure all documentation reflects your changes
2. **Run Tests**: Verify all existing tests pass
3. **Add Tests**: Include tests for new functionality
4. **Check Style**: Ensure code follows project style guidelines
5. **Review Checklist**: Complete the PR checklist (below)

### Pull Request Checklist

Your pull request should include:

- [ ] Clear, descriptive title
- [ ] Detailed description of changes
- [ ] Reference to related issues (if applicable)
- [ ] Documentation updates
- [ ] Test coverage for new code
- [ ] Data source documentation (for data contributions)
- [ ] Validation results
- [ ] Screenshots/visualizations (if applicable)

### Review Process

All pull requests will be reviewed for:

1. **Alignment with Core Principles**: Adherence to fact-based, high-integrity standards
2. **Technical Quality**: Code quality, testing, and documentation
3. **Data Integrity**: Verification of data sources and quality
4. **Impact**: Value added to the project

Reviewers may:
- Request changes or additional information
- Suggest improvements
- Ask for additional validation
- Request clearer documentation

## Issue Reporting

### Reporting Bugs

When reporting bugs, please include:

- Clear, descriptive title
- Detailed description of the issue
- Steps to reproduce the problem
- Expected vs. actual behavior
- Environment information (OS, software versions, etc.)
- Screenshots or error messages (if applicable)

### Requesting Features

Feature requests should include:

- Clear description of the proposed feature
- Use case and rationale
- Potential implementation approach
- Expected benefits to the project

### Reporting Data Issues

For data-related issues, provide:

- Specific dataset and version
- Description of the issue
- Evidence of the problem
- Suggested correction (if known)
- Source documentation

## Documentation Standards

### Code Documentation

- Use clear, descriptive variable and function names
- Include docstrings for all functions and classes
- Comment complex logic or non-obvious implementations
- Keep comments up-to-date with code changes

### Data Documentation

- Provide README files for new datasets
- Include data dictionaries defining all fields
- Document units, scales, and data types
- Explain any codes or categorical values
- List known limitations or caveats

### Analytical Documentation

- Document analytical objectives
- Explain methodology and approach
- Describe data sources and preprocessing
- Present results with context and interpretation
- Discuss limitations and uncertainties

## Questions and Support

If you have questions about contributing:

1. **Check Existing Documentation**: Review README and project wiki
2. **Search Issues**: Look for similar questions in closed issues
3. **Open a Discussion**: Use GitHub Discussions for general questions
4. **Contact Maintainers**: Reach out to project maintainers for specific guidance

## Attribution

Contributors will be acknowledged in the project README and/or CONTRIBUTORS file. Significant contributions may warrant co-authorship in any resulting publications or presentations.

## License

By contributing to this project, you agree that your contributions will be licensed under the same MIT License that covers the project. See the LICENSE file for details.

---

Thank you for helping maintain the high standards of integrity and quality that make this project valuable to the US manufacturing intelligence community.
