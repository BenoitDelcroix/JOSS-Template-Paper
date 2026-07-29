# JOSS Template Paper

A template repository for preparing scientific papers to submit to the [Journal of Open Source Software (JOSS)](https://joss.theoj.org/).

## About JOSS

The Journal of Open Source Software is a developer-friendly journal for research software with a focus on quality, sustainability, and openness. JOSS accepts papers describing research software that solve research problems and are designed to be used by other researchers.

## Getting Started

### Prerequisites

To build and preview your paper, you'll need:

- **Git**: For version control and GitHub workflow
- **Pandoc**: For converting Markdown to PDF and other formats
- **LaTeX/TinyTeX**: For PDF generation (pandoc requirement)
- **Docker** (optional): For reproducible builds without local dependencies

### Quick Setup

1. **Use this template**: Click "Use this template" on GitHub to create a new repository for your paper.

2. **Clone your repository**:
   ```bash
   git clone https://github.com/YOUR_USERNAME/your-paper-repo.git
   cd your-paper-repo
   ```

3. **Edit the paper files**:
   - `paper.md`: Main paper content with YAML frontmatter
   - `paper.bib`: BibTeX bibliography entries
   - `README.md`: This file (optional to keep)

## File Structure

```
├── paper.md          # Your paper content and metadata
├── paper.bib         # Bibliography entries
└── README.md         # This file
```

## Writing Your Paper

### paper.md Format

The `paper.md` file contains:

1. **YAML Frontmatter** (header between `---` markers):
   - `title`: Paper title
   - `authors`: Author information (names, ORCIDs, affiliations)
   - `affiliations`: Author affiliations with indices
   - `date`: Publication date
   - `bibliography`: Reference to your BibTeX file
   - `tags`: Keywords for your paper

2. **Markdown Body**:
   - Structure your paper with sections
   - Use standard Markdown formatting
   - Reference citations using `@key` notation (e.g., `@Pearson:2017`)
   - Use `![](path/to/image.png)` for figures

### Example YAML Header

```yaml
---
title: 'Your Paper Title'
tags:
  - keyword1
  - keyword2
authors:
  - name: Your Name
    orcid: 0000-0000-0000-0000
    affiliation: 1
affiliations:
  - name: Your Institution, Country
    index: 1
date: 1 January 2024
bibliography: paper.bib
---
```

### Author Information

- **ORCID**: Get a free ORCID at [orcid.org](https://orcid.org/) for better research attribution
- **Affiliations**: List all author affiliations and reference them by index
- **Corresponding Author**: Mark with `corresponding: true`
- **Equal Contributors**: Mark with `equal-contrib: true`

## Building Your Paper

### Using Pandoc (Local)

```bash
pandoc paper.md -o paper.pdf --citeproc
```

For PDF output with better formatting:

```bash
pandoc paper.md -o paper.pdf --citeproc --template eisvogel
```

### Using Docker

If you don't have Pandoc installed:

```bash
docker run --rm --volume "$PWD":/data pandoc/pandoc paper.md -o paper.pdf --citeproc
```

## GitHub Workflow for Submission

### 1. Prepare Your Paper

- [ ] Complete all sections (Summary, Statement of Need, etc.)
- [ ] Add all authors and affiliations
- [ ] Include proper citations
- [ ] Add figures and supplementary materials as needed
- [ ] Review JOSS submission guidelines

### 2. Create a Submission Branch

```bash
git checkout -b paper-submission
git add .
git commit -m "Prepare paper for JOSS submission"
git push origin paper-submission
```

### 3. Create a Pull Request

Create a pull request on GitHub to prepare for submission review internally before submitting to JOSS.

### 4. Submit to JOSS

- Visit [JOSS Submissions](https://joss.theoj.org/papers/new)
- Provide:
  - Repository URL
  - Paper archive URL (GitHub release or Zenodo link)
  - DOI of the software or permanent archive link
- JOSS editors and reviewers will interact via GitHub issues

### 5. Address Reviewer Feedback

- Respond to comments in the JOSS review issue
- Make changes to your paper
- Commit and push updates to your repository

```bash
git add paper.md
git commit -m "Address reviewer comments"
git push origin main
```

## JOSS Requirements Checklist

- [ ] Paper is written in clear English
- [ ] Paper is less than 1000 words (excluding references)
- [ ] Paper describes research software (not data or hardware)
- [ ] Software has a clear research purpose
- [ ] Software is free and open source
- [ ] Software has a significant user base or potential impact
- [ ] Software documentation is sufficient
- [ ] Software has been peer-reviewed or has evidence of use
- [ ] All authors have ORCIDs (recommended)
- [ ] DOI is obtained for software version or archive

## Resources

- [JOSS Paper Guidelines](https://joss.theoj.org/about#paper_guidelines)
- [JOSS Submission Instructions](https://joss.theoj.org/papers/new)
- [JOSS Review Process](https://joss.theoj.org/about#review_process)
- [Markdown Guide](https://www.markdownguide.org/)
- [Pandoc Documentation](https://pandoc.org/MANUAL.html)
- [BibTeX Format](https://www.ctan.org/pkg/bibtex)

## Tips for Success

1. **Start Early**: Begin writing your paper well before submission
2. **Get Feedback**: Have colleagues review your paper and software
3. **Clear Software Description**: Clearly explain what your software does and why it matters
4. **Proper Citations**: Cite relevant work and your own previous publications
5. **Test Build**: Ensure your paper builds without errors before submission
6. **Follow Format**: Adhere to the YAML structure and Markdown conventions
7. **Active Repository**: Keep your software repository active and updated

## Support

For questions about JOSS submission:
- Check [JOSS FAQ](https://joss.theoj.org/about)
- Search [JOSS GitHub Issues](https://github.com/openjournals/joss/issues)
- Contact JOSS editors at `admin@theoj.org`

---

**Ready to submit?** Follow the JOSS submission process at [joss.theoj.org](https://joss.theoj.org/)
