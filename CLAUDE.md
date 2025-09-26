# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Quarto extension template for creating research notebooks with structured analysis workflows. The template is designed for reproducible research with R code chunks, organized data analysis scripts, and standardized formatting. It can be installed via `quarto use template hubcad25/quarto-research-notebook`.

## Template Structure

### Core Extension Files
- `_extension.yml` - Extension configuration defining the Quarto template
- `template.qmd` - Base template file that serves as the starting point for new research notebooks

### Example Structure (in `code/` directory)
The `code/` directory demonstrates the intended research workflow structure:
- `cleaning.R` - Data cleaning and preprocessing scripts
- `codebook.R` - Variable definitions and data documentation
- `results/` - Analysis results and outputs
  - `results.qmd` - Main analysis document with structured sections
  - `r_scripts/` - Modular R analysis scripts organized by topic
  - `results_files/` - Generated figures, tables, and cached outputs

## Research Notebook Structure

### Analysis Document Structure
The template follows a standardized structure for research analysis:

1. **YAML Front Matter** - Document metadata, output formats, execution options
2. **Introduction** - Research questions and hypotheses
3. **Data Exploration** - Descriptive statistics with collapsible sections
4. **Hypothesis Testing** - Structured analysis by research question
5. **Results** - Statistical models and findings with proper documentation

### Code Organization
- **Modular R Scripts**: Analysis broken into logical chunks (e.g., `01_data_structure.R`, `02_descriptive_stats.R`)
- **Source Pattern**: Main document sources modular scripts using `source("code/results/r_scripts/filename.R")`
- **Caching**: Uses Quarto's built-in caching for computational efficiency
- **Figure Management**: Automated figure generation with proper labeling and captions

### Key Features
- **Collapsible Sections**: Uses HTML `<details>` tags to organize large amounts of descriptive statistics
- **Conditional Plot Display**: Checks for plot object existence before rendering
- **Standardized Chunk Labels**: Follows consistent naming patterns for code chunks and figures
- **Cache Management**: Implements smart caching strategy for time-intensive computations

## Development Workflow

### Creating a New Research Notebook
1. Use `quarto use template hubcad25/quarto-research-notebook` to create new project
2. Modify the base `template.qmd` with your research specifics
3. Organize analysis scripts in the `r_scripts/` directory following the modular pattern
4. Use the established chunk labeling and figure naming conventions

### Testing and Rendering
1. Test template rendering: `quarto render template.qmd`
2. Verify all R scripts execute without errors
3. Check that figures and tables generate correctly
4. Ensure cache files are properly managed

### Template Development
- Extension files should be in `_extensions/hubcad25/quarto-research-notebook/`
- Update `_extension.yml` version when making template changes
- Test template installation process with `quarto add` command
- Maintain example structure in `code/` directory as reference

## Code Conventions

### R Code Style
- Use descriptive variable names following snake_case
- Organize scripts by analysis phase (data structure, descriptive stats, hypothesis testing)
- Include proper error checking for plot object existence
- Use consistent library loading patterns at script start

### Quarto Document Conventions
- Use `#|` syntax for chunk options
- Follow established chunk labeling pattern: `fig-`, `tbl-`, analysis topic
- Include figure captions using `fig-cap` option
- Use cache strategically for computationally intensive chunks

### File Organization
- Keep raw data processing separate from analysis
- Use relative paths for reproducibility
- Maintain clear separation between scripts, outputs, and documentation
- Follow the established directory structure for consistency