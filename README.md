# Cornerstone of global communication: Vulnerabilities of submarine telecommunication cable from networks

This document aims to document the research initiative and implementations during the development

---

## Key info
* author's master level dissertation at The Bartlett Centre for Advanced Spatial Analysis - UCL
* Implementation of complex network in spatial analysis at the key infrastructures
* Research topic was inspired by the [International Conference on Complex Networks](https://complexnetworks.org/)

---

## Background

### Tools
* Chrome console
* Python3 Jupyter notebook
* Sqlite database
* Datagrip
* Markdown
* Latex

### Pre-requisite knowledge

* Network science or graph theory
* GIS
* Some geopolitical awareness

### Abstract
see the [pdf](https://github.com/Hypergear/UCL_Dissertation/blob/main/Dissertation_220921_1233pdf.pdf)

--- 

## Datasets

Note, the hyper links in the report might give api which might not directly accessible via web browser

Below gives browser accessible links

* [submarinecablemap](https://www.submarinecablemap.com/)
* [subtelforum](https://subtelforum.com/products/submarine-cable-almanac/)
* [infrapedia](https://www.infrapedia.com/)
* [itu](https://www.itu.int/en/ITU-D/Statistics/Pages/about.aspx)

---

## Development lifecycle

### Coding

1. Gather data raw datasets and store to db
2. Clean cable data and spatial data, then store cleaned data to db
3. Inspect data and use ML to predict the nulls
4. Assign ID to each landing stations and cable path segments
5. Create network topologies in two levels(Country, Landing station)
6. Analysis both network topologies
7. Improve the regional network in Tonga area
8. Testing

### Writing

The writing phase is split into two phases with different tools:
With the help of conversion tool from pandoc, author can switch the doc formats in between
- Development phase -> Markdown
- Production phase -> Overleaf(Latex)

The choose and design of this architecture gives more flexibility and efficiency while the report is not finished, also makes the final report more formal. 

Markdown may achieve majority of the functionalities(including citations) in latex with minimal notations. More than that, the simple grammar, multi-platform and zero-setup requirements gives more agile and smooth writing experience.:100:

---

## Future research directions

Many research area can be expanded based on the existing networks topologies. We recommended you to read relative papers

Here author wants to propose a complex network tool from a research team at stanford [node2vec](https://snap.stanford.edu/node2vec/). This tool will help you to quantitatively convert a given graph to matrix, you may implement many ML or other mathematical analysis as long as it is matrix supported