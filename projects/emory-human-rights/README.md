# Country Labeling for Human Rights Reports

At Emory, I developed country-name matching rules and prepared text for research on U.S. human-rights rhetoric. My RA work included a labeling/NLP workflow for 10K+ documents and standardizing 100K+ report sections.

## Start here

- [A country-labeling example](EXAMPLE.md): why a substring match can confuse Niger with Nigeria.
- [Country-labeling working draft](country-labeling/Labeling%20country%20names%20v4.qmd): dictionary cleanup, matching rules, and assignment logic.
- [Text preprocessing](nlp-preprocessing/NLP.ipynb) and [corpus collection](corpus-collection/labeling-pts.ipynb): selected original notebooks.

## What the labeling code does

The R draft builds a country-name dictionary, counts matches in each document, and assigns the country with the most matches. Ties and documents without matches receive `0`. Specific rules address overlapping names such as Niger/Nigeria and Sudan/South Sudan.

## Contribution and data

These are selected historical scripts from my research assistantship, not the full research corpus. The original files remain unchanged; they depend on data not included here. Some drafts contain unfinished accuracy placeholders, so no measured accuracy is claimed. The larger project and research outputs were collaborative.
