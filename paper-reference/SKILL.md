---
name: paper-reference
description: Format BibTeX references for papers in a fixed house style. Use when the user gives a BibTeX entry, DOI, arXiv ID, paper title or link and wants a bib entry, citation or reference for their paper. Trims @article entries to title/author/journal/volume/pages/year/url with abbreviated journal names, upgrades arXiv preprints to their published version when one exists, and truncates author lists to three names plus "and others".
---

# Paper reference

Turn whatever the user gives (BibTeX entry, DOI, arXiv ID or URL, title, publisher link) into a BibTeX entry in the style below. Handle several references at once if given several.

## Rules for every entry type

**Authors**
- Separate names with ` and ` (BibTeX style), never commas or `&`.
- More than 3 authors: keep the first 3 in the original order, then `and others`.
- 3 or fewer authors: list all of them, with no `and others`.
- Write each name the way the source gives it (full name or initials). Do not invent first names.

**Title**
- Always include `title`, using the paper's exact title.
- Protect capitals that must survive bibliography styles with braces: proper nouns, acronyms, chemical formulas and element symbols, e.g. `{Josephson}`, `{CZ}`, `{NbTiN}`. Wrap inline math in `$...$`.

**Key**
- Keep the citation key the user supplied. If there is none, build one from the first author's surname, the year and the first significant title word, e.g. `valadares2024magnetic`.

**Formatting**
- One field per line, two-space indent, `=` signs aligned within the entry, values in single braces `{...}`, as in the examples.

## 1. `@article` (published papers)

Keep **only** these fields, in this order: `title`, `author`, `journal`, `volume`, `pages`, `year`, `url`. Drop everything else (doi, number, month, issn, publisher, abstract, keywords, note, ...).

- `journal`: use the standard abbreviated journal name (ISO 4 / the abbreviation the journal itself uses), e.g. `Nat. Commun.`, `Phys. Rev. Lett.`, `Phys. Rev. Appl.`, `Phys. Rev. A`, `PRX Quantum`, `npj Quantum Inf.`, `Nat. Phys.`, `Rev. Mod. Phys.`, `Appl. Phys. Lett.`. If you are not certain of the abbreviation, search online (e.g. the journal's site or the ISSN/ISO 4 abbreviation list); never guess.
- `pages`: the page range or the article number (e.g. `5816`, `010501`). If the source gives a range, keep it as `start--end`.
- `url`: link to the article on the publisher's site. If you can't find that, use `https://doi.org/<doi>`.

Example:

```bibtex
@article{magnetichose1,
  title   = {On-demand transposition across light-matter interaction regimes in bosonic {cQED}},
  author  = {Fernando Valadares and Ni-Ni Huang and Kyle Timothy Ng Chu and others},
  journal = {Nat. Commun.},
  volume  = {15},
  pages   = {5816},
  year    = {2024},
  url     = {https://www.nature.com/articles/s41467-024-50201-7}
}
```

## 2. arXiv preprints

Do this for any arXiv input, whether it arrives as `@misc`, `@article` with `journal = {arXiv...}`, `eprint = ...`, an arXiv ID or an arXiv URL.

1. **Check whether it has since been published.** Look at the arXiv abstract page (`https://arxiv.org/abs/<id>`) for the "Journal reference" and "DOI" fields. Also search online by title (publisher sites, Crossref, Google Scholar), because arXiv metadata is often not updated.
2. **If it is published**, output an `@article` entry following section 1, using the journal version's metadata. Keep the user's citation key.
3. **If it is still only on arXiv**, output an `@misc` entry with exactly these fields, in this order: `title`, `author`, `howpublished = {arXiv:<id>}`, `year`, `url = {https://arxiv.org/abs/<id>}`. Use the ID without the version suffix (e.g. `1404.7456`, not `1404.7456v2`).

Example (still on arXiv):

```bibtex
@misc{adscalingbaydin2014automatic,
  title        = {Automatic Differentiation of Algorithms for Machine Learning},
  author       = {A. G. Baydin and B. A. Pearlmutter},
  howpublished = {arXiv:1404.7456},
  year         = {2014},
  url          = {https://arxiv.org/abs/1404.7456},
}
```

## 3. All other entry types

For `@book`, `@inproceedings`, `@phdthesis`, `@incollection`, `@techreport`, non-arXiv `@misc`, etc.:

- Keep **all** fields as given.
- Still apply the rules for every entry type: the author truncation with `and`, a `title` field (add it if it is missing), and the formatting.

## Output

- Return the finished BibTeX in a single ```bibtex code block.
- After the block, add one short line per entry only when something needs the user's attention: an arXiv paper you upgraded to its journal version (name the journal), a journal abbreviation you had to look up, or metadata you could not verify.
- If the user names a `.bib` file, add or update the entries there, replacing an existing entry with the same key rather than duplicating it.
